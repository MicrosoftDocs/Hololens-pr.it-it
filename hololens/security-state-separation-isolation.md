---
title: Separazione e isolamento dello stato
description: Informazioni sulla separazione dello stato, l'isolamento, la firma del codice e le applicazioni defender HoloLens 2 dispositivo di realtà mista.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: security, hololens, state separation, state separation and isolation, hololens 2, hololens2 security, security overview, security architecture, architecture, hololens 2 architecture
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0487ea49c706c753f4dfca7da7daa499d1715e9f
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2021
ms.locfileid: "126036227"
---
# <a name="state-separation-and-isolation"></a>Separazione e isolamento dello stato

La separazione e l'isolamento dello stato proteggono le parti critiche del sistema operativo Hololens 2 dalle modifiche, ad esempio quelle necessarie per l'avvio del sistema operativo in uno stato attendibile. Con la tecnologia di isolamento, le app non attendibili vengono spostate in un ambiente sandbox isolato, per garantire che non influiscano sulla sicurezza del sistema.

## <a name="state-separation"></a>Separazione dello stato

La separazione dello HoloLens 2 migliora notevolmente la sicurezza e la gestibilità (aggiornamento) e consente di proteggere i dati dell'applicazione.  La separazione dello stato funziona come segue:
  * Il sistema operativo di base viene archiviato nel volume principale del sistema operativo (sistema operativo Microsoft attendibile o verificato che aggiorna il sistema operativo).
  * Le parti del sistema operativo che possono essere modificate in fase di esecuzione,ad esempio i driver e le configurazioni scaricabili, usano un'ulteriore separazione dello stato per partizionare i dati e archiviarli in posizioni di archiviazione sicure e separate.
  * A ogni posizione di archiviazione sicura sono associati criteri di sicurezza distinti, che offrono diversi vantaggi in termini di sicurezza, come descritto nella sezione seguente.

## <a name="state-separation-benefits"></a>Vantaggi della separazione dello stato

  * Sicurezza: la separazione dello stato in primo piano HoloLens 2'integrità della piattaforma, la difesa da malware e la protezione dei dati degli utenti. Separando la parte inaffidabile del sistema operativo e rendendola di sola lettura o protetta dall'integrità, la separazione dello stato rende estremamente difficile la persistenza del malware durante un riavvio a freddo. 
  * Aggiornamenti: con HoloLens 2, quando il sistema operativo di base è immodificabile ed è stato separato in modo pulito dal resto dei dati nel dispositivo, gli aggiornamenti diventano semplici e affidabili.  Inoltre, la separazione dello stato è fondamentale per gli aggiornamenti notevolmente più veloci, che consente di sostituire il sistema operativo in un unico passaggio (unità atomica).
  * Reimpostazione del dispositivo: HoloLens 2 reimpostazione cancella i dati generati dall'utente e i dati delle app utente nel dispositivo, incluse le posizioni di archiviazione interne ed esterne. Mantiene le app correnti del sistema operativo e le app critiche per la sicurezza e le app microsoft e OEM personalizzate correnti (preinstallate). Queste app preinstallate possono essere riidratate nel dispositivo al termine della reimpostazione

### <a name="state-separation-states"></a>Stati di separazione dello stato

La separazione dello stato garantisce che il sistema operativo possa essere modificato solo dai componenti dei dispositivi attendibili Microsoft e che solo lo stato di valore elevato possa persistere tra i riavvii; L'altro stato del sistema esiste solo per la durata della sessione di avvio e viene eliminato dopo un riavvio. La separazione dello stato riporta rapidamente il dispositivo allo stato factory. Windows Holographic for Business gli stati possono essere suddivisi in queste categorie distinte:
  * Sistema operativo di base: stato non raggiungibile
  * Dati del sistema operativo - Stato modificabile 
  * Dati utente : stato modificabile

Ognuno di questi HoloLens 2 operativi è descritto nella sezione seguente.

#### <a name="core-operating-system"></a>Sistema operativo di base

Uno stato non modificabile è costituito da file eseguibili e dati non modificabili e che possono essere modificati da Microsoft solo durante l'installazione degli aggiornamenti. Durante un aggiornamento di questo tipo del sistema operativo di base, viene abilitata una nuova immagine contenente lo stato operativo desiderato più recente.
Lo stato inatteso è contrassegnato come di sola lettura (o è altrimenti protetto dall'integrità), impedendo la persistenza di qualsiasi malware con privilegi elevati. I file eseguibili e i dati seguenti sono protetti nello stato non modificabile:
  * Windows Driver di Posta in arrivo olografica
  * File binari del sistema operativo
  * Windows di posta in arrivo
  * Impostazioni Windows olografiche archiviate in Windows Hive del Registro di sistema (HKLM)
    * Esempio: HKLM archivia le informazioni di configurazione per le app installate in un computer. Archivia anche le informazioni per rilevare l'hardware e i driver corrispondenti.
Proteggendo questi elementi nello stato non modificabile (integrità e protetto di sola lettura), si garantisce che il sistema operativo di base si avvia sempre in uno stato attendibile. Inoltre, quando un dispositivo viene reimpostato, è possibile assicurarsi che il dispositivo si avvia solo nei componenti presenti in questa sezione non modificabile. 

#### <a name="operating-system-data"></a>Dati del sistema operativo 

È importante notare che i file eseguibili e i dati modificabili in fase di esecuzione (e non critici per la funzione del sistema operativo) possono essere eliminati e ri-creati quando i dati vengono danneggiati o compromessi. Uno stato modificabile di valore elevato è richiesto dal punto di vista funzionale per essere reso persistente dal sistema operativo o deve persistere tra l'arresto del sistema operativo e/o tra i riavvii da scenari supportati Windows sistemi operativi e dispositivi. Di seguito sono riportati alcuni esempi di stato modificabile di valore elevato:
  * Impostazioni globali del dispositivo configurate dall'amministratore IT, ad esempio la disabilitazione della posizione per tutti gli utenti.
  * La connessione di rete Wi-Fi accede alle reti memorizzate dal dispositivo e alle password di connessione associate.
  * Dump di arresto anomalo del sistema, inclusi impostazioni, log.
  * Driver scaricati su richiesta per i dispositivi appena individuati.
Uno stato modificabile di valore elevato nel HoloLens 2 risiede nel percorso di sicurezza dei dati del sistema operativo, come file salvato su disco o in un hive del Registro di sistema persistente.

#### <a name="user-data"></a>Dati utente

L'ultima categoria di stato rappresenta i dati utente prodotti o resi persistenti dalle applicazioni UWP o dal sistema operativo. In questo percorso vengono archiviate anche tutte le cartelle utente note, ad esempio Download, Documenti, Video, profili utente e HKEY_CURRENT_USER hive. Questi dati non possono essere estratti senza le credenziali appropriate. Per altre informazioni sulla modalità di protezione dei dati, vedere [Crittografia e protezione dei dati.](security-encryption-data-protection.md)

##  <a name="isolation"></a>Isolamento

Per ottenere questo equilibrio, HoloLens 2 dispone di un sistema operativo di base usato per le funzioni principali, ad esempio l'avvio, il controllo hardware, l'accesso e così via. Esistono solo due set di applicazioni in esecuzione nel sistema operativo di base: applicazioni preinstallato e app UWP.

## <a name="code-signing"></a>Firma del codice

La firma digitale del codice consente di verificare che i file eseguibili e gli script non siano stati modificati dopo la firma da parte di un'origine attendibile, garantendo quindi l'autenticità e l'integrità. Le autorità che HoloLens 2 attendibilità per impostazione predefinita sono Microsoft e Microsoft Store. Gli amministratori IT possono aggiungere nuovi certificati al dispositivo tramite i CSP [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) e [RootCATrustedCertificates.](/windows/client-management/mdm/rootcacertificates-csp) Possono anche usare il criterio [AllowAllTrustedApps](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) per considerare attendibili altre app sideloaded [o line-of-business.](/intune/apps/lob-apps-windows) I certificati si trovano nell'archivio certificati del computer locale archiviato in HKLM/Root se si usa "Device" o in HKCU se si usa "User".

## <a name="defender-protections"></a>Protezioni di Defender
HoloLens 2 usa servizi Microsoft per offrire agli utenti un livello di sicurezza avanzato:

* [Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) viene abilitato automaticamente in Windows Holographic dal sistema operativo e protegge da phishing e malware, nonché dal download di file potenzialmente dannosi in Microsoft Edge. Non può essere disattivata dall'utente, ma può essere disabilitata tramite criteri.

* [Defender Firewall blocca](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) il flusso del traffico di rete non autorizzato da e verso il dispositivo. È abilitato per impostazione predefinita e non può essere configurato dal cliente tramite azioni o criteri locali. 

* [Windows Defender applicazione:](/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview)HoloLens 2 supporta WDAC che consente all'amministratore IT di eseguire il push dei criteri di controllo delle applicazioni nel dispositivo. Altre informazioni sono disponibili in [Use WDAC on HoloLens 2 devices with MSFT Intune (Usare WDAC HoloLens 2 dispositivi con MSFT Intune).](/mem/intune/configuration/custom-profile-hololens) 

Gli amministratori IT possono gestire il comportamento di SmartScreen [tramite AllowSmartScreen](/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) e il comportamento del browser [tramite questi criteri.](/windows/client-management/mdm/policy-csps-supported-by-hololens2) 

