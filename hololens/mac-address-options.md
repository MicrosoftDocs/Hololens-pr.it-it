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
ms.openlocfilehash: 3e06540dd7dca8892cd69abaf9a318d46ca0f3f2
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253143"
---
# Registrazione dei dispositivi HoloLens in ambienti Wi-Fi aziendali con accesso limitato in base all'indirizzo MAC

Questo documento descrive uno scenario comune identificato negli ambienti dei clienti in cui la rete Wi-Fi è limitata in base agli indirizzi MAC, oppure dei certificati sono richiesti per accedere alle reti wireless.

## Scenario di esempio:

Molti clienti di ambienti sicuri hanno restrizioni sulle reti wireless o cablate che consentono solo la connessione dei dispositivi approvati, in base ai loro indirizzi MAC, tramite il filtro degli indirizzi MAC su un punto di accesso wireless o un server DHCP. Inoltre, alcune reti wireless possono essere protette con PEAP, che richiede l'applicazione di un certificato ai dispositivi prima di potersi autenticare correttamente alla rete wireless.

Possono emergere due problematiche che causano ritardi e richiedono l'intervento manuale per accedere alla rete con i dispositivi HoloLens.  

- Il certificato PEAP della rete wireless deve essere applicato al dispositivo prima che possa connettersi alla rete wireless.
- L'indirizzo MAC della scheda Wi-Fi di HoloLens deve essere registrato.

Le principali sfide sono:

1. Al momento, l'indirizzo MAC può essere identificato soltanto tramite l'app Impostazioni nel dispositivo, o tramite Intune dopo essersi registrati su Intune.
2. Senza l'indirizzo MAC, il dispositivo non può accedere alla rete Wi-Fi per iniziare la registrazione.
3. Le soluzioni manuali di questi problemi richiedono l'intervento tecnico sui dispositivi.

## Soluzioni

Esistono molti modi per migliorare questa situazione, a seconda dell'infrastruttura disponibile nel proprio ambiente.

| Soluzione | Vantaggi | Requisiti |
| --- | --- | --- |
| Pacchetto di provisioning con adattatore Ethernet | Migliora l'esperienza di configurazione guidata e consente interventi tecnici più rapidi. | Hub USB-C compatibile con HoloLens, il tecnico deve comunque interagire con il dispositivo per recuperare l'indirizzo MAC e finalizzare la configurazione guidata |
| Registrazione di Autopilot con Intune tramite ethernet | Connessione a singolo passaggio e registrazione del dispositivo nell'ambiente del clienteIl recupero dell'indirizzo MAC può essere completato senza interagire con il dispositivo | Intune abilitato per Azure AD del cliente, adattatore di rete USB-C compatibile con HoloLens |
| Rilevamento automatico degli indirizzi MAC | Quando i dispositivi sono stati registrati nel tenant di Intune, l'indirizzo MAC viene segnalato tramite script al tecnico. | Cmdlet di PowerShell in Intune |

## Pacchetto di provisioning con adattatore Ethernet

> [!NOTE] 
> Se anche la rete cablata è sottoposta alle limitazioni MAC, l'indirizzo MAC dell'adattatore / hub ethernet USB-C dovrà essere approvato preventivamente. Occorre prestare attenzione con l'hub, perché consentirà di accedere alla rete con altri dispositivi.

### Requisiti

- Porta di rete cablata con accesso alla rete del cliente
- Hub USB-C compatibile con HoloLens e contenente un adattatore ethernet. Qualsiasi hub che non richiede di installare applicazioni o driver aggiuntivi dovrebbe essere idoneo.
- Pacchetto di provisioning contenente:
  - Informazioni e certificati per la rete wireless
  - Informazioni per la registrazione dell'app Azure AD aziendale&#39;s (facoltativo)
  - Qualsiasi altra impostazione di provisioning necessaria

### Process

Il processo può variare in base al software del dispositivo. Se sul dispositivo è installato l'[aggiornamento di maggio 2004](hololens-release-notes.md#windows-holographic-version-2004), seguire i passi sottostanti.

1. Mettere il pacchetto di provisioning nel percorso root di una chiavetta USB, e collegarla all'hub.
2. Collegare il cavo ethernet all'hub.
3. Collegare il cavo USB-C al dispositivo HoloLens.
4. Accendere l'HoloLens e indossare il dispositivo. 
5. Premere **volume - e il pulsante di accensione** per applicare il pacchetto di provisioning. 
6. Il tecnico può ora seguire OOBE e, una volta finito, aprire l'app Impostazioni e recuperare l'indirizzo MAC del dispositivo.

Se sul dispositivo è installato un sistema operativo precedente all'[aggiornamento di maggio 2004](hololens-release-notes.md#windows-holographic-version-2004), seguire questi passaggi.

1. Attivare il dispositivo HoloLens e collegarlo a un PC.
2. Il dispositivo dovrebbe essere visualizzato nel PC come dispositivo di archiviazione di file.
3. Copiare il pacchetto di provisioning nel dispositivo
4. Collegare il cavo ethernet all'hub.
5. Collegare il cavo USB-C al dispositivo HoloLens.
6. Indossare il dispositivo.
7. Premere **volume - e il tasto di accensione** per applicare il pacchetto di provisioning.
8. Il tecnico può ora seguire OOBE e, una volta finito, aprire l'app Impostazioni e recuperare l'indirizzo MAC del dispositivo.

### Vantaggi

Ciò consente il &quot;Tocco singolo&quot; sul dispositivo per applicare il pacchetto di provisioning corretto e recuperare l'indirizzo MAC del dispositivo. [I pacchetti di provisioning possono essere creati seguendo queste indicazioni.](https://docs.microsoft.com/hololens/hololens-provisioning)

## Autopilot con registrazione Intune

### Requisiti

- Porta di rete cablata con accesso alla rete del cliente
- Dispositivi HoloLens su cui è installato Windows Holographic 2004
- Hub USB-C compatibile con HoloLens
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

### Processo

1. Collegare l'hub USB-C e il cavo ethernet al dispositivo HoloLens 2.
2. Accendere HoloLens 2.
3. Il dispositivo dovrebbe connettersi automaticamente a internet tramite configurazione attraverso l'adattatore ethernet, rilevare la configurazione di Autopilot, e registrarsi automaticamente in Azure AD e Intune
4. Il dispositivo applica le configurazioni e gli altri certificati Wi-Fi necessari tramite Intune
5. Al termine, il tecnico potrà caricare il portale Intune (Endpoint Manager) e accedere alla pagine delle proprietà del dispositivo passando a **Home -> Dispositivi -> Nome dispositivo -> Hardware**
6. L'indirizzo MAC Wi-Fi sarà visibile nel portale Intune

![Indirizzo MAC con Intune](images/mac-address-intune.jpg)

7. Il tecnico aggiunge questo indirizzo MAC come un dispositivo autorizzato.

### Vantaggi

Ciò offre al tecnico un'esperienza di distribuzione &quot;diretta&quot;, in cui il dispositivo passa dalla scatola alla registrazione in Azure AD e Intune senza che il tecnico debba indossare il dispositivo o interagire manualmente con l'ambiente di HoloLens.

## Segnalazione degli indirizzi MAC al tecnico

### Requisiti

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

### Process

Una volta completata la registrazione su Intune, il tecnico esegue lo script sovrastante per recuperare l'indirizzo MAC.
