---
title: Integración del correo electrónico de Outlook y Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Obtenga más información sobre las características de integración de correo electrónico de Teams y Outlook, incluidas las características que permiten a los usuarios compartir información entre el correo electrónico en Outlook y chat o conversaciones de canales en Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 474da725ad88221d131959078a733ed1724ae1be
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "44611184"
---
# <a name="teams-and-outlook-email-integration"></a>Integración del correo electrónico de Outlook y Teams

Microsoft Teams incluye características que facilitan a los usuarios de su organización la tarea de compartir información entre el correo electrónico en Outlook y el chat o las conversaciones de canales en Teams, así como mantenerse al día con las conversaciones perdidas. Este artículo le ofrece información general sobre estas características y los controles de administrador que se aplican.

## <a name="share-to-outlook"></a>Compartir en Outlook

**Compartir con Outlook** permite a los usuarios compartir una copia de una conversación de equipo con un correo electrónico de Outlook, sin tener que salir de Teams. Esta característica es útil si los usuarios necesitan compartir conversaciones o actualizaciones de estado con usuarios ajenos a su equipo inmediato o incluso con su organización. Vaya a la parte superior de la conversación en Teams, seleccione **̇ ̇ ̇ más opciones**y, a continuación, seleccione **compartir en Outlook**.  Para obtener más información, vea [compartir con Outlook desde Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Captura de pantalla que muestra la característica compartir con Outlook en Teams](media/share-to-outlook.png)

Para usar esta característica, Outlook en la web debe estar activado para el usuario. Si Outlook en la web está desactivado, la opción **compartir en Outlook** no se muestra en Teams para el usuario. Para conocer los pasos sobre cómo activar y desactivar Outlook en la web, vea [habilitar o deshabilitar Outlook en la web para un buzón](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).

## <a name="actionable-activity-emails"></a>Mensajes de correo electrónico de actividades accionables

Los usuarios obtienen automáticamente mensajes de correo electrónico con acciones perdidas que le ayudan a ponerse al día de las conversaciones perdidas en Teams. Los mensajes de correo electrónico actividad perdida muestran las respuestas más recientes de una conversación, incluidos los mensajes que se enviaron después del mensaje perdido y los usuarios pueden hacer clic en **responder** para responder directamente desde Outlook. Para obtener más información, consulte [responder a mensajes de correo electrónico de actividades perdidas de Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381).

![Captura de pantalla que muestra una actividad de correo electrónico perdida](media/missed-activity-email.png)

![Captura de pantalla que muestra cómo responder a un correo electrónico de actividad perdida](media/missed-activity-email-reply.png)

Puede usar el cmdlet [set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) junto con el parámetro **SmtpActionableMessagesEnabled** para desactivar los correos electrónicos accionables. De forma predeterminada, el parámetro **SmtpActionableMessagesEnabled** se establece en **true**. Establecer el parámetro en **false** desactiva los mensajes de correo electrónico que se pueda accionar en Office 365. Para los usuarios de Teams, esto significa que la opción de **respuesta** para responder directamente en Outlook no está disponible en los correos electrónicos de actividades perdidas. En su lugar, los correos electrónicos de actividad perdida incluyen una respuesta en la opción de **Teams** para que los usuarios respondan en Teams.
