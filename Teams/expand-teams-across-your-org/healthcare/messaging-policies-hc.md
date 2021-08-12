---
title: Mensajería segura para organizaciones sanitarias que usan Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Aprenda a personalizar una directiva de mensajería segura para Microsoft Teams que pueda incluir confirmaciones de lectura y notificaciones de prioridad.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b05a753873901d3faa4ae3446947c0b791b55c0b4531d9d03adf039a421c2f5a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308759"
---
# <a name="secure-messaging-for-healthcare-organizations"></a>Mensajería segura para organizaciones sanitarias

Las directivas de mensajería se utilizan para controlar qué características de mensajería de canal y de chat están disponibles para los usuarios de Microsoft Teams y, además, forman parte de la implementación general de mensajería segura para organizaciones del sector sanitario, como hospitales, clínicas o consultorios médicos, donde resulta crucial recibir un mensaje para actuar de manera oportuna, al igual que saber cuándo se leen los mensajes cruciales.

Puede usar la directiva global (predeterminada para toda la organización) o bien crear una o más directivas de mensajería personalizadas para los miembros de la organización. Los usuarios de la organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada. Después de crear una directiva personalizada, asígnela a un usuario o a grupos de usuarios de la organización. Por ejemplo, puede optar por permitir que solo ciertos roles de trabajo usen estas funciones (quizá solo médicos y enfermeras) y otros trabajadores (como el personal de limpieza o de cocina) obtengan un conjunto más limitado de funciones. Decida usted mismo qué necesidades tiene su organización usando esta guía tan solo como una forma de sugerencia.

Las directivas se administran fácilmente en el [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com) iniciando sesión con las credenciales de administrador y eligiendo **Directivas de mensajería** en el panel de navegación izquierdo.

 ![Captura de pantalla de la página Directivas de mensajería](../../media/hc-messaging-policy-admin-center.png)

Para editar la directiva de mensajería predeterminada existente para la organización, haga clic en **Global (predeterminada para toda la organización)**, tras lo cual realice los cambios. Para crear una nueva directiva de mensajería predeterminada, haga clic en **Añadir** y, después, seleccione la configuración deseada. Seleccione **Guardar** cuando termine.

![Captura de pantalla de la configuración de la directiva de mensajería](../../media/hc-messaging-policy.png)

Las siguientes configuraciones son de especial interés como aplicaciones del sector sanitario y deberían tenerse en cuenta al diseñar una directiva personalizada que se use en el mismo:

## <a name="read-receipts"></a>Confirmaciones de lectura

Las confirmaciones de lectura permiten al remitente de un mensaje de chat saber cuándo el destinatario leyó el mensaje en 1:1 y en los chats grupales de 20 personas o menos. Use esta opción para especificar si las confirmaciones de lectura las controla el usuario, están habilitadas para todos o si, por el contrario, están deshabilitadas. Los mensajes y las confirmaciones son importantes en el sector sanitario porque eliminan la incertidumbre sobre si un mensaje se leyó o no.

Para aplicar al sector sanitario, elija entre **Controladas por el usuario** o **Habilitadas para todos**. Tenga en cuenta que cuando se usa la configuración **Habilitadas para todos**, la única forma de establecer confirmaciones para todo el espacio empresarial es, o bien tener solo una directiva de mensajería para todo el espacio empresarial (la directiva predeterminada denominada «Global (predeterminada para toda la organización)») o bien que todas las directivas de mensajería del espacio empresarial usen la misma configuración para las confirmaciones. Las característica de confirmaciones de lectura es más efectiva cuando se encuentra activa como **Habilitadas para todos**.

*Un ejemplo de uso sin confirmaciones de lectura:* Jakob Roth, un paciente de alto riesgo, es ingresado en el hospital.  A Sofia Krause, una enfermera que trabaja como parte del equipo interdisciplinar (IDT) de trabajadores médicos, que incluye diferentes especialistas, se le ha asignado la coordinación de atención primaria de este paciente.  Sofía envía correos electrónicos y otros mensajes instantáneos a un grupo de enfermeras y médicos que utilizan una variedad de clientes y aplicaciones de mensajería y, a menudo, no obtiene respuesta o indicación de si los miembros del equipo leyeron un mensaje. Debido a procesos de comunicación liosos, la medicación de Jakob se aplicó incorrectamente y su estadía en el hospital se ve prolongada.

*Un ejemplo de uso con confirmaciones de lectura:* Jakob Roth, un paciente de alto riesgo, es ingresado en el hospital.  A Sofia Krause, una enfermera que trabaja como parte del equipo interdisciplinar (IDT) de trabajadores médicos, que incluye diferentes especialistas, se le ha asignado la coordinación de atención primaria de este paciente.  Sofía inicia un chat grupal con un grupo de médicos y otras enfermeras que trabajarán con el paciente para coordinar la atención, y comienza un triaje de emergencia.  Las enfermeras y los médicos se comunican y colaboran sobre el plan de atención del paciente durante todo el proceso de coordinación de la atención médica.  Los mensajes importantes y urgentes se envían a través de conversaciones de chat grupal y 1:1. Sofia utiliza la función de confirmación de lectura para determinar si los médicos o enfermeras seleccionados reciben y leen los mensajes enviados solicitando asistencia. Los resultados del paciente Jakob son casi óptimos y se va a casa antes de tiempo porque el equipo de salud logró comunicarse de forma fluida.

## <a name="send-urgent-messages-using-priority-notifications"></a>Enviar mensajes urgentes con notificaciones prioritarias

Un usuario puede marcar un mensaje como *urgente* al enviar mensajes de chat a otros usuarios. Esta función ayuda al personal del hospital a alertarse entre sí cuando un incidente crítico requiere de su atención. Al contrario que con los mensajes *importantes* normales, las [notificación prioritarias](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) notifican a los usuarios cada dos minutos durante un máximo de 20 minutos o hasta que el destinatario reciba y lea el mensaje, lo que maximiza la probabilidad de que se actúe en el momento oportuno.

Un administrador puede habilitar o deshabilitar la capacidad que los usuarios asignados a esta directiva tienen para enviar notificaciones de prioridad. Esta característica está activada de forma predeterminada. Es posible que el destinatario del mensaje prioritario no tenga la misma directiva de mensajería y, por lo tanto, no tenga la opción de deshabilitar la recepción de mensajes prioritarios. Para su aplicación al sector sanitario, recomendamos habilitar la función para, al menos, algunos usuarios, aunque deberá determinar cuáles de ellos.

*Ejemplo de uso:* Sofia Krause reingresa al paciente de alto riesgo Jakob Roth. Manuela Carstens, médica, es la doctora de atención primaria de este paciente.  Sofia envía un mensaje a Manuela mediante una notificación de prioridad, en el que pide ayuda inmediata con el triaje de Jakob.  El teléfono de Manuela recibe el mensaje pero Manuela no sintió la vibración del teléfono, con lo que no responde. Teams vuelven a notificar a Manuela y continuará notificando de manera persistente hasta que ella lea el mensaje. Si las confirmaciones de lectura también se habilitan, Sofía podrá saber que Manuela leyó el mensaje, incluso antes de que Manuela decida la respuesta.

## <a name="related-topics"></a>Temas relacionados

- [Administrar las directivas de mensajería en Teams](../../messaging-policies-in-teams.md)
- [Introducción a Teams para organizaciones sanitarias](teams-in-hc.md)
