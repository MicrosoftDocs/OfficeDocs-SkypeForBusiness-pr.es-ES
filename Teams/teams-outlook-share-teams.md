---
title: Compartir en Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre la característica Compartir Teams, que permite a los usuarios compartir correos electrónicos y datos adjuntos de correo electrónico desde Outlook a cualquier chat o canal en Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098226"
---
# <a name="share-to-teams-from-outlook"></a>Compartir a Teams desde Outlook

Compartir a Teams desde Outlook (Compartir a Teams) permite a los usuarios compartir correos electrónicos, incluidos los datos adjuntos, desde Outlook a cualquier chat o canal en Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook complemento para Compartir en Teams 

La característica Compartir Teams requiere un complemento para Outlook. Este complemento se instala automáticamente siempre que un usuario inicie sesión en la aplicación web Teams o en el Teams de escritorio.

> [!NOTE]
> Asegúrese de revisar complementos para Outlook en [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) y Reglas de acceso de cliente en [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) para asegurarse de que los complementos para Outlook funcionan correctamente. Además, deshabilitar las experiencias conectadas puede impedir que los complementos Outlook funcionen correctamente. Vea [Experiencias conectadas en Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) para obtener más información.  

Compartir en Teams usa el mismo mecanismo de transporte que cuando un usuario envía un correo electrónico a un canal. Para compartir en chats, los correos electrónicos (incluidos los datos adjuntos de correo electrónico) se copian en el OneDrive. Para compartir con canales, los correos electrónicos y los datos adjuntos se copian en la carpeta **Mensajes de** correo electrónico de SharePoint.

El complemento Outlook para Compartir en Teams usa el conjunto de requisitos 1.7, como se detalla en la documentación de complementos de [Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)que incluye detalles sobre complementos de Outlook, requisitos de entorno para complementos de Outlook y los clientes de Outlook específicos compatibles con el conjunto de requisitos 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Habilitar o deshabilitar Compartir para Teams

El Outlook para Compartir en Teams puede deshabilitarse o habilitarse selectivamente por usuario con los siguientes cmdlets de PowerShell.

> [!NOTE]
> Deshabilitar el complemento solo es posible después de instalar el complemento. Si desea exigir la deshabilitación para todos los usuarios de su inquilino, ejecute un script periódicamente.

Para deshabilitar el complemento para Outlook uso de Share para Teams, ejecute el [cmdlet que se encuentra aquí.](/powershell/module/exchange/disable-app?view=exchange-ps) 

Para habilitar el complemento para Outlook uso compartido para Teams, ejecute el [cmdlet que se encuentra aquí.](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>Exploradores y inicio de sesión único

Compartir a Teams, tanto en Outlook web como en Outlook de escritorio, se basa en un explorador WebView. Vea [Exploradores usados por Office complementos para](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) obtener información detallada sobre qué clientes usan los exploradores específicos. 

> [!IMPORTANT]
> Compartir a Teams requiere que las cookies de terceros y el acceso de almacenamiento local se habiliten para los exploradores de los usuarios.

Compartir en Teams usa inicio de sesión único (SSO), lo que significa que los usuarios no necesitan proporcionar sus credenciales al usar el complemento a través de Compartir a Teams. SSO para Outlook en la web admite https://outlook.office365.com/owa/extSSO.aspx y responde direcciones URL de forma https://outlook.office.com/owa/extSSO.aspx predeterminada. Para los dominios de vanidad, los administradores deben agregar la dirección URL Azure Active Directory respuesta.