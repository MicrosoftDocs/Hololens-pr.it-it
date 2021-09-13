---
title: Enterprise Registrazione di dispositivi HoloLens nell'indirizzo MAC con restrizioni Wi-Fi environment
description: Come determinare l'indirizzo MAC per la rete HoloLens 2 dispositivi
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
ms.openlocfilehash: d21a63aae94f5ea5269f61fe319a9036626de1b4
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036230"
---
# <a name="enterprise-enrollment-of-hololens-devices-in-mac-address-restricted-wi-fi-environment"></a>Enterprise Registrazione di dispositivi HoloLens nell'indirizzo MAC con restrizioni Wi-Fi environment

Questo documento descrive uno scenario comune identificato negli ambienti dei clienti in cui il Wi-Fi è limitato da indirizzi MAC o i certificati sono necessari per l'aggiunta a reti wireless.

## <a name="example-scenario"></a>Scenario di esempio

Molti clienti in ambienti sicuri hanno restrizioni sulle reti wireless o cablate che consentono solo ai dispositivi approvati (in base agli indirizzi MAC) di connettersi correttamente. Questa operazione può essere applicata tramite il filtro degli indirizzi MAC in un punto di accesso wireless o tramite un server DHCP. Inoltre, alcune reti wireless possono essere protette con PEAP, che richiede l'applicazione di un certificato al dispositivo prima di eseguire l'autenticazione nella rete wireless.

In questo scenario, due requisiti chiave possono introdurre ritardi o richiedere l'intervento manuale quando si HoloLens dispositivi alla rete:

- Il certificato PEAP wireless deve essere applicato al dispositivo prima che il dispositivo si unirà correttamente alla rete wireless.
- L'indirizzo MAC dell'adattatore HoloLens Wi-Fi deve essere registrato.

I principali problemi relativi ai requisiti precedenti sono i seguenti:

1. L'indirizzo MAC può attualmente essere identificato solo dall'app Impostazioni nel dispositivo o da Intune dopo una registrazione riuscita.

2. Senza l'indirizzo MAC, il dispositivo non può essere Wi-Fi rete per iniziare la registrazione.

3. Le soluzioni alternative manuali a questi problemi richiedono che un tecnico interagisca con il dispositivo.

## <a name="solutions"></a>Soluzioni

Esistono diversi modi per migliorare questa situazione, a seconda dell'infrastruttura disponibile all'interno dell'ambiente.

| Soluzione | Vantaggi | Requisiti |
| --- | --- | --- |
| Pacchetto di provisioning con adattatore Ethernet | Migliora l'esperienza di Gestione guidata e consente un'esperienza di tecnico più rapida. | HoloLens adattatore USB-C Hub + Ethernet compatibile e il tecnico dovrà comunque interagire con il dispositivo per l'acquisizione MAC e la finalizzazione della Configurazione guidata |
| Autopilot con registrazione di Intune su Ethernet | Si tratta di una connessione in un unico passaggio e della registrazione del dispositivo nell'ambiente del cliente. L'acquisizione MAC può essere completata senza dover interagire con il dispositivo | Intune abilitato per il tenant AAD del cliente e un HoloLens adattatore USB-C Ethernet compatibile |
| Creazione automatica di report degli indirizzi MAC | Quando i dispositivi vengono registrati con il tenant di Intune, uno script può segnalare l'indirizzo MAC al tecnico. | Cmdlet di PowerShell per Intune |

## <a name="provisioning-package-with-ethernet-adaptor"></a>Pacchetto di provisioning con adattatore Ethernet

> [!NOTE] 
> Se anche la rete cablata è soggetta a restrizioni MAC, sarà necessario pre-approvato anche l'indirizzo MAC dell'adattatore USB-C Hub + Ethernet. È necessario fare attenzione con questa scheda perché consentirà l'accesso alla rete da altri dispositivi.

### <a name="requirements"></a>Requisiti

- Porta di rete cablata con accesso alla rete del cliente
- HoloLens Hub USB-C compatibile con adattatore Ethernet: qualsiasi scheda che non richiede driver aggiuntivi o installazioni di applicazioni deve essere adatta.
- Pacchetto di provisioning contenente:
  - Contenente le informazioni sulla rete wireless e il certificato
  - Facoltativamente, contenenti le informazioni di registrazione per l'Azure AD
  - Contenente tutte le altre impostazioni di provisioning necessarie

### <a name="process"></a>Processo

Il processo può variare a seconda del livello software del dispositivo. Se il dispositivo ha [l'aggiornamento di maggio 2004,](hololens-release-notes.md#windows-holographic-version-2004)seguire questa procedura.

1. Posizionare il pacchetto di provisioning nella radice di una chiavetta USB e collegarlo all'hub.
2. Connessione Cavo Ethernet per la scheda Hub + Ethernet.
3. Connessione Hub USB-C per HoloLens dispositivo.
4. Accendere il HoloLens e posizionare il dispositivo.
5. Premere il **pulsante Volume down (Volume in basso) e Power** (Alimentazione) per applicare il pacchetto di provisioning.
6. Il tecnico può ora seguire la Configurazione guidata e, al termine, aprire l'app Impostazioni per recuperare l'indirizzo MAC del dispositivo.

Se il dispositivo ha una build del sistema operativo prima dell'aggiornamento di maggio [2004,](hololens-release-notes.md#windows-holographic-version-2004)seguire questa procedura.

1. Accendere il HoloLens e collegare il dispositivo a un PC.
2. Il dispositivo dovrebbe essere visualizzato nel PC come dispositivo di archiviazione file.
3. Copiare il pacchetto di provisioning nel dispositivo
4. Connessione Cavo Ethernet all'hub.
5. Connessione Hub USB-C per HoloLens dispositivo.
6. Inserire nella HoloLens
7. Premere il **pulsante Volume down (Volume in** basso) e Power (Alimentazione) per applicare il pacchetto di provisioning.
8. Il tecnico può ora seguire la Configurazione guidata e, al termine, aprire l'app Impostazioni per recuperare l'indirizzo MAC del dispositivo.

### <a name="benefits"></a>Vantaggi

In questo modo sarà possibile applicare il pacchetto di provisioning corretto e raccogliere l'indirizzo MAC del dispositivo. [I pacchetti di provisioning possono essere creati seguendo le indicazioni riportate qui.](hololens-provisioning.md)

## <a name="autopilot-with-intune-enrollment"></a>Autopilot con registrazione di Intune

### <a name="requirements"></a>Requisiti

- Porta di rete cablata con accesso alla rete del cliente
- HoloLens dispositivi che eseguono Windows Holographic 2004
- HoloLens Scheda Ethernet USB-C compatibile
- Intune configurato e abilitato per il tenant del cliente
- Dispositivo registrato per Autopilot e importato nel tenant del cliente
- Criteri di Intune definiti per il dispositivo:
   - Contenente le informazioni sulla rete wireless e il certificato
   - Contenente tutte le altre impostazioni di provisioning necessarie

Ciò consentirà a un cliente con requisiti di rete avanzati di registrare i dispositivi in un approccio scalabile e hands-off

Saranno necessari altri prerequisiti, come indicato di seguito:
1. [Abilitare il tenant per l'anteprima di Autopilot.](hololens2-autopilot.md)
1. Creare i criteri HoloLens per sostituire il pacchetto di provisioning in Intune.
1. Creare il HoloLens criteri di Intune.
1. Assegnare i dispositivi al gruppo corretto.

### <a name="process"></a>Processo

1. Connessione il cavo ethernet all'adattatore e collegare l'adattatore alla porta USB-C sul HoloLens 2 dispositivo.

2. Attivare il HoloLens.

3. Il dispositivo deve connettersi automaticamente a Internet durante la Configurazione guidata tramite l'adattatore Ethernet. Dovrebbe rilevare la configurazione di Autopilot e registrarsi automaticamente con Azure AD e Intune.

4. Il dispositivo applicherà i certificati Wi-Fi e altre configurazioni necessarie tramite Intune.

5. Al termine, il tecnico può caricare il portale di Intune (Endpoint Manager) ed esaminare la pagina delle proprietà del dispositivo in **Home -> Devices -> DeviceName -> Hardware**.

6. Il Wi-Fi MAC sarà visibile all'interno del portale di Intune.

   ![Indirizzo MAC tramite Intune.](images/mac-address-intune.jpg)

7. Il tecnico aggiungerà questo indirizzo MAC come dispositivo consentito.

### <a name="benefits"></a>Vantaggi

In questo modo il tecnico potrà eseguire un'esperienza di distribuzione "Heads off", con il dispositivo in grado di passare dalla casella alla registrazione in Azure AD e Intune senza che il tecnico abbia la necessità di usare il dispositivo o interagire manualmente con l'ambiente HoloLens.

## <a name="reporting-of-mac-addresses-to-the-technician"></a>Segnalazione di indirizzi MAC al tecnico

### <a name="requirements"></a>Requisiti

- Autorizzazione di "Intune Graph PowerShell" per il tenant del cliente
- Installazione di Intune Graph PowerShell nel computer dei tecnici.
- [https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1907.1.0)
- Accesso in lettura agli elementi "Dispositivi gestiti" di Intune. (Operatore help desk o versione superiore o un ruolo personalizzato)

Al momento non esiste un modo "semplice" per attivare un comando di automazione basato sulla registrazione di un nuovo dispositivo in Intune. Di conseguenza, questo comando fornirà al tecnico un modo semplice per recuperare l'indirizzo MAC senza dover accedere al portale e recuperarlo manualmente.

```powershell
Import-Module Microsoft.Graph.Intune

Connect-MSGraph

Get-IntuneManagedDevice -Filter "model eq 'Hololens 2'" | where {$_.enrolledDateTime -gt (get-date).AddDays(-30)}  | select deviceName, wiFiMacAddress 
```

Verranno restituiti il nome e l'indirizzo MAC HoloLens dispositivi registrati negli ultimi 30 giorni.

![Indirizzo MAC tramite PowerShell.](images/mac-address-powershell.jpg)

### <a name="process"></a>Processo

Al termine della registrazione di Intune, il tecnico eseguirebbe lo script precedente per recuperare l'indirizzo MAC.
