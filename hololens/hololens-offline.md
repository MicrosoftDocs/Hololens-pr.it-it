---
title: Gestire gli endpoint di connessione per HoloLens
description: Informazioni su come configurare un'HoloLens in una rete Wi-Fi durante la gestione e la configurazione degli endpoint di connessione.
keywords: hololens, offline, Configurazione offline
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
ms.openlocfilehash: 63c82e5b1a953ee2f69bf4c22a8442c7bca07f073cc13f1e5e573fde0ccc1976
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662932"
---
# <a name="manage-connection-endpoints-for-hololens"></a>Gestire gli endpoint di connessione per HoloLens

Alcuni HoloLens, le app e i servizi correlati trasferiscono i dati agli endpoint di rete Microsoft. Questo articolo elenca i diversi endpoint e URL che devono essere consentiti nella configurazione di rete (ad esempio proxy o firewall) per il modo in cui tali componenti siano funzionanti.    

## <a name="near-offline-setup"></a>Configurazione quasi offline

HoloLens supporta un set limitato di esperienze offline per i clienti con restrizioni relative all'ambiente di rete. Tuttavia, HoloLens deve essere stabilita una connessione di rete per eseguire la configurazione iniziale del dispositivo e devono essere abilitati gli URL seguenti:

| Scopo | URL |
|------|------|
| Sfollati | https://sdx.microsoft.com/frx/idps |
| [NCSI](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services#bkmk-ncsi) |  http://www.msftconnecttest.com/connecttest.txt  |
| AADv9 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/9 |
| AADv10 | https://login.microsoftonline.com/WebApp/CloudDomainJoin/10 |
| AAD Pin | https://account.live.com/aadngc?uiflavor=win10&showSuccess=1 |
| Account del servizio gestito | https://login.live.com/ppsecure/inlineconnect.srf?id=80600 |
| MSA Pin | https://account.live.com/msangc?fl=enroll |

## <a name="endpoint-configuration"></a>Configurazione dell'endpoint

Oltre all'elenco precedente, per sfruttare al meglio HoloLens funzionalità, nella configurazione di rete devono essere abilitati gli endpoint seguenti.


| Scopo | URL |
|------|------|
| Azure                                               | wd-prod-fe.cloudapp.azure.com                                       |
|                                                     | ris-prod-atm.trafficmanager.net                                     |
|                                                     | validation-v2.sls.trafficmanager.net                                |
| Azure AD Multi-Factor Authentication                | https://secure.aadcdn.microsoftonline-p.com                         |
| Configurazioni di Intune e MDM                       | activation-v2.sls.microsoft.com/*                                   |
|                                                     | cdn.onenote.net                                                     |
|                                                     | client.wns.windows.com                                              |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ctldl.windowsupdate.com                                             |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | dm3p.wns.windows.com                                                |
|                                                     | *microsoft.com/pkiops/*                                             |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | r.manage.microsoft.com                                              |
|                                                     | tile-service.weather.microsoft.com                                  |
|                                                     | settings-win.data.microsoft.com                                     |
| Certificati                                        | activation-v2.sls.microsoft.com/*                                   |
|                                                     | crl.microsoft.com/pki/crl/*                                         |
|                                                     | ocsp.digicert.com/*                                                 |
|                                                     | https://www.microsoft.com/pkiops/*                                          |
| Cortana e Cerca                                  | store-images.*microsoft.com                                         |
|                                                     | www.bing.com/client                                                 |
|                                                     | www.bing.com                                                        |
|                                                     | www.bing.com/proactive                                              |
|                                                     | www.bing.com/threshold/xls.aspx                                     |
|                                                     | exo-ring.msedge.net                                                 |
|                                                     | fp.msedge.net                                                       |
|                                                     | fp-vp.azureedge.net                                                 |
|                                                     | odinvzc.azureedge.net                                               |
|                                                     | spo-ring.msedge.net                                                 |
| Autenticazione del dispositivo                               | login.live.com*                                                     |
| Metadati del dispositivo                                     | dmd.metaservices.microsoft.com                                      |
| Località                                            | inference.location.live.net                                         |
|                                                     | location-inference-westus.cloudapp.net                              |
| Dati di diagnostica                                     | v10.events.data.microsoft.com                                       |
|                                                     | v10.vortex-win.data.microsoft.com/collect/v1                        |
|                                                     | https://www.microsoft.com                                                   |
|                                                     | co4.telecommand.telemetry.microsoft.com                             |
|                                                     | cs11.wpc.v0cdn.net                                                  |
|                                                     | cs1137.wpc.gammacdn.net                                             |
|                                                     | modern.watson.data.microsoft.com*                                   |
|                                                     | watson.telemetry.microsoft.com                                      |
| Gestione delle licenze                                           | licensing.mp.microsoft.com                                          |
| Account Microsoft                                   | login.msa.akadns6.net                                               |
|                                                     | us.configsvc1.live.com.akadns.net                                   |
| Microsoft Edge                                      | iecvlist.microsoft.com                                              |
| Servizio di reindirizzamento con collegamento di inoltro di Microsoft (FWLink) | go.microsoft.com                                                    |
| Microsoft Store                                     | *.wns.windows.com                                                   |
|                                                     | storecatalogrevocation.storequality.microsoft.com                   |
|                                                     | img-prod-cms-rt-microsoft-com*                                      |
|                                                     | store-images.microsoft.com                                          |
|                                                     | File con estensione md.mp.microsoft.com                                                |
|                                                     | *displaycatalog.mp.microsoft.com                                    |
|                                                     | pti.store.microsoft.com                                             |
|                                                     | storeedgefd.dsx.mp.microsoft.com                                    |
|                                                     | markets.books.microsoft.com                                         |
|                                                     | share.microsoft.com                                                 |
| Indicatore stato connettività di rete          | www.msftconnecttest.com*                                            |
| Office                                              | *.c-msedge.net                                                      |
|                                                     | *.e-msedge.net                                                      |
|                                                     | *.s-msedge.net                                                      |
|                                                     | nexusrules.officeapps.live.com                                      |
|                                                     | ocos-office365-s2s.msedge.net                                       |
|                                                     | officeclient.microsoft.com                                          |
|                                                     | outlook.office365.com                                               |
|                                                     | client-office365-tas.msedge.net                                     |
|                                                     | https://www.office.com                                                      |
|                                                     | onecollector.cloudapp.aria                                          |
|                                                     | v10.events.data.microsoft.com/onecollector/1.0/                     |
|                                                     | self.events.data.microsoft.com                                      |
|                                                     | to-do.microsoft.com                                                 |
| OneDrive                                            | g.live.com/1rewlive5skydrive/*                                      |
|                                                     | msagfx.live.com                                                     |
|                                                     | oneclient.sfx.ms                                                    |
| App Foto                                          | evoke-windowsservices-tas.msedge.net                                |
| Impostazioni                                            | cy2.settings.data.microsoft.com.akadns.net                          |
|                                                     | settings.data.microsoft.com                                         |
|                                                     | settings-win.data.microsoft.com                                     |
| Windows Defender                                    | wdcp.microsoft.com                                                  |
|                                                     | definitionupdates.microsoft.com                                     |
|                                                     | go.microsoft.com                                                    |
|                                                     | *smartscreen.microsoft.com                                          |
|                                                     | smartscreen-sn3p.smartscreen.microsoft.com                          |
|                                                     | unitedstates.smartscreen-prod.microsoft.com                         |
| Contenuti in evidenza di Windows                                   | *.search.msn.com                                                    |
|                                                     | arc.msn.com                                                         |
|                                                     | g.msn.com*                                                          |
|                                                     | query.prod.cms.rt.microsoft.com                                     |
|                                                     | ris.api.iris.microsoft.com                                          |
| Windows Update                                      | *.prod.do.dsp.mp.microsoft.com                                      |
|                                                     | cs9.wac.phicdn.net                                                  |
|                                                     | emdl.ws.microsoft.com                                               |
|                                                     | *.dl.delivery.mp.microsoft.com                                      |
|                                                     | *.windowsupdate.com                                                 |
|                                                     | *.delivery.mp.microsoft.com                                         |
|                                                     | *.update.microsoft.com                                              |



## <a name="references"></a>Riferimenti

> [!NOTE]
> Se si distribuisce D365 Remote Assist, è necessario abilitare gli endpoint elencati per SharePoint Online e OneDrive for Business negli URL Office 365 e negli intervalli di indirizzi [IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

- [Configurare i dati di diagnostica di Windows nell'organizzazione](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)
- [Gestire gli endpoint di connessione Windows 10 Enterprise versione 1903](/windows/privacy/manage-windows-1903-endpoints)
- [Gestire le connessioni Windows 10 componenti del sistema operativo a servizi Microsoft](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services)
- [Gestire le connessioni Windows 10 componenti del sistema operativo servizi Microsoft usando Microsoft Intune server MDM](/windows/privacy/manage-connections-from-windows-operating-system-components-to-microsoft-services-using-mdm)
- [Requisiti di configurazione di rete di Intune e larghezza di banda](/intune/fundamentals/network-bandwidth-use#network-communication-requirements)
- [Endpoint di rete per Microsoft Intune](/intune/fundamentals/intune-endpoints)
- [URL e intervalli di indirizzi IP per Office 365](/office365/enterprise/urls-and-ip-address-ranges)
- [Prerequisiti di Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)


## <a name="hololens-limitations"></a>HoloLens limitazioni

Dopo aver configurato il HoloLens, è possibile usarlo senza una connessione Wi-Fi, ma le app che usano connessioni Internet avranno funzionalità limitate quando si HoloLens offline.
