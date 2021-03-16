---
title: Integración de correo electrónico de Teams y Outlook
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre las características de integración de correo electrónico de Teams y Outlook, incluidas las características que permiten a los usuarios compartir información entre el correo electrónico en Outlook y las conversaciones de chat o canal en Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e469017eb9d03cbba55017ca609f49da9ebfe07a
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819366"
---
# <a name="teams-and-outlook-email-integration"></a>Integración de correo electrónico de Teams y Outlook

Microsoft Teams incluye características que permiten a los usuarios de su organización compartir información entre correo electrónico en Outlook y chatear o canalizar conversaciones en Teams y mantenerse al tanto de las conversaciones perdidas. En este artículo se ofrece información general sobre estas características y los controles de administración que se aplican.

## <a name="share-to-outlook"></a>Compartir en Outlook

**Compartir con Outlook** permite a los usuarios compartir una copia de una conversación de Teams en un correo electrónico en Outlook, sin tener que salir de Teams. Esta característica es útil si los usuarios necesitan compartir conversaciones o actualizaciones de estado con usuarios fuera de su equipo inmediato o incluso de su organización. Vaya a la parte superior de la conversación en Teams, seleccione   Para obtener más información, vea [Compartir en Outlook desde Teams.](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)

![Captura de pantalla que muestra la característica Compartir en Outlook en Teams](media/share-to-outlook.png)

Para usar esta característica, Outlook en la web debe estar activado para el usuario. Si Outlook en la web está desactivado, la opción Compartir en **Outlook** no se muestra en Teams para el usuario. Para ver los pasos sobre cómo activar y desactivar Outlook en la web, vea Habilitar o deshabilitar [Outlook en la web para un buzón.](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)

## <a name="actionable-activity-emails"></a>Correos electrónicos de actividad que se pueden actuar

Los usuarios obtienen automáticamente correos electrónicos de actividad perdida que les ayudan a ponerse al día de las conversaciones perdidas en Teams. Los correos electrónicos de actividad perdidos muestran las respuestas más recientes de una  conversación, incluidos los mensajes que se enviaron después del mensaje perdido, y los usuarios pueden hacer clic en Responder para responder directamente desde Outlook. Para obtener más información, vea Responder a mensajes [de correo electrónico de actividad perdida de Outlook.](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381) 

> [!NOTE]
> Esta característica no es compatible con Outlook para Mac ni con algunas versiones anteriores de Outlook para Windows. Para obtener más información, vea [Mensajes útiles en Outlook y grupos de Office 365.](https://docs.microsoft.com/outlook/actionable-messages/)

![Captura de pantalla que muestra un correo electrónico de actividad perdida](media/missed-activity-email.png)

![Captura de pantalla que muestra cómo responder a un correo electrónico de actividad perdido](media/missed-activity-email-reply.png)

Puede usar el cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) junto con el parámetro **SmtpActionableMessagesEnabled** para desactivar los correos electrónicos que se pueden usar. De forma predeterminada, el **parámetro SmtpActionableMessagesEnabled** se establece en **true**. Al establecer el parámetro en **false,** se desactivan los mensajes de correo electrónico que se pueden usar en Office 365. Para los usuarios de  Teams, esto significa que la opción Responder para responder directamente en Outlook no está disponible en los correos electrónicos de actividad perdida. En su lugar, los correos electrónicos de actividad perdida incluyen **una opción** Responder en Teams para que los usuarios respondan en Teams.
