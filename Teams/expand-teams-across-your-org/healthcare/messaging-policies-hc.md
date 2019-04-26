---
title: Introducción a la mensajería segura para las organizaciones sanitarias
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Introducción a la mensajería segura para las organizaciones sanitarias
ms.openlocfilehash: b59ab4d487635847190c24b0f8535cbed1526e5c
ms.sourcegitcommit: 16b3ee042e8f0efacc92811ff8be093b240df9fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304951"
---
# <a name="get-started-with-secure-messaging-for-healthcare-organizations"></a>Introducción a la mensajería segura para las organizaciones sanitarias

Las directivas de mensajería se usan para controlar qué chat y canal de características de mensajería están disponibles para los usuarios de Microsoft Teams y forman parte de la implementación general de mensajería segura para las organizaciones de salud como hospitales, clínicas u oficinas médicas, donde con un mensaje de recogida y actuar de manera oportuna es crucial, como es saber cuándo se leen los mensajes cruciales.

Puede usar la directiva predeterminada o bien crear una o más directivas de mensajería personalizadas para los miembros de su organización. Después de crear una directiva, tendrá que asignarla a un usuario o grupos de usuarios de la organización. Por ejemplo, puede permitir que solo determinadas funciones de trabajo usar estas características (quizás médicos y enfermeras sólo) y otros trabajadores (al igual que el personal de Portería o cocinas) para obtener un conjunto más limitado de características. Decidir por sí mismo qué las necesidades de su organización tiene, como máximo, las instrucciones aquí son una sugerencia.

Las directivas pueden administrarse fácilmente en el [Centro de administración de equipos de Microsoft](http://admin.teams.microsoft.com) , iniciar sesión con credenciales de administrador y elija **Las directivas de mensajería** en el panel de navegación izquierdo.

 ![directivas de mensajería de los equipos](../../media/messaging-policies-image1.png)

Para editar la directiva de mensajería predeterminado existente para su organización, haga clic en la fila **Global (valor predeterminado de toda la organización)** y, a continuación, realice los cambios. Para crear una nueva directiva personalizada de mensajería, haga clic en **nueva directiva** y seleccione su configuración. Cuando haya terminado, elija **Guardar** .

![Configuración de la directiva de mensajería de Healthcare](../../media/hc-message-policy.png)

Los siguientes valores son de interés especial para aplicaciones de asistencia sanitaria y deben tenerse en cuenta al diseñar una directiva personalizada que se usa en el campo de asistencia sanitaria:

## <a name="read-reciepts"></a>Cobro de lectura

- ![número uno](../../media/sfbcallout1.png) confirmaciones de lectura de **las confirmaciones de lectura** permite al remitente de un mensaje de chat para saber cuándo su mensaje se ha leído el destinatario. Utilice esta opción para especificar si confirmaciones de lectura se usuario controlado, habilitado para todos los usuarios o deshabilitado para todos los usuarios. Mensaje leído confirmaciones son importantes en las organizaciones de salud debido a que también se quitan sin certeza sobre si se leyó un mensaje.

  Para aplicaciones de asistencia sanitaria, elija **usuario controlado** o **habilitado para todos los usuarios**. Tenga en cuenta que cuando se usa la configuración **habilitada para todos los usuarios** , la única forma de establecer confirmaciones para el inquilino todo es tener sólo una directiva de mensajería para el inquilino todo (la directiva predeterminada denominada "Global (valor predeterminado de toda la organización)") o para que todos los de mensajería las directivas en el inquilino utilizan la misma configuración para confirmaciones.

  > [!NOTE]
  > Cuando se utilizan confirmaciones en un grupo grande de lectura conversaciones (con más de 100 usuarios, por ejemplo), la recepción de mensajes pueden saturar los mensajes reales y conducir a frustraciones de usuario de chat. Esto es algo que se debe hacer que los usuarios conozcan. Una conversación en grupo más pequeña (quizás 20 usuarios o menos) hace un mejor uso de esta característica.

    *Ejemplo de uso sin confirmaciones de lectura:* Jakob Roth, un paciente de alto riesgo, es admitido en el hospital.Sofía Krause es una enfermera trabajar como parte del equipo de entre granjas disciplinario (IDT) de los trabajadores del sector médico, incluyendo a especialistas diferentes, se asigna como el Coordinador de atención primaria encargado de este paciente.  Sofía envía mensajes de correo electrónico y otros mensajes instantáneos a un grupos de enfermeras y médicos que usan una gran variedad de clientes de mensajería y aplicaciones y a menudo obtiene no hay respuesta o una indicación de si se ha leído un mensaje por los miembros del equipo. Debido a los procesos de comunicación complicada, medicación Jakob es aplicar en forma incorrecta y se ha ampliado su internación.

    *Ejemplo de uso con confirmaciones de lectura:* Jakob Roth, un paciente de alto riesgo, es admitido en el hospital.Sofía Krause es una enfermera trabajar como parte del equipo de entre granjas disciplinario (IDT) de los trabajadores del sector médico, incluyendo a especialistas diferentes, se asigna como el Coordinador de atención primaria encargado de este paciente.  Sofía inicia una conversación en grupo con un conjunto de los médicos y otros enfermeras que va a trabajar con el paciente para coordinar la atención y se inicia una evaluación de errores de emergencia.Los médicos y enfermeras comunican y colaboran en el plan de atención durante todo el proceso de coordinación de atención.  Importantes y urgentes los mensajes se envían a través de 1:1 y las conversaciones de chat de grupo. Sofía usa la funcionalidad de confirmaciones de lectura para determinar si puede enviar mensajes de solicitud de soporte técnico se entregan y leídos por el destino de los médicos o enfermeras. Los resultados del paciente Jakob son casi óptima y que va a particular antes debido a que su equipo de asistencia médica se comunica sin problemas.

## <a name="priority-notifications"></a>Notificaciones de prioridad

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

- ![número dos](../../media/sfbcallout2.png) **los usuarios pueden enviar las notificaciones de prioridad** Use esta opción para permitir a los usuarios enviar mensajes de chat de prioridad a otros usuarios. Esta característica ayuda a personal de alerta entre sí cuando un incidente crítico requiere su atención. A diferencia de los mensajes "importantes" regulares, las notificaciones de prioridad notificar a los usuarios varias veces durante un período de 20 minutos o hasta que se recogen los mensajes y leen el destinatario, maximizar la probabilidad de que el mensaje se selecciona y se realiza una acción de manera oportuna.

  Un administrador puede habilitar o deshabilitar la capacidad de los usuarios asignados a esta directiva para enviar las notificaciones de prioridad. Esta característica está activada de forma predeterminada. El destinatario del mensaje de prioridad no es posible que tienen la misma directiva de mensajería y no tendrá una opción para deshabilitar la recepción de mensajes de prioridad. Para aplicaciones de asistencia sanitaria, se recomienda habilitar la característica para al menos algunos usuarios, pero necesita determinar cuáles.

  *Ejemplo de uso:* Sofía Krause es readmitting un paciente de alto riesgo, Jakob Roth. Manuela Carstens, un médico, es el médico de atención primaria para este paciente.  Sofía envía que un mensaje a Manuela marcadas como 'Alta prioridad' y la necesidad de inmediato ayuda con la evaluación de errores de Jakob.  Teléfono de Manuela recibe el mensaje pero Manuela no se sienten la vibración de teléfono y no responde. Los equipos notifica volver a Manuela y seguirán persistentemente volver a notificar hasta que se lee el mensaje. Si se puede tener en cuenta que se ha leído el mensaje por Manuela lectura recibos también están habilitados, Sofía, incluso antes de que Manuela decide cómo responder.

## <a name="related-topics"></a>Temas relacionados

- [Administrar directivas de mensajería de Teams](../../messaging-policies-in-teams.md)
- [Introducción a Teams para organizaciones sanitarias](teams-in-hc.md)
