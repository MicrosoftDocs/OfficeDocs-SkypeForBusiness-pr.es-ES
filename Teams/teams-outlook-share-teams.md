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
description: Obtenga información sobre la característica Compartir Teams, que permite a los usuarios compartir correos electrónicos y datos adjuntos de correo electrónico desde Outlook a cualquier chat o canal en Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb13db7a7ebb5728913b58fb712ad86d851d469a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62409833"
---
# <a name="share-to-teams-from-outlook"></a>Compartir a Teams desde Outlook

Compartir a Teams desde Outlook (Compartir a Teams) permite a los usuarios compartir correos electrónicos, incluidos los datos adjuntos, desde Outlook a cualquier chat o canal en Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook complemento para Compartir en Teams 

La característica Compartir Teams requiere un complemento para Outlook. Este complemento se instala automáticamente siempre que un usuario inicie sesión en la aplicación web Teams web o en Teams cliente de escritorio.

> [!NOTE]
> Asegúrese de revisar complementos para Outlook en [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) y Reglas de acceso de cliente en [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) para asegurarse de que los complementos para Outlook funcionan correctamente. Además, deshabilitar las experiencias conectadas puede impedir que los complementos Outlook funcionen correctamente. Vea [Experiencias conectadas en Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) para obtener más información.  

Compartir a Teams usa el mismo mecanismo de transporte que cuando un usuario envía un correo electrónico a un canal. Para compartir en chats, los correos electrónicos (incluidos los datos adjuntos de correo electrónico) se copian en el OneDrive. Para compartir con canales, los correos electrónicos y los datos adjuntos se copian en la carpeta Mensajes **de** correo electrónico de SharePoint.

El complemento Outlook para Compartir en Teams usa el conjunto de requisitos 1.7, como se detalla en la documentación de complementos de [Outlook, que](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) incluye detalles sobre complementos de Outlook, requisitos de entorno para complementos de Outlook y los clientes de Outlook específicos compatibles con el conjunto de requisitos 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Habilitar o deshabilitar Compartir para Teams

El Outlook para Compartir en Teams puede deshabilitarse o habilitarse selectivamente por usuario con los siguientes cmdlets de PowerShell.

> [!NOTE]
> Deshabilitar el complemento solo es posible después de instalar el complemento. Si desea exigir la deshabilitación para todos los usuarios de su inquilino, ejecute un script periódicamente.

Para deshabilitar el complemento para Outlook uso compartido para Teams, ejecute el [cmdlet que se encuentra aquí](/powershell/module/exchange/disable-app?view=exchange-ps). 

Para habilitar el complemento para Outlook uso compartido para Teams, ejecute el [cmdlet que se encuentra aquí](/powershell/module/exchange/enable-app?view=exchange-ps).

## <a name="browsers-and-single-sign-on"></a>Exploradores y inicio de sesión único

Compartir con Teams, tanto en Outlook en la Web como Outlook de escritorio, se basa en un explorador WebView. Vea [Exploradores usados por Office complementos](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) para obtener información detallada sobre qué clientes usan los exploradores específicos. 

> [!IMPORTANT]
> Compartir a Teams requiere que las cookies de terceros y el acceso de almacenamiento local se habiliten para los exploradores de los usuarios.

Compartir en Teams usa inicio de sesión único (SSO), lo que significa que los usuarios no necesitan proporcionar sus credenciales al usar el complemento a través de Compartir a Teams. SSO para Outlook en la Web admite https://outlook.office365.com/owa/extSSO.aspx y responder https://outlook.office.com/owa/extSSO.aspx direcciones URL de forma predeterminada. Para los dominios de vanidad, los administradores deben agregar la dirección URL Azure Active Directory respuesta.