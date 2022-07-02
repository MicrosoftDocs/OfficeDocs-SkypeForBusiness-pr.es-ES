---
title: Integración de correo electrónico de Teams y Outlook
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga más información sobre las características de integración de correo electrónico de Teams y Outlook, incluidas las características que permiten a los usuarios compartir información entre el correo electrónico en Outlook y las conversaciones de canal o chat en Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76a2ecf05a8769b51ffcb9827c0fe6ff75df7b18
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606239"
---
# <a name="teams-and-outlook-email-integration"></a>Integración de correo electrónico de Teams y Outlook

Microsoft Teams incluye características que facilitan a los usuarios de su organización compartir información entre el correo electrónico en Outlook y las conversaciones de chat o canal en Teams y mantenerse al tanto de las conversaciones perdidas. En este artículo se proporciona información general sobre estas características y los controles de administración que se aplican.

## <a name="share-to-outlook"></a>Compartir en Outlook

**Compartir en Outlook permite a** los usuarios compartir una copia de una conversación de Teams en un correo electrónico en Outlook, sin tener que salir de Teams. Esta característica es útil si los usuarios necesitan compartir conversaciones o actualizaciones de estado con usuarios que no pertenecen a su equipo inmediato o incluso a su organización. Vaya a la parte superior de la conversación en Teams, seleccione **... Más opciones** y, a continuación, seleccione **Compartir en Outlook**.  Para obtener más información, consulte [Compartir con Outlook desde Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Captura de pantalla que muestra la característica Compartir con Outlook en Teams.](media/share-to-outlook.png)

Para usar esta característica, Outlook en la Web debe estar activado para el usuario. Si Outlook en la Web está desactivada, la opción **Compartir con Outlook** no se muestra en Teams para el usuario. Para conocer los pasos para activar y desactivar Outlook en la Web, vea [Habilitar o deshabilitar Outlook en la Web para un buzón](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).

## <a name="actionable-activity-emails"></a>Mensajes de actividad procesables

Los usuarios reciben automáticamente correos electrónicos de actividad perdida accionables que les ayudan a ponerse al día con las conversaciones perdidas en Teams. Los correos electrónicos de actividad perdida muestran las respuestas más recientes de una conversación, incluidos los mensajes enviados después del mensaje perdido, y los usuarios pueden hacer clic en **Responder** para responder directamente desde Outlook. Para obtener más información, consulte [Responder a correos electrónicos de actividad perdida desde Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381). 

> [!NOTE]
> Esta característica no es compatible con Outlook para Mac ni con algunas versiones anteriores de Outlook para Windows. Para obtener más información, vea [Mensajes accionables en Outlook y grupos de Office 365](/outlook/actionable-messages/).

![Captura de pantalla que muestra un correo electrónico de actividad perdida.](media/missed-activity-email.png)

![Captura de pantalla que muestra cómo responder a un correo electrónico de actividad perdida.](media/missed-activity-email-reply.png)

Puede usar el cmdlet [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) junto con el parámetro **SmtpActionableMessagesEnabled** para desactivar los correos electrónicos que requieren acción. De forma predeterminada, el parámetro **SmtpActionableMessagesEnabled** se establece en **true**. Si establece el parámetro en **false**, se desactivarán los mensajes de correo electrónico que se puedan accionar en Office 365. Para los usuarios de Teams, esto significa que la opción **Responder** para responder directamente en Outlook no está disponible en los correos electrónicos de actividad perdida. En su lugar, los correos electrónicos de actividad perdida incluyen la opción **Responder en Teams** para que los usuarios respondan en Teams.

Vea también [Mensajes accionables en Outlook y grupos de Office 365](/outlook/actionable-messages/).
