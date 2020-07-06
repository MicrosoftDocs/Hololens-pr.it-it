---
title: Gestire gli endpoint di connessione per HoloLens
description: Per configurare il dispositivo HoloLens è necessario connetterlo a una rete Wi-Fi.
keywords: hololens, offline, OOBE
audience: ITPro
ms.date: 07/01/2019
ms.assetid: b86f603c-d25f-409b-b055-4bbc6edcd301
author: Teresa-Motiv
ms.author: v-tea
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: jarrettr
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f40d5adec0a8c0dc4bde5583a080ceedc0950fdb
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "10829222"
---
# Gestire gli endpoint di connessione per HoloLens

Alcuni componenti, app e servizi correlati di HoloLens trasferiscono i dati agli endpoint di rete Microsoft. Questo articolo elenca i vari endpoint e URL che devono essere autorizzati nella configurazione della rete, ad esempio proxy o firewall, per usare i componenti in modo corretto.    

## Configurazione con connessione di rete limitata

HoloLens supporta un set limitato di esperienze offline per i clienti con restrizioni all'ambiente di rete. Tuttavia, HoloLens richiede la connessione di rete per iniziare la configurazione del dispositivo e gli URL seguenti devono essere autorizzati:

| Scopo | URL |
|------|------|
| IDPS | https://sdx.microsoft.com/frx/idps |
| [NCSI](https://docs.microsoft.com/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| Pin AAD | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| MSA | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| Pin MSA | https://account.live.com/msangc?fl=enroll |

## Configurazione endpoint

Oltre all'elenco riportato sopra, per sfruttare al meglio le funzionalità di HoloLens, è necessario che gli endpoint seguenti siano abilitati nella configurazione della rete.


| Scopo | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |   |   |   
|                                                     | ris-prod-atm.trafficmanager.net                                     |   |   |   |
|                                                     | validation-v2.sls.trafficmanager.net                                |   |   |   |
| Autenticazione a più fattori di Azure                | https://secure.aadcdn.microsoftonline-p.com                         |   |   |   |
| Configurazioni di Intune e MDM                       | activation-v2.sls.microsoft.com/*                                   |   |   |   |
|                                                     | cdn.onenote.net                                                     |   |   |   |
|                                                     | client.wns.windows.com                                              |   |   |   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |   |   |   |
|                                                     | ctldl.windowsupdate.com                                             |   |   |   |
|                                                     | *displaycatalog.mp.microsoft.com                                    |   |   |   |
|                                                     | dm3p.wns.windows.com                                                |   |   |   |
|                                                     | *microsoft.com/pkiops/*                                             |   |   |   |
|                                                     | ocsp.digicert.com/*                                                 |   |   |   |
|                                                     | r.manage.microsoft.com                                              |   |   |   |
|                                                     | tile-service.weather.microsoft.com                                  |   |   |   |
|                                                     | settings-win.data.microsoft.com                                     |   |   |   |
| Certificati                                        | activation-v2.sls.microsoft.com/*                                   |   |   |   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |   |   |   |
|                                                     | ocsp.digicert.com/*                                                 |   |   |   |
|                                                     | https://www.microsoft.com/pkiops/*                                          |   |   |   |
| Cortana e ricerca                                  | store-images.*microsoft.com                                         |   |   |   |
|                                                     | www.bing.com/client                                                 |   |   |   |
|                                                     | www.bing.com                                                        |   |   |   |
|                                                     | www.bing.com/proactive                                              |   |   |   |
|                                                     | www.bing.com/threshold/xls.aspx                                     |   |   |   |
|                                                     | exo-ring.msedge.net                                                 |   |   |   |
|                                                     | fp.msedge.net                                                       |   |   |   |
|                                                     | fp-vp.azureedge.net                                                 |   |   |   |
|                                                     | odinvzc.azureedge.net                                               |   |   |   |
|                                                     | spo-ring.msedge.net                                                 |   |   |   |
| Autenticazione del dispositivo                               | login.live.com*                                                     |   |   |   |
| Metadati dei dispositivi                                     | dmd.metaservices.microsoft.com                                      |   |   |   |
| Location                                            | inference.location.live.net                                         |   |   |   |
|                                                     | location-inference-westus.cloudapp.net                              |   |   |   |
| Dati di diagnostica                                     | v10.events.data.microsoft.com                                       |   |   |   |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |   |   |   |
|                                                     | https://www.microsoft.com                                                   |   |   |   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |   |   |   |
|                                                     | cs11.wpc.v0cdn.net                                                  |   |   |   |
|                                                     | cs1137.wpc.gammacdn.net                                             |   |   |   |
|                                                     | modern.watson.data.microsoft.com*                                   |   |   |   |
|                                                     | watson.telemetry.microsoft.com                                      |   |   |   |
| Gestione licenze                                           | licensing.mp.microsoft.com                                          |   |   |   |
| Account Microsoft                                   | login.msa.akadns6.net                                               |   |   |   |
|                                                     | us.configsvc1.live.com.akadns.net                                   |   |   |   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |   |   |   |
| Servizio di reindirizzamento con collegamento di inoltro di Microsoft (FWLink) | go.microsoft.com                                                    |   |   |   |
| Microsoft Store                                     | *.wns.windows.com                                                   |   |   |   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |   |   |   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |   |   |   |
|                                                     | store-images.microsoft.com                                          |   |   |   |
|                                                     | .md.mp.microsoft.com                                                |   |   |
|                                                     | *displaycatalog.mp.microsoft.com                                    |   |   |   |
|                                                     | pti.store.microsoft.com                                             |   |   |   |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |   |   |   |
|                                                     | markets.books.microsoft.com                                         |   |   |   |
|                                                     | share.microsoft.com                                                 |   |   |   |
| Indicatore stato connettività di rete          | www.msftconnecttest.com*                                            |   |   |   |
| Office                                              | *.c-msedge.net                                                      |   |   |   |
|                                                     | *.e-msedge.net                                                      |   |   |   |
|                                                     | *.s-msedge.net                                                      |   |   |   |
|                                                     | nexusrules.officeapps.Live.com                                      |   |   |   |
|                                                     | ocos-office365-s2s.msedge.net                                       |   |   |   |
|                                                     | officeclient.microsoft.com                                          |   |   |   |
|                                                     | outlook.office365.com                                               |   |   |   |
|                                                     | client-office365-tas.msedge.net                                     |   |   |   |
|                                                     | https://www.office.com                                                      |   |   |   |
|                                                     | onecollector.cloudapp.aria                                          |   |   |   |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |   |   |   |
|                                                     | self.events.data.microsoft.com                                      |   |   |   |
|                                                     | to-do.microsoft.com                                                 |   |   |   |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |   |   |   |
|                                                     | msagfx.live.com                                                     |   |   |   |
|                                                     | oneclient.sfx.ms                                                    |   |   |   |
| App Foto                                          | evoke-windowsservices-tas.msedge.net                                |   |   |   |
| Impostazioni                                            | cy2.settings.data.microsoft.com.akadns.net                          |   |   |   |
|                                                     | settings.data.microsoft.com                                         |   |   |   |
|                                                     | settings-win.data.microsoft.com                                     |   |   |   |
| Windows Defender                                    | wdcp.microsoft.com                                                  |   |   |   |
|                                                     | definitionupdates.microsoft.com                                     |   |   |   |
|                                                     | go.microsoft.com                                                    |   |   |   |
|                                                     | *smartscreen.microsoft.com                                          |   |   |   |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |   |   |   |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |   |   |   |
| Contenuti in evidenza di Windows                                   | *.search.msn.com                                                    |   |   |   |
|                                                     | arc.msn.com                                                         |   |   |   |
|                                                     | g.msn.com*                                                          |   |   |   |
|                                                     | query.prod.cms.rt.microsoft.com                                     |   |   |   |
|                                                     | ris.api.iris.microsoft.com                                          |   |   |   |
| Windows Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |   |   |   |
|                                                     | cs9.wac.phicdn.net                                                  |   |   |   |
|                                                     | emdl.ws.microsoft.com                                               |   |   |   |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |   |   |   |
|                                                     | *.windowsupdate.com                                                 |   |   |   |
|                                                     | *.delivery.mp.microsoft.com                                         |   |   |   |
|                                                     | *.update.microsoft.com                                              |   |   |   |



## Riferimenti

> [!NOTE]
> Se si distribuisce D365 assistenza remota, è necessario abilitare gli endpoint contenuti in questo [elenco](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 
- [Configurare i dati di Diagnostica Windows nell'organizzazione](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Gestire gli endpoint di connessione per Windows 10 Enterprise, versione 1903](https://docs.microsoft.com/windows/privacy/manage-windows-1903-endpoints)
- [Gestire le connessioni tra i componenti del sistema operativo Windows 10 e i servizi Microsoft](https://docs.microsoft.com/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Gestire le connessioni da componenti del sistema operativo Windows 10 ai servizi Microsoft con il server MDM di Microsoft Intune](https://docs.microsoft.com/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Requisiti di configurazione e larghezza di banda della rete Intune](https://docs.microsoft.com/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Endpoint di rete per Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/intune-endpoints)
- [Intervalli di indirizzi IP e URL di Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)
- [Prerequisiti per Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## Limitazioni di HoloLens

Dopo aver configurato il dispositivo HoloLens, è possibile usarlo senza una connessione Wi-Fi. Tuttavia, quando si usa il dispositivo offline le app che usano le connessioni Internet avranno funzionalità limitate.
