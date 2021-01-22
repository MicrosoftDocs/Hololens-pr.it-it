---
title: Isolamento e separazione di stato
description: Informazioni sulla separazione dello stato, l'isolamento, la firma del codice e le applicazioni defender nel dispositivo HoloLens 2 in realtà mista.
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: sicurezza, hololens, separazione di stato, isolamento e separazione di stato, hololens 2, sicurezza hololens2, panoramica della sicurezza, architettura di sicurezza, architettura, architettura hololens 2
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 60d6d7c0e281395957ce9158144a5f3d60927682
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282807"
---
# Isolamento e separazione di stato

L'isolamento e separazione di stato impedisce la modifica delle parti fondamentali del sistema operativo HoloLens 2, ad esempio quelle necessarie per l'avvio del sistema operativo in uno stato attendibile. Con la tecnologia di isolamento, le app non attendibili vengono spostate in un ambiente sandbox isolato, per garantire che non compromettano la sicurezza del sistema.

## Separazione di stato

La separazione di stato in HoloLens 2 migliora notevolmente la sicurezza e la manutenzione (aggiornamento) e consente di proteggere i dati delle applicazioni.  La separazione di stato funziona in questo modo:
  * Il sistema operativo core è archiviato nel volume del sistema operativo core (sistema operativo Microsoft attendibile e verificato che aggiorna il sistema operativo).
  * Le parti del sistema operativo che possono essere modificate in tempo reale, ad esempio le configurazioni e i driver scaricabili, usano ulteriori separazioni di stato per partizionare i dati e archiviarli in posizioni di archiviazione separate.
  * A ogni posizione di archiviazione sicura sono associati diversi criteri di sicurezza, con vari vantaggi in termini di sicurezza illustrati in dettaglio nella sezione seguente.

## Vantaggi della separazione di stato

  * Sicurezza: la separazione di stato disponibile in HoloLens 2 migliora significativamente l'integrità della piattaforma, la resistenza ai malware e la protezione dei dati degli utenti. Separando la parte inalterabile del sistema operativo e rendendola di sola lettura o protetta per l'integrità, la separazione di stato rende estremamente complessa la persistenza del malware durante il riavvio a freddo. 
  * Aggiornamenti: con HoloLens 2, quando il sistema operativo core non è modificabile ed è stato separato dal resto dei dati nel dispositivo, gli aggiornamenti diventano semplici e affidabili.  Inoltre, la separazione di stato pone le basi per aggiornamenti nettamente più rapidi, che consente di sostituire il sistema operativo in un unico passaggio (unità atomica).
  * Reset dei dispositivi: il reset di HoloLens 2 cancella i dati generati dall'utente e i dati dell'app utente nel dispositivo, incluse le posizioni di archiviazione interna ed esterna. Mantiene le app del sistema operativo e le app critiche per la sicurezza, nonché le app personalizzate Microsoft e OEM (preinstallate) correnti. Queste app preinstallate possono essere reidratate nel dispositivo dopo il completamento del reset.

### Stati della separazione di stato

La separazione di stato assicura che il sistema operativo possa essere modificato solo dai componenti del dispositivo attendibili Microsoft e che sia consentita la persistenza solo dello stato di valore elevato durante i riavvii; gli altri stati del sistema sono disponibili solo per la durata della sessione di avvio e vengono eliminati dopo un riavvio. Con la separazione di stato è possibile ripristinare rapidamente lo stato di fabbrica del dispositivo. Gli stati di Windows Holographic for Business possono essere suddivisi in queste categorie:
  * Sistema operativo core: stato non modificabile
  * Dati del sistema operativo: stato modificabile 
  * Dati utente: stato modificabile

Questi stati operativi di HoloLens 2 sono descritti nella sezione seguente.

#### Sistema operativo core

Uno stato non modificabile è costituito da file eseguibili e dati inalterabili e può essere modificato solo da Microsoft durante l'installazione degli aggiornamenti. Durante un aggiornamento del sistema operativo core, viene abilitata una nuova immagine contenente lo stato operativo desiderato più recente.
Lo stato inalterabile è contrassegnato come di sola lettura (oppure protetto per l'integrità), impedendo la persistenza di eventuali malware con privilegi elevati. I file eseguibili e i dati seguenti sono protetti nello stato non modificabile:
  * Driver inclusi di Windows Holographic
  * File binari del sistema operativo
  * Driver inclusi di Windows
  * Impostazioni statiche di Windows Holographic archiviate nell'hive del Registro di sistema di Windows (HKLM)
    * Esempio: HKLM archivia le informazioni di configurazione per le app installate in una macchina. Archivia anche le informazioni per rilevare l'hardware e i driver corrispondenti.
Proteggendole nello stato non modificabile (protezione per l'integrità e in sola lettura), ci assicuriamo che il sistema operativo core sia venga sempre avviato in uno stato attendibile. Inoltre, quando un dispositivo viene reimpostato, è possibile fare in modo che il dispositivo venga avviato solo nei componenti presenti in questa sezione non modificabile. 

#### Dati del sistema operativo 

È importante tenere presente che i file eseguibili e i dati che sono modificabili in fase di esecuzione e che non sono essenziali per il funzionamento del sistema operativo possono essere eliminati e ricreati in caso di danneggiamento o compromissione dei dati. La persistenza di uno stato modificabile di valore elevato è funzionalmente necessaria al sistema operativo o è prevista tra gli arresti e/o i riavvii del sistema operativo in scenari supportati del sistema operativo Windows e dei dispositivi. Ecco alcuni esempi di stati modificabili di valore elevato:
  * Impostazioni globali del dispositivo configurate dall'amministratore IT, ad esempio la disabilitazione della posizione per tutti gli utenti.
  * Dati di accesso per la connessione alla rete Wi-Fi: reti memorizzate dal dispositivo e password di connessione associate.
  * Dettagli sugli arresti anomali, tra cui impostazioni e log.
  * Driver scaricati su richiesta per i nuovi dispositivi individuati.
Uno stato modificabile di valore elevato in HoloLens 2 risiede nella posizione di sicurezza dei dati del sistema operativo, in un file salvato sul disco o in un hive del Registro di sistema persistente.

#### Dati utente

L'ultima categoria di stato rappresenta i dati utente creati o resi permanenti dalle applicazioni della piattaforma UWP o dal sistema operativo. In questa posizione sono archiviate anche tutte le cartelle note degli utenti, ad esempio Download, Documenti, Video, profili utente e l'hive HKEY_CURRENT_USER. Questi dati non possono essere estratti senza le credenziali appropriate. Per saperne di più sul modo in cui vengono protetti i dati, vedere [Crittografia e protezione dei dati](security-encryption-data-protection.md).

##  Isolamento

Per raggiungere questo equilibrio, HoloLens 2 include un sistema operativo core usato per le funzioni principali, come l'avvio, il controllo hardware, l'accesso e così via. Sono disponibili solo due set di applicazioni eseguite nel sistema operativo core, ossia le applicazioni preinstallate e le app della piattaforma UWP.

## Firma del codice

Il codice firmato digitalmente consente di confermare che i file eseguibili e gli script non sono stati modificati perché sono stati firmati da una fonte attendibile, garantendo così l'autenticità e l'integrità. Le autorità che HoloLens 2 considera attendibili per impostazione predefinita sono Microsoft e Microsoft Store. Gli amministratori IT possono aggiungere nuovi certificati al dispositivo tramite i CSP [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) e [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp). Possono anche usare il [criterio AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) per rendere attendibili altre [app line-of-business](https://docs.microsoft.com/intune/apps/lob-apps-windows) o trasferite tramite sideload. I certificati risiedono nell'archivio certificati del computer locale, che si trova in HKLM/Root se si usa "Device" o in HKCU se si usa "User".

## Protezioni Defender
HoloLens 2 usa i servizi Microsoft per offrire agli utenti un livello di sicurezza avanzato:

* [Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) viene abilitato automaticamente in Windows Holographic dal sistema operativo e protegge dal phishing e dal malware, oltre che dal download di file potenzialmente dannosi, in Microsoft Edge. Non può essere disattivato dall'utente, ma può essere disabilitato tramite criteri.

* [Defender Firewall](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) blocca il flusso del traffico di rete non autorizzato in entrata e in uscita dal dispositivo. È abilitato per impostazione predefinita e non è configurabile dal cliente tramite azioni o criteri locali. 

* [Controllo di applicazioni di Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/wdac-and-applocker-overview): HoloLens 2 supporta WDAC, che consente all'amministratore IT di eseguire il push dei criteri di controllo delle applicazioni al dispositivo. Altre informazioni sono disponibili nell'articolo relativo all'[uso di WDAC nei dispositivi HoloLens 2 con Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens). 

Gli amministratori IT possono gestire il comportamento di SmartScreen con [AllowSmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsmartscreen) e il comportamento del browser mediante [questi criteri](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2). 

