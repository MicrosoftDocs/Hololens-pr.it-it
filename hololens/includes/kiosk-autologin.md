---
ms.openlocfilehash: d96a769b40daba0948f8f3c71a88513576c531b5
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859405"
---
# <a name="non-aad-configuration"></a>[Configurazione non AAD](#tab/nonaadlogon)

#### <a name="non-aad-configuration"></a>Configurazione non AAD

1. Creare un pacchetto di provisioning che:
    1. Configura le impostazioni di runtime/AssignedAccess per consentire gli account Visitor.
    1. Facoltativamente, registra il dispositivo in MDM (Impostazioni di runtime/Area di lavoro/Registrazioni) in modo che possa essere gestito in un secondo momento.
    1. Non creare un account locale
2. [Applicare il pacchetto di provisioning](../hololens-provisioning.md).

# <a name="aad-configuration"></a>[Configurazione di AAD](#tab/aadlogon)

#### <a name="aad-configuration"></a>Configurazione di AAD

I dispositivi aggiunti ad AAD configurati per la modalità tutto schermo possono accedere a un account Visitatore con un solo pulsante nella schermata di accesso. Dopo aver eseguito l'accesso all'account visitatore, il dispositivo non richiederà di nuovo l'accesso fino a quando il visitatore non viene disconnesso in modo esplicito dal menu Start o non viene riavviato il dispositivo.

L'accesso automatico del visitatore può essere gestito tramite [criteri URI OMA personalizzati:](/mem/intune/configuration/custom-settings-windows-10)

- Valore URI: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| Criteri | Descrizione | Configurazioni |
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | Consente a un visitatore di accedere automaticamente a un chiosco multimediale. | 1 (Sì), 0 (No, impostazione predefinita). |