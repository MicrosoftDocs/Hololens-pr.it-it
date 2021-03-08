---
title: Registrazione dei dispositivi HoloLens in ambienti Wi-Fi aziendali con accesso limitato in base all'indirizzo MAC
description: Come recuperare gli indirizzi MAC dei dispositivi HoloLens 2 per le reti
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: mata
ms.topic: article
ms.localizationpriority: high
ms.date: 10/01/2020
ms.reviewer: v-evmill
audience: ITPro
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: fe365248332f8e78b15ab362f169b84e48dfe594
ms.sourcegitcommit: 07ffe1bf2f45dcb2ba9d7fbe54b4773a0fb9d525
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393840"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Registrazione dei dispositivi HoloLens in ambienti Wi-Fi aziendali con accesso limitato in base all'indirizzo MAC

Questo documento descrive uno scenario comune identificato negli ambienti dei clienti in cui la rete Wi-Fi è limitata in base agli indirizzi MAC, oppure dei certificati sono richiesti per accedere alle reti wireless.

## <a name="example-scenario"></a>Scenario di esempio

Molti clienti in ambienti sicuri hanno restrizioni sulle reti wireless o cablate che consentiranno la connessione dei dispositivi approvati (in base agli indirizzi MAC). Questo può essere applicato tramite il filtro degli indirizzi MAC su un punto di accesso wireless o tramite un server DHCP. Inoltre, alcune reti wireless possono essere protette con PEAP, che richiede l'applicazione di un certificato al dispositivo prima dell'autenticazione nella rete wireless.

In questo scenario, due requisiti chiave possono introdurre ritardi o richiedere un intervento manuale quando si uniscono i dispositivi HoloLens alla rete:

- Il certificato PEAP della rete wireless deve essere applicato al dispositivo prima che possa connettersi alla rete wireless.
- L'indirizzo MAC della scheda Wi-Fi di HoloLens deve essere registrato.

Le sfide principali con i requisiti precedenti sono:

1. L'indirizzo MAC può attualmente essere identificato solo dall'app Impostazioni nel dispositivo o da Intune dopo una registrazione riuscita.
2. Senza l'indirizzo MAC, il dispositivo non può accedere alla rete Wi-Fi per iniziare la registrazione.
3. Le soluzioni alternative manuali a queste sfide richiedono a un tecnico di interagire con il dispositivo.

## <a name="solutions"></a>Soluzioni

Esistono molti modi per migliorare questa situazione, a seconda dell'infrastruttura disponibile nel proprio ambiente.

| Soluzione | Vantaggi | Requisiti |
| --- | --- | --- |
| Pacchetto di provisioning con adattatore Ethernet | Migliora l'esperienza di configurazione guidata e consente interventi tecnici più rapidi. | Scheda Hub USB-C compatibile con HoloLens e il tecnico dovrà comunque interagire con il dispositivo per l'acquisizione MAC e la finalizzazione della Configurazione guidata |
| Registrazione di Autopilot con Intune tramite ethernet | Si tratta di una connessione e registrazione passo a passo del dispositivo nell'ambiente del cliente. L'acquisizione MAC può essere completata senza dover interagire con il dispositivo | Intune abilitato per il tenant AAD del cliente e una scheda Ethernet USB-C compatibile con HoloLens |
| Rilevamento automatico degli indirizzi MAC | Quando i dispositivi vengono registrati con il tenant di Intune, uno script può segnalare l'indirizzo MAC al tecnico. | Cmdlet di PowerShell in Intune |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Pacchetto di provisioning con scheda Ethernet

> [!NOTE] 
> Se anche la rete cablata è soggetta a restrizioni MAC, sarà necessario che sia pre-approvato anche l'indirizzo MAC della scheda Hub + Ethernet USB-C. È necessario fare attenzione con questa scheda perché consentirà l'accesso alla rete da altri dispositivi.

### <a name="requirements"></a>Requisiti

- Porta di rete cablata con accesso alla rete del cliente
- Hub USB-C compatibile holoLens con scheda Ethernet: qualsiasi scheda che&#39;non richieda driver aggiuntivi o installazioni di applicazioni dovrebbe essere adatta.
- Pacchetto di provisioning contenente:
  - Informazioni e certificati per la rete wireless
  - Informazioni per la registrazione dell'app Azure AD aziendale&#39;s (facoltativo)
  - Qualsiasi altra impostazione di provisioning necessaria

### <a name="process"></a>Process

Il processo può variare in base al software del dispositivo. Se sul dispositivo è installato l'[aggiornamento di maggio 2004](hololens-release-notes.md#windows-holographic-version-2004), seguire i passi sottostanti.

1. Mettere il pacchetto di provisioning nel percorso root di una chiavetta USB, e collegarla all'hub.
2. Collegare il cavo Ethernet alla scheda Hub + Ethernet.
3. Connettere l'hub USB-C al dispositivo HoloLens.
4. Attivare HoloLens e posizionare il dispositivo.
5. Premere **Volume - e il pulsante di accensione** per applicare il pacchetto di provisioning.
6. Il tecnico può ora seguire la Configurazione guidata e, al termine, aprire l'app Impostazioni per recuperare l'indirizzo MAC del dispositivo.

Se sul dispositivo è installato un sistema operativo precedente all'[aggiornamento di maggio 2004](hololens-release-notes.md#windows-holographic-version-2004), seguire questi passaggi.

1. Attivare HoloLens e collegare il dispositivo a un PC.
2. Il dispositivo dovrebbe essere visualizzato nel PC come dispositivo di archiviazione di file.
3. Copiare il pacchetto di provisioning nel dispositivo
4. Collegare il cavo ethernet all'hub.
5. Connettere l'hub USB-C al dispositivo HoloLens.
6. Posizionare HoloLens
7. Premere **volume - e il tasto di accensione** per applicare il pacchetto di provisioning.
8. Il tecnico può ora seguire la Configurazione guidata e, al termine, aprire l'app Impostazioni per recuperare l'indirizzo MAC del dispositivo.

### <a name="benefits"></a>Vantaggi

Ciò consente il &quot;Tocco singolo&quot; sul dispositivo per applicare il pacchetto di provisioning corretto e recuperare l'indirizzo MAC del dispositivo. [I pacchetti di provisioning possono essere creati seguendo queste indicazioni.](https://docs.microsoft.com/hololens/hololens-provisioning)

## <a name="autopilot-with-intune-enrollment"></a>Autopilot con registrazione Intune

### <a name="requirements"></a>Requisiti

- Porta di rete cablata con accesso alla rete del cliente
- Dispositivi HoloLens su cui è installato Windows Holographic 2004
- Scheda Ethernet USB-C compatibile HoloLens
- Intune deve essere configurato e abilitato per il tenant del cliente
- Dispositivo registrato per Autopilot e importato nel tenant del cliente
- Criteri di Intune definiti per il dispositivo:
   - Informazioni e certificati per la rete wireless
   - Qualsiasi altra impostazione di provisioning necessaria

Ciò consente ai clienti con requisiti di connettività avanzati di registrare i dispositivi seguendo un approccio scalabile e flessibile

I prerequisiti aggiuntivi sono i seguenti:
1. [Abilitare il tenant per l'anteprima di Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)
1. Creare i criteri di HoloLens per sostituire il pacchetto di provisioning all'interno di Intune.
1. Creare i criteri di Intune per HoloLens.
1. Assegnare i dispositivi al gruppo corretto.

### <a name="process"></a>Processo

1. Collegare il cavo ethernet alla scheda e collegarlo alla porta USB-C nel dispositivo HoloLens 2.
2. Attivare HoloLens.
3. Il dispositivo deve connettersi automaticamente a Internet durante la configurazione guidata tramite la scheda Ethernet. Dovrebbe rilevare la configurazione di Autopilot e registrarsi automaticamente con Azure AD e Intune
4. Il dispositivo applica le configurazioni e gli altri certificati Wi-Fi necessari tramite Intune
5. Al termine, il tecnico può caricare il portale di Intune (Endpoint Manager) ed eseguire il drill-down nella pagina delle proprietà del dispositivo in **Home -> Dispositivi -> DeviceName -> Hardware**
6. L'indirizzo MAC sarà visibile nel portale Intune

![Indirizzo MAC con Intune](images/mac-address-intune.jpg)

7. Il tecnico aggiunge questo indirizzo MAC come un dispositivo autorizzato.

### <a name="benefits"></a>Vantaggi

Ciò offre al tecnico un'esperienza di distribuzione &quot;diretta&quot;, in cui il dispositivo passa dalla scatola alla registrazione in Azure AD e Intune senza che il tecnico debba indossare il dispositivo o interagire manualmente con l'ambiente di HoloLens.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Segnalazione degli indirizzi MAC al tecnico

### <a name="requirements"></a>Requisiti

- Autorizzazione di &quot;Intune Graph PowerShell&quot; nel tenant del cliente
- Installazione di Intune Graph PowerShell nel computer dei tecnici.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Accesso in lettura agli elementi &quot;Dispositivi gestiti&quot; di Intune. (Operatore Help desk o superiore, oppure un ruolo su misura)

Al momento non esistono modi &quot;semplici&quot; per attivare un comando i base alla registrazione di un nuovo dispositivo con Intune. Pertanto, questo comando fornisce al tecnico un modo semplice per recuperare l'indirizzo MAC senza dovere accedere al portale e recuperalo manualmente.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

In questo modo, verranno restituiti il nome e l'indirizzo MAC di qualsiasi dispositivo HoloLens registrato nei 30 giorni precedenti.

![Indirizzo MAC con PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a>Process

Una volta completata la registrazione su Intune, il tecnico esegue lo script sovrastante per recuperare l'indirizzo MAC.
