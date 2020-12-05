---
title: Guida alla distribuzione-cloud connected HoloLens 2 con Remote Assist-Panoramica
description: Registrare i dispositivi HoloLens tramite una rete connessa al cloud
keywords: HoloLens, gestione, cloud connected, Remote Assist, AAD, Azure AD, MDM, gestione di dispositivi mobili
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ba3f826360f999a72e671166af7a19d19ce9c567
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196328"
---
# Guida alla distribuzione-cloud connected HoloLens 2 con Remote Assist-Panoramica

Questa guida aiuta i professionisti IT a pianificare e distribuire i dispositivi Microsoft HoloLens 2 alla propria organizzazione con l'obiettivo generale di consentire a questi dispositivi di essere connessi alla propria organizzazione con l'assistenza remota di Dynamics 365 pronta per l'uso. Tieni presente che questo sarà un modello per le distribuzioni Proof-of-concept per la tua organizzazione in diversi casi di utilizzo di HoloLens 2.

Durante la guida verrà illustrato come registrare i dispositivi nella gestione del dispositivo, applicare le licenze in base alle esigenze e verificare che gli utenti finali siano in grado di usare immediatamente l'assistenza remota alla configurazione del dispositivo. A questo scopo, rivediamo i principali componenti dell'infrastruttura necessari per la configurazione e l'uso, ottenendo la distribuzione in scala con HoloLens 2.

## In questa guida

Questa guida ha l'obiettivo specifico di configurare l'assistenza remota all'interno dell'organizzazione nei dispositivi HoloLens. Riguarderemo le necessità necessarie per raggiungere questo obiettivo. Per mantenere lo stato attivo su questo obiettivo, alcuni preparati e configurazioni verranno preselezionati per ottimizzare la distribuzione o per ridurre gli elementi necessari per la configurazione. Sarai informato di queste opzioni e potrai personalizzare la distribuzione in base alle tue esigenze aziendali.

Si tratta di una configurazione simile allo [scenario a: distribuire ai dispositivi Cloud Connect](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), che è una buona opzione per molti strumenti di prova per le distribuzioni di concetti che includono:

- Le reti di Wi-Fi sono in genere completamente aperte a Internet e ai servizi cloud
- Join di Azure AD con registrazione automatica MDM--MDM (Intune) Managed
- Accesso degli utenti con il proprio account aziendale (AAD)
  - Singoli o più utenti per dispositivo supportati
- I vari livelli di configurazioni di blocco dei dispositivi vengono applicati in base a casi di utilizzo specifici, dal chiosco completamente aperto al singolo app

![Scenario connesso al cloud](./images/cloud-connected-deployment-chart.png)

In questa guida non verranno applicate ulteriori limitazioni o configurazioni di dispositivi, ma ti invitiamo ad esplorare queste opzioni dopo la fine.

## Informazioni sull'assistenza remota

L'assistenza remota consente la manutenzione e il ripristino collaborativo, il controllo remoto e la condivisione delle conoscenze e la formazione. Collegando persone in ruoli e posizioni diverse, un tecnico che usa l'assistenza remota può connettersi a un collaboratore remoto in Microsoft teams. Possono combinare video, screenshot e annotazioni per risolvere i problemi in tempo reale anche quando non sono&#39;t nella stessa posizione. I collaboratori remoti possono inserire immagini di riferimento, schemi e altre informazioni utili per lo spazio fisico del tecnico&#39;, in modo che possano riferirsi allo schema mentre si lavora a heads-up e Hands-Free su HoloLens.

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## In questa guida verrà:

Preparare

> [!div class="checklist"]
> - [Informazioni sull'infrastruttura Essentials per i dispositivi HoloLens 2.](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [Leggi altre informazioni su AAD e impostane una se non si ha&#39;t.](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [Informazioni sulla gestione delle identità e sulla configurazione ottimale degli account AAD.](hololens2-cloud-connected-prepare.md#identity-management)
> - [Leggi altre informazioni su MDM e configura con Intune se Don&#39;t ne hai già uno pronto.](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [Informazioni sui requisiti di rete di Remote assist.](hololens2-cloud-connected-prepare.md#network)
> - [Facoltativamente: VPN per connettersi alle risorse dell'organizzazione](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

Configurare

> [!div class="checklist"]
> - [Come creare utenti e gruppi.](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [Come configurare la registrazione automatica all'interno di AAD.](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [Come assegnare le licenze dell'applicazione.](hololens2-cloud-connected-configure.md#application-licenses)

Distribuire

> [!div class="checklist"]
> - [Configurare la registrazione di HoloLens 2 e Validate.](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [Verificare che sia possibile effettuare una chiamata assistita remota.](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

Mantenere

> [!div class="checklist"]
> - [Come aggiornare Remote Assist con l'app Microsoft Store.](hololens2-cloud-connected-maintain.md#updates)
> - [Creazione di un piano di supporto.](hololens2-cloud-connected-maintain.md#support-plan)
> - [Piano di sviluppo.](hololens2-cloud-connected-maintain.md#development-plan)

## Passaggio successivo

> [!div class="nextstepaction"]
> [Distribuzione connessa al cloud-preparare](hololens2-cloud-connected-prepare.md)

