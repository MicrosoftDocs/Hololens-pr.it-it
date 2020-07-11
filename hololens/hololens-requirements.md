---
title: Configurare HoloLens in un ambiente commerciale
description: Leggi altre informazioni su come distribuire e gestire HoloLens in ambienti aziendali.
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865565"
---
# Distribuire HoloLens in un ambiente commerciale

È possibile distribuire e configurare HoloLens in scala in un'impostazione commerciale. Questo articolo fornisce istruzioni per la distribuzione di dispositivi HoloLens in un ambiente commerciale. Questa guida presuppone familiarità di base con HoloLens. Seguire la [Guida introduttiva](hololens1-setup.md) per configurare HoloLens per la prima volta.

Questo documento presuppone inoltre che HoloLens sia stato valutato da team di sicurezza come sicuro da usare nella rete aziendale.  
> [!Tip]
> Leggi altre informazioni sulla [sicurezza di HoloLens](security-overview.md).
> Per la sicurezza di HoloLens (1a generazione), consultare le [domande frequenti](hololens1-faq-security.md).

## Panoramica dei passaggi di distribuzione

1. [Determinare le caratteristiche necessarie](hololens-requirements.md#step-1-determine-what-you-need)
1. [Determinare le licenze necessarie](hololens-licenses-requirements.md)
1. [Configurare la rete per HoloLens](hololens-commercial-infrastructure.md).
    1. Questa sezione include requisiti di larghezza di banda, URL e porte che devono essere consentiti nel firewall. Linee guida di Azure AD; Linee guida per la gestione di dispositivi mobili (MDM); Guida alla distribuzione/gestione delle app; e indicazioni per i certificati.
1. Opzionale [Configurare HoloLens usando un pacchetto di provisioning](hololens-provisioning.md)
1. [Dispositivo di registrazione](hololens-enroll-mdm.md)
1. [Configurare gli aggiornamenti basati su anello per HoloLens](hololens-updates.md)
1. [Abilitare la crittografia dispositivo Bitlocker per HoloLens](security-encryption-data-protection.md)

## Passaggio 1. Determinare le informazioni necessarie

Prima di distribuire il HoloLens nell'ambiente, è importante determinare prima quali caratteristiche, app e tipo di identità sono necessarie. È anche importante assicurarsi che il team di sicurezza abbia approvato l'uso della HoloLens nella rete aziendale. Per altre informazioni sulla sicurezza, vedere [sicurezza di HoloLens2](security-overview.md) .

### Tipo di identità

Determinare il tipo di identità che verrà usata per accedere al dispositivo.

1. **Account locali:** Questo account è locale per il dispositivo, ad esempio un account di amministratore locale in un PC Windows. In questo modo sarà possibile accedere al dispositivo solo 1 utente.
2. **MSA:** Si tratta di un account personale (ad esempio Outlook, Hotmail, Gmail, Yahoo e così via) In questo modo sarà possibile accedere al dispositivo solo 1 utente.
3. **Account di Azure Active Directory (Azure ad):** Si tratta di un account creato in Azure AD. Questo garantisce alla tua azienda la possibilità di gestire il dispositivo HoloLens. Ciò consentirà a più utenti di accedere alla HoloLens 1a gen Commercial Suite/il dispositivo HoloLens 2.

Per informazioni più dettagliate sui tipi di identità, vedere l'articolo sull' [identità di HoloLens](hololens-identity.md) .

### Tipo di funzionalità

I requisiti della funzionalità determineranno le HoloLens necessarie. Una caratteristica popolare che vediamo distribuita in ambienti cliente è spesso la modalità Kiosk. [Qui](hololens-commercial-features.md)è possibile trovare un elenco delle caratteristiche principali di HoloLens e le edizioni di HoloLens che le supportano.

**Che cos'è la modalità Kiosk?**

La modalità Kiosk è un modo per limitare le app a cui un utente ha accesso. Questo significa che agli utenti sarà consentito accedere solo ad alcune app.

**Quale modalità Kiosk è necessaria?**

Esistono due tipi di modalità Kiosk: Single app e multi-app. La modalità single app Kiosk consente all'utente di accedere a un'app solo mentre la modalità Kiosk multiapp consente agli utenti di accedere a più app specificate. Per determinare la modalità Kiosk appropriata per la propria società, è necessario rispondere alle due domande seguenti:

1. **Gli utenti diversi richiedono diverse esperienze/restrizioni?** Si consideri l'esempio seguente: l'utente A è un ingegnere del servizio di campo che deve solo accedere a Remote assist. L'utente B è un tirocinante che deve accedere solo alle guide.
    1. In caso affermativo, sarà necessario quanto segue:
        1. Account di Azure AD come metodo di accesso al dispositivo.
        1. Modalità Kiosk **multi-app** .
    1. Se no, continuare a interrogare due
1. **Hai bisogno di un'esperienza multi-app?**
    1. Se sì, è necessaria la modalità chiosco **multi-app**
    1. Se la risposta alla domanda 1 e 2 non è disponibile, è possibile usare la modalità chiosco **Single-app**

**Come configurare la modalità Kiosk:**

Esistono due modi principali ([provisioning Packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) e [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) per distribuire la modalità Kiosk per HoloLens. Queste opzioni verranno discusse più avanti nel documento; Tuttavia, è possibile usare i collegamenti descritti sopra per passare alle rispettive sezioni di questo documento.

### App e scenari specifici delle app

La maggior parte dei passaggi trovati in questo documento si applica anche alle app seguenti:

| App | Scenari specifici dell'app |
| --- | --- |
| Assistenza remota | [Comunicazione tra tenant](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| Guide  | *Prossimamente* |
|App personalizzate | *Prossimamente* |

### Determinare il metodo di registrazione

1. Registrazione in blocco con un token di sicurezza in un pacchetto di provisioning.  
  Vantaggi: questo è l'approccio più automatizzato \
  Svantaggi: richiede l'installazione iniziale sul lato server  
1. Registrazione automatica all'accesso dell'utente.  
  Vantaggi: approccio più semplice  
  Svantaggi: gli utenti dovranno completare la configurazione dopo l'applicazione del pacchetto di provisioning
1. _sconsigliato: registrare_ manualmente la registrazione post-installazione.  
  Vantaggi: possibile iscriversi dopo la configurazione  
  Svantaggi: la maggior parte degli approcci manuali e dei dispositivi non è gestibile centralmente fino a quando non viene registrato manualmente.

  Altre informazioni possono essere trovate [qui](hololens-enroll-mdm.md)

### Determinare se è necessario creare un pacchetto di provisioning

Esistono due metodi per configurare un dispositivo HoloLens (provisioning packages and MDMs). Ti consigliamo di usare MDM per configurare il dispositivo HoloLens. Tuttavia, esistono alcuni scenari in cui l'uso di un pacchetto di provisioning è la scelta migliore:

1. Si vuole configurare HoloLens per ignorare l'esperienza della casella fuori sede (OOBE)
1. Si verificano problemi durante la distribuzione di certificati in una rete complessa. La maggior parte del tempo è possibile distribuire i certificati con MDM (anche in ambienti complessi). Tuttavia, alcuni scenari richiedono la distribuzione di certificati tramite il pacchetto di provisioning.

Alcune delle configurazioni di HoloLens che è possibile applicare in un pacchetto di provisioning:

- Applicare certificati al dispositivo
- Configurare una connessione Wi-Fi
- Configurare le domande predefinite come lingua e impostazioni locali
- (HoloLens 2) Registrare in blocco la gestione dei dispositivi mobili
- (HoloLens V1) Applicare la chiave per attivare Windows Holographic for Business

Se si decide di usare i pacchetti di provisioning, seguire [questa guida](hololens-provisioning.md).

## Ottieni supporto

Ottenere supporto tramite il sito del supporto tecnico Microsoft.

[Presentare una richiesta di supporto](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
