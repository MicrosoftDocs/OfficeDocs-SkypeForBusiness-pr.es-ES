---
title: Compartir en Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre la característica Compartir en Teams, que permite a los usuarios compartir correos electrónicos y datos adjuntos de correo electrónico desde Outlook a cualquier chat o canal de Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a768424033ff300a079fc0b505d1e9ce32a970e
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682031"
---
# <a name="share-to-teams-from-outlook"></a>Compartir con Teams desde Outlook

Compartir en Teams desde Outlook (Compartir a Teams) permite a los usuarios compartir correos electrónicos, incluidos datos adjuntos, desde Outlook a cualquier chat o canal de Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook complemento para compartir en Teams 

La característica Compartir para Teams requiere un complemento para Outlook. Este complemento se instala automáticamente siempre que un usuario inicia sesión en la aplicación web de Teams o en el cliente de escritorio Teams.

> [!NOTE]
> Asegúrese de revisar [los complementos de Outlook en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) y [reglas de acceso de cliente en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) para asegurarse de que los complementos para Outlook funcionan correctamente. Además, deshabilitar las experiencias conectadas puede impedir que los complementos para Outlook funcionen correctamente. Vea [Experiencias conectadas en Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) para obtener más información.  

Compartir en Teams usa el mismo mecanismo de transporte que cuando un usuario envía correos electrónicos a un canal. Para compartir en chats, los correos electrónicos (incluidos los datos adjuntos de correo electrónico) se copian en la OneDrive del remitente. Para compartir con canales, los correos electrónicos y los datos adjuntos se copian en la carpeta **Mensajes de correo electrónico** de SharePoint.

El complemento Outlook para compartir en Teams usa el conjunto de requisitos 1.7, como se detalla en [Outlook documentación de complementos](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), que incluye detalles sobre los complementos de Outlook, los requisitos del entorno para Outlook complementos y los clientes Outlook específicos compatibles con el conjunto de requisitos 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Habilitar o deshabilitar Compartir en Teams

El complemento Outlook para Compartir en Teams se puede deshabilitar o habilitar selectivamente para cada usuario mediante los siguientes cmdlets de PowerShell.

> [!NOTE]
> Deshabilitar el complemento solo es posible después de instalarlo. Si desea exigir la deshabilitación para todos los usuarios de su inquilino, ejecute un script periódicamente.

Para deshabilitar el complemento para Outlook usa Share para Teams, ejecute el [cmdlet que se encuentra aquí](/powershell/module/exchange/disable-app).

Para habilitar el complemento para Outlook usa Share para Teams, ejecute el [cmdlet que se encuentra aquí](/powershell/module/exchange/enable-app).

## <a name="browsers-and-single-sign-on"></a>Exploradores e inicio de sesión único

Compartir con Teams, tanto en Outlook en la Web como en Outlook clientes de escritorio, se basa en un explorador WebView. Vea [Exploradores usados por Office complementos](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) para obtener más información sobre los clientes que usan los exploradores específicos. 

> [!IMPORTANT]
> Compartir con Teams requiere que tanto las cookies de terceros como el acceso al almacenamiento local estén habilitados para los exploradores de los usuarios.

Compartir en Teams usa el inicio de sesión único (SSO), lo que significa que los usuarios no necesitan proporcionar sus credenciales al usar el complemento a través de Compartir para Teams. SSO para Outlook en la Web admite <https://outlook.office365.com/owa/extSSO.aspx> direcciones URL de respuesta y <https://outlook.office.com/owa/extSSO.aspx> las admite de forma predeterminada. Para los dominios de vanidad, los administradores deben agregar la dirección URL de respuesta Azure Active Directory adecuada.
