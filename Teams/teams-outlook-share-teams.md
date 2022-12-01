---
title: Compartir en Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga más información sobre la característica Compartir en Teams, que permite a los usuarios compartir correos electrónicos y datos adjuntos de correo electrónico desde Outlook con cualquier chat o canal en Teams.
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f8334f8dbdbebce17dea4a8a4ebc8ebf798b79
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198492"
---
# <a name="share-to-teams-from-outlook"></a>Compartir en Teams desde Outlook

Compartir en Teams desde Outlook (Compartir con Teams) permite a los usuarios compartir correos electrónicos, incluidos datos adjuntos, desde Outlook a cualquier chat o canal en Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Complemento de Outlook para compartir en Teams 

La característica Compartir en Teams requiere un complemento para Outlook. Este complemento se instala automáticamente siempre que un usuario inicia sesión en la aplicación web de Teams o en el cliente de escritorio de Teams.

> [!NOTE]
> Asegúrese de revisar [complementos para Outlook en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) y [reglas de acceso de cliente en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) para asegurarse de que los complementos para Outlook funcionan correctamente. Además, deshabilitar las experiencias conectadas puede impedir que los complementos para Outlook funcionen correctamente. Vea [Experiencias conectadas en Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) para obtener más información. Los buzones compartidos no son compatibles con el complemento. 

Compartir en Teams usa el mismo mecanismo de transporte que cuando un usuario envía correos electrónicos a un canal. Para compartir en chats, los correos electrónicos (incluidos los datos adjuntos de correo electrónico) se copian en el OneDrive del remitente. Para compartir con canales, los correos electrónicos y los datos adjuntos se copian en la carpeta **de mensajes de Email** de SharePoint.

El complemento de Outlook para compartir en Teams usa el conjunto de requisitos 1.7, como se detalla en la [documentación de complementos de Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), que incluye detalles sobre los complementos de Outlook, los requisitos del entorno para los complementos de Outlook y los clientes específicos de Outlook compatibles con el conjunto de requisitos 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Habilitar o deshabilitar Compartir en Teams

El complemento de Outlook para compartir en Teams puede deshabilitarse o habilitarse selectivamente para cada usuario mediante los siguientes cmdlets de PowerShell.

> [!NOTE]
> Deshabilitar el complemento solo es posible después de instalarlo. Si desea exigir la deshabilitación para todos los usuarios de su inquilino, ejecute un script periódicamente.

Para deshabilitar el complemento para Outlook usado por Compartir en Teams, ejecute el [cmdlet que se encuentra aquí](/powershell/module/exchange/disable-app).

Para habilitar el complemento para Outlook usado por Compartir en Teams, ejecute el [cmdlet que se encuentra aquí](/powershell/module/exchange/enable-app).

## <a name="browsers-and-single-sign-on"></a>Exploradores e inicio de sesión único

Compartir con Teams, tanto en Outlook en la Web como en clientes de escritorio de Outlook, depende de un explorador WebView. Vea [Exploradores usados por complementos de Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) para obtener más información sobre qué clientes usan cada explorador específico. 

> [!IMPORTANT]
> Compartir en Teams requiere que tanto las cookies de terceros como el acceso al almacenamiento local estén habilitados para los exploradores de los usuarios.

Compartir en Teams usa el inicio de sesión único (SSO), lo que significa que los usuarios no necesitan proporcionar sus credenciales al usar el complemento a través de Compartir en Teams. SSO para Outlook en la Web admite <https://outlook.office365.com/owa/extSSO.aspx> direcciones URL de respuesta y <https://outlook.office.com/owa/extSSO.aspx> las admite de forma predeterminada. Para los dominios de vanidad, los administradores deben agregar la dirección URL de respuesta de Azure Active Directory adecuada.
