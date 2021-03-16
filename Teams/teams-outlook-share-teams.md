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
description: Obtenga información sobre la característica Compartir en Teams, que permite a los usuarios compartir correos electrónicos y datos adjuntos de correo electrónico desde Outlook a cualquier chat o canal de Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80882bddae434b66f6a3e5988c08474859b37861
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819482"
---
# <a name="share-to-teams-from-outlook"></a>Compartir en Teams desde Outlook

Compartir en Teams desde Outlook (Compartir en Teams) permite a los usuarios compartir correos electrónicos, incluidos los datos adjuntos, desde Outlook a cualquier chat o canal en Teams.

## <a name="outlook-add-in-for-share-to-teams"></a>Complemento de Outlook para compartir en Teams 

La característica Compartir en Teams requiere un complemento para Outlook. Este complemento se instala automáticamente siempre que un usuario inicie sesión en la aplicación web de Teams o en el cliente de escritorio de Teams.

> [!NOTE]
> Asegúrese de revisar complementos para Outlook en [Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) y reglas de acceso de cliente en [Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) para asegurarse de que los complementos para Outlook funcionan correctamente. Además, deshabilitar las experiencias conectadas puede impedir que los complementos de Outlook funcionen correctamente. Vea [Experiencias conectadas en Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) para obtener más información.  

Compartir en Teams usa el mismo mecanismo de transporte que cuando un usuario envía un correo electrónico a un canal. Para compartir en chats, los correos electrónicos (incluidos los datos adjuntos de correo electrónico) se copian en OneDrive del remitente. Para compartir con canales, los correos electrónicos y los datos adjuntos se copian en la carpeta **Mensajes de** correo electrónico de SharePoint.

El complemento de Outlook para compartir en Teams usa el conjunto de requisitos 1.7, como se detalla en la documentación de complementos de [Outlook,](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)que incluye detalles sobre complementos de Outlook, requisitos de entorno para complementos de Outlook y los clientes específicos de Outlook compatibles con el conjunto de requisitos 1.7.

## <a name="enabling-or-disabling-share-to-teams"></a>Habilitar o deshabilitar Compartir en Teams

El complemento de Outlook para compartir en Teams se puede deshabilitar o habilitar selectivamente por usuario con los siguientes cmdlets de PowerShell.

> [!NOTE]
> Deshabilitar el complemento solo es posible después de instalar el complemento. Si desea exigir la deshabilitación para todos los usuarios de su inquilino, ejecute un script periódicamente.

Para deshabilitar el complemento para Outlook que usa Compartir en Teams, ejecute el [cmdlet que se encuentra aquí.](https://docs.microsoft.com/powershell/module/exchange/disable-app?view=exchange-ps) 

Para habilitar el complemento para Outlook que usa Compartir en Teams, ejecute el [cmdlet que se encuentra aquí.](https://docs.microsoft.com/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>Exploradores y inicio de sesión único

Compartir en Teams, tanto en Outlook en la web como en clientes de escritorio de Outlook, se basa en un explorador WebView. Vea [Exploradores usados por los complementos de Office](https://docs.microsoft.com/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) para obtener información detallada sobre qué clientes usan los exploradores específicos. 

> [!IMPORTANT]
> Compartir en Teams requiere que las cookies de terceros y el acceso de almacenamiento local se habiliten para los exploradores de los usuarios.

Compartir en Teams usa el inicio de sesión único (SSO), lo que significa que los usuarios no necesitan proporcionar sus credenciales al usar el complemento a través de Compartir en Teams. SSO para Outlook en la web admite https://outlook.office365.com/owa/extSSO.aspx y responde direcciones URL de forma https://outlook.office.com/owa/extSSO.aspx predeterminada. Para los dominios de vanidad, los administradores deben agregar la dirección URL de respuesta de Azure Active Directory adecuada.