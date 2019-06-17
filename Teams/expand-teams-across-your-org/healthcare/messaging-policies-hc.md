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
ms.openlocfilehash: d53a445cd7c13001fee8f365bc5d897a065de398
ms.sourcegitcommit: f735495849f02e0ea23c7d6f250e9c0656daeea1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2019
ms.locfileid: "34933860"
---
# <a name="get-started-with-secure-messaging-for-healthcare-organizations"></a>Introducción a la mensajería segura para las organizaciones sanitarias

Las directivas de mensajería se usan para controlar qué características de mensajería de chat y mensajería están disponibles para los usuarios en Microsoft Teams, y forman parte de la implementación general de mensajería segura para organizaciones de salud como hospitales, clínicas o oficinas de médicos, donde es fundamental tener un mensaje que se recoja y se actuó de forma puntual, como es saber cuándo se leen los mensajes fundamentales.

Puede usar la directiva predeterminada o bien crear una o más directivas de mensajería personalizadas para los miembros de su organización. Después de crear una directiva, tendrá que asignarla a un usuario o grupos de usuarios de la organización. Por ejemplo, puede optar por permitir que determinados roles de trabajo utilicen estas características (tal vez solo para médicos y enfermeras) y otros trabajadores (como el personal de la cocina o el JANITORIAL) para obtener un conjunto más limitado de características. Decidir usted mismo qué necesidades tiene su organización, esta guía es como más una sugerencia.

Las directivas se pueden administrar fácilmente en el [centro de administración de Microsoft Teams](http://admin.teams.microsoft.com) iniciando sesión con credenciales de administrador y eligiendo directivas de **Mensajería** en el panel de navegación izquierdo.

 ![Captura de pantalla de la página de directivas de mensajería](../../media/messaging-policies-image1.png)

Para editar la Directiva de mensajería predeterminada existente para su organización, haga clic en la fila **global (predeterminada para toda** la organización) y, a continuación, realice los cambios. Para crear una nueva Directiva de mensajería personalizada, haga clic en **nueva Directiva** y seleccione la configuración. Elija **Guardar** cuando haya terminado.

![Captura de pantalla de la configuración de directiva de mensajería](../../media/hc-message-policy.png)

La siguiente configuración es de especial interés para las aplicaciones de cuidado de la salud, y se debe tener en cuenta al diseñar una directiva personalizada que se use en el campo de asistencia sanitaria:

## <a name="read-receipts"></a>Confirmaciones de lectura

- ![Icono del número 1, que hace referencia a una llamada en la](../../media/sfbcallout1.png) captura de pantalla anterior, **lectura** de lectura confirmaciones de lectura permite al remitente de un mensaje de conversación saber cuándo el destinatario ha leído el mensaje en 1:1 y los chats grupales o menos. Use esta opción para especificar si las confirmaciones de lectura están controladas por el usuario, en para todos o desactivadas para todo el mundo. Las confirmaciones de lectura de mensajes son importantes en las organizaciones de cuidado de la salud porque no eliminan certeza acerca de si se leyó un mensaje.

  Para las aplicaciones de cuidado de la salud, elija controlado por el **usuario** o **activado para todos**. Tenga en cuenta que al usar la configuración **activado para todos** , la única forma de establecer confirmaciones para todo el inquilino es que solo tenga una directiva de mensajería para todo el inquilino (la directiva predeterminada denominada "global (valor predeterminado de toda la organización)") o para tener todas las directivas de mensajería en el inquilino usa la misma configuración para los recibos. La característica confirmaciones de lectura es más eficaz cuando la característica está habilitada para **todos los usuarios**.

    *Ejemplo de uso sin confirmaciones de lectura:* Jakob Roth, un paciente de alto riesgo, es admitido en el hospital.Sofía Krause es una enfermera que funciona como parte del equipo inter-disciplinar (IDT) de los trabajadores de medicina, incluidos los distintos especialistas, se asigna como Coordinador de atención primaria encargado de este paciente.  Sofía envía correos electrónicos y otros mensajes instantáneos a un grupo de enfermeras y doctores que usan una variedad de clientes y aplicaciones de mensajería, y con frecuencia no recibe respuesta o indica si los miembros del equipo leyeron un mensaje. Debido a los procesos de comunicación, el medicamento de Jakob se ha aplicado de forma indebida y se amplía la estadía de su hospital.

    *Ejemplo de uso con confirmaciones de lectura:* Jakob Roth, un paciente de alto riesgo, es admitido en el hospital.Sofía Krause es una enfermera que funciona como parte del equipo inter-disciplinar (IDT) de los trabajadores de medicina, incluidos los distintos especialistas, se asigna como Coordinador de atención primaria encargado de este paciente.  Sofía inicia un chat grupal con un conjunto de médicos y otros enfermeras que trabajarán con el paciente para coordinar el cuidado y comenzar una evaluación de emergencia.Los enfermeras y los médicos se comunican y colaboran en el plan de cuidados del paciente a lo largo del proceso de coordinación de cuidados.  Los mensajes importantes y urgentes se envían a través de 1:1 y conversaciones grupales. Sofía usa la función de confirmaciones de lectura para determinar si los mensajes enviados que solicitan asistencia son entregados y leídos por los médicos o enfermeras de destino. Los resultados del paciente de Jakob son casi óptimos y va a casa antes de que su equipo de atención se comunique sin problemas.

## <a name="priority-notifications"></a>Notificaciones prioritarias

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

[!INCLUDE [pri-message-offer](../../includes/pri-message-offer.md)]

- ![Icono del número 2, que hace referencia a una llamada en la](../../media/sfbcallout2.png) captura de pantalla anterior, **los usuarios pueden enviar notificaciones prioritarias** un usuario puede marcar un mensaje como "urgente" al enviar mensajes instantáneos a otros usuarios. Esta característica ayuda al personal del hospital a avisar una vez cuando un incidente importante requiere su atención. A diferencia de los mensajes "importantes" normales, las notificaciones prioritarias notifican a los usuarios cada dos minutos durante un máximo de 20 minutos o hasta que el destinatario recoja y lea el mensaje, lo cual maximizará las probabilidades de que el mensaje se haya basado puntualmente.

  Un administrador puede habilitar o deshabilitar la posibilidad de que los usuarios que tengan asignada esta directiva envíen notificaciones prioritarias. Esta característica está activada de forma predeterminada. Es posible que el destinatario del mensaje de prioridad no tenga la misma directiva de mensajería y no tendrá la opción de deshabilitar la recepción de mensajes de prioridad. Para las aplicaciones de cuidado de la salud, recomendamos habilitar la característica para al menos algunos usuarios, pero tendrá que determinar cuáles.

  *Ejemplo de uso:* Sofía Krause es readmisión de un paciente de alto riesgo, Jakob Roth. Manuela Carstens, médico, es el especialista principal para este paciente.  Sofía envía un mensaje a Manuela usando una notificación prioritaria que solicita ayuda inmediata con la evaluación de Jakob.  El teléfono de Manuela recibe el mensaje, pero Manuela no creo la vibración del teléfono y no responde. Teams vuelve a notificar a Manuela y continuará recomunicando de forma continuada hasta que lea el mensaje. Si las confirmaciones de lectura también están habilitadas, Sofía puede ser consciente de que el mensaje fue leído por Manuela, incluso antes de que Manuela decida cómo responder.

## <a name="related-topics"></a>Temas relacionados

- [Administrar directivas de mensajería de Teams](../../messaging-policies-in-teams.md)
- [Introducción a Teams para organizaciones sanitarias](teams-in-hc.md)
