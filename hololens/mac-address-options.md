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
ms.openlocfilehash: a577eace62040e2d48de5d3e4cc99ef108bd006c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407621"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Registrazione dei dispositivi HoloLens in ambienti Wi-Fi aziendali con accesso limitato in base all'indirizzo MAC

Questo documento descrive uno scenario comune identificato negli ambienti dei clienti in cui la rete Wi-Fi è limitata in base agli indirizzi MAC, oppure dei certificati sono richiesti per accedere alle reti wireless.

## <a name="example-scenario"></a>Scenario di esempio

Molti clienti in ambienti sicuri hanno restrizioni sulle reti wireless o cablate che consentiranno solo ai dispositivi approvati (in base agli indirizzi MAC) di connettersi correttamente. Questo può essere applicato tramite il filtro degli indirizzi MAC su un punto di accesso wireless o tramite un server DHCP. Inoltre, alcune reti wireless possono essere protette con PEAP, che richiede l'applicazione di un certificato al dispositivo prima dell'autenticazione nella rete wireless.

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
| Pacchetto di provisioning con adattatore Ethernet | Migliora l'esperienza di configurazione guidata e consente interventi tecnici più rapidi. | Hub USB-C compatibile con HoloLens e il tecnico dovrà comunque interagire con il dispositivo per l'acquisizione MAC e la finalizzazione della Configurazione guidata |
| Registrazione di Autopilot con Intune tramite ethernet | Si tratta di una connessione e di una registrazione in un solo passaggio del dispositivo nell'ambiente del cliente. L'acquisizione MAC può essere completata senza dover interagire con il dispositivo | Intune abilitato per il tenant AAD del cliente e una scheda Ethernet USB-C compatibile con HoloLens |
| Rilevamento automatico degli indirizzi MAC | Quando i dispositivi vengono registrati con il tenant di Intune, uno script può segnalare l'indirizzo MAC al tecnico. | Cmdlet di PowerShell per Intune |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Pacchetto di provisioning con scheda Ethernet

> [!NOTE] 
> Se anche la rete cablata è soggetta a restrizioni MAC, sarà necessario che sia pre-approvato anche l'indirizzo MAC della scheda Hub + Ethernet USB-C. È necessario fare attenzione con questa scheda perché consentirà l'accesso alla rete da altri dispositivi.

### <a name="requirements"></a>Requisiti

- Porta di rete cablata con accesso alla rete del cliente
- Hub USB-C compatibile con HoloLens con scheda Ethernet: qualsiasi scheda che non richiede driver aggiuntivi o installazioni di applicazioni dovrebbe essere adatta.
- Pacchetto di provisioning contenente:
  - Informazioni e certificati per la rete wireless
  - Facoltativamente contenente informazioni di registrazione per Azure AD dell'organizzazione
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

In questo modo, un "single touch" del dispositivo può applicare il pacchetto di provisioning corretto e raccogliere l'indirizzo MAC del dispositivo. [I pacchetti di provisioning possono essere creati seguendo queste indicazioni.](https://docs.microsoft.com/hololens/hololens-provisioning)

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
1. [Abilitare il tenant per l'anteprima di Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot).
1. Creare i criteri di HoloLens per sostituire il pacchetto di provisioning all'interno di Intune.
1. Creare i criteri di Intune per HoloLens.
1. Assegnare i dispositivi al gruppo corretto.

### <a name="process"></a>Processo

1. Collegare il cavo ethernet alla scheda e collegarlo alla porta USB-C nel dispositivo HoloLens 2.

2. Attivare HoloLens.

3. Il dispositivo deve connettersi automaticamente a Internet durante la configurazione guidata tramite la scheda Ethernet. Dovrebbe rilevare la configurazione di Autopilot e registrarsi automaticamente con Azure AD e Intune.

4. Il dispositivo applicherà i certificati Wi-Fi e altre configurazioni necessarie tramite Intune.

5. Al termine, il tecnico può caricare il portale di Intune (Endpoint Manager) ed eseguire il drill-down nella pagina delle proprietà del dispositivo in **Home -> Dispositivi -> DeviceName -> Hardware**.

6. L'indirizzo MAC Wi-Fi sarà visibile nel portale Intune.

   ![Indirizzo MAC con Intune](images/mac-address-intune.jpg)

7. Il tecnico aggiunge questo indirizzo MAC come un dispositivo autorizzato.

### <a name="benefits"></a>Vantaggi

Ciò offre al tecnico un'esperienza di distribuzione diretta, in cui il dispositivo passa dalla scatola alla registrazione in Azure AD e Intune senza che il tecnico debba indossare il dispositivo o interagire manualmente con l'ambiente di HoloLens.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Segnalazione degli indirizzi MAC al tecnico

### <a name="requirements"></a>Requisiti

- Autorizzazione di "Intune Graph PowerShell" per il tenant del cliente
- Installazione di Intune Graph PowerShell nel computer dei tecnici.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Accesso in lettura agli elementi "Dispositivi gestiti" di Intune. (Operatore Help desk o superiore, oppure un ruolo su misura)

Al momento, non esiste un modo semplice per attivare un comando di automazione in base alla registrazione di un nuovo dispositivo in Intune. Pertanto, questo comando fornisce al tecnico un modo semplice per recuperare l'indirizzo MAC senza dovere accedere al portale e recuperalo manualmente.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

In questo modo verranno restituiti il nome e l'indirizzo MAC di tutti i dispositivi HoloLens registrati negli ultimi 30 giorni.

![Indirizzo MAC tramite PowerShell](images/mac-address-powershell.jpg)

### <a name="process"></a>Processo

Al termine della registrazione di Intune, il tecnico eseguirà lo script precedente per recuperare l'indirizzo MAC.
