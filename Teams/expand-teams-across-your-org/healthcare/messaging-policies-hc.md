---
title: Mensajería segura para organizaciones de cuidados de la salud
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Introducción a la mensajería segura para las organizaciones sanitarias
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f2b431eb28d2f475bc8abdf6ac05db760200d40e
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136990"
---
# <a name="get-started-with-secure-messaging-for-healthcare-organizations"></a>Introducción a la mensajería segura para las organizaciones sanitarias

Las directivas de mensajería se usan para controlar qué características de mensajería instantánea y mensajería están disponibles para los usuarios en Microsoft Teams, y forman parte de la implementación general de mensajería segura para organizaciones de cuidados de la salud, como hospitales, clínicas o oficinas de médicos, en las que es esencial tener un mensaje que se haya seleccionado y se pueda actuar de manera oportuna, como saber cuándo se leen mensajes fundamentales

Puede usar la directiva global (opción predeterminada para toda la organización) o crear una o más directivas de mensajería personalizadas para los usuarios de su organización. Los usuarios de la organización obtendrán automáticamente la directiva global a menos que cree y asigne una directiva personalizada. Después de crear una directiva personalizada, asígnela a un usuario o a un grupo de usuarios de la organización. Por ejemplo, puede optar por permitir que determinados roles de trabajo utilicen estas características (tal vez solo para médicos y enfermeras) y otros trabajadores (como el personal de la cocina o el JANITORIAL) para obtener un conjunto más limitado de características. Decidir usted mismo qué necesidades tiene su organización, esta guía es como más una sugerencia.

Las directivas se pueden administrar fácilmente en el [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com) iniciando sesión con credenciales de administrador y eligiendo **directivas de mensajería** en el panel de navegación izquierdo.

 ![Captura de pantalla de la página de directivas de mensajería](../../media/hc-messaging-policy-admin-center.png)

Para editar la Directiva de mensajería predeterminada existente para su organización, haga clic en **global (valor predeterminado de org)** y, a continuación, realice los cambios. Para crear una nueva Directiva de mensajería personalizada, haga clic en **Agregar** y, a continuación, seleccione la configuración. Elija **Guardar** cuando haya terminado.

![Captura de pantalla de la configuración de directiva de mensajería](../../media/hc-messaging-policy.png)

La siguiente configuración es de especial interés para las aplicaciones de cuidado de la salud, y se debe tener en cuenta al diseñar una directiva personalizada que se use en el campo de asistencia sanitaria:

## <a name="read-receipts"></a>Confirmaciones de lectura

Confirmaciones de lectura permite al remitente de un mensaje instantáneo saber cuándo el destinatario ha leído su mensaje en 1:1 y los chats grupales de 20 personas o menos. Use esta opción para especificar si las confirmaciones de lectura están controladas por el usuario, en para todos o desactivadas para todo el mundo. Las confirmaciones de lectura de mensajes son importantes en las organizaciones de cuidado de la salud porque no eliminan certeza acerca de si se leyó un mensaje.

Para las aplicaciones de cuidado de la salud, elija controlado por el **usuario** o **activado para todos**. Tenga en cuenta que al usar la configuración **activado para todos** , la única forma de establecer confirmaciones para todo el inquilino es que solo tenga una directiva de mensajería para todo el inquilino (la directiva predeterminada denominada "global (valor predeterminado de toda la organización)") o para que todas las directivas de mensajería del inquilino usen la misma configuración para las confirmaciones. La característica confirmaciones de lectura es más eficaz cuando la característica está habilitada para **todos los usuarios**.

*Ejemplo de uso sin confirmaciones de lectura:* Jakob Roth, un paciente de alto riesgo, es admitido en el hospital.Sofía Krause es una enfermera que funciona como parte del equipo inter-disciplinar (IDT) de los trabajadores de medicina, incluidos los distintos especialistas, se asigna como Coordinador de atención primaria encargado de este paciente.  Sofía envía correos electrónicos y otros mensajes instantáneos a un grupo de enfermeras y doctores que usan una variedad de clientes y aplicaciones de mensajería, y con frecuencia no recibe respuesta o indica si los miembros del equipo leyeron un mensaje. Debido a los procesos de comunicación, el medicamento de Jakob se ha aplicado de forma indebida y se amplía la estadía de su hospital.

*Ejemplo de uso con confirmaciones de lectura:* Jakob Roth, un paciente de alto riesgo, es admitido en el hospital.Sofía Krause es una enfermera que funciona como parte del equipo inter-disciplinar (IDT) de los trabajadores de medicina, incluidos los distintos especialistas, se asigna como Coordinador de atención primaria encargado de este paciente.  Sofía inicia un chat grupal con un conjunto de médicos y otros enfermeras que trabajarán con el paciente para coordinar el cuidado y comenzar una evaluación de emergencia.Los enfermeras y los médicos se comunican y colaboran en el plan de cuidados del paciente a lo largo del proceso de coordinación de cuidados.  Los mensajes importantes y urgentes se envían a través de 1:1 y conversaciones grupales. Sofía usa la función de confirmaciones de lectura para determinar si los mensajes enviados que solicitan asistencia son entregados y leídos por los médicos o enfermeras de destino. Los resultados del paciente de Jakob son casi óptimos y va a casa antes de que su equipo de atención se comunique sin problemas.

## <a name="send-urgent-messages-using-priority-notifications"></a>Enviar mensajes urgentes con notificaciones prioritarias

[!INCLUDE [pri-message-offer](../../includes/pri-message-offer.md)]

Un usuario puede marcar un mensaje como *urgente* cuando envía mensajes instantáneos a otros usuarios. Esta característica ayuda al personal del hospital a avisar una vez cuando un incidente importante requiere su atención. A diferencia de los mensajes *importantes* normales, las [notificaciones prioritarias](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) notifican a los usuarios cada dos minutos durante un máximo de 20 minutos o hasta que el destinatario recoja y lea el mensaje, lo cual maximiza la probabilidad de que el mensaje se haya basado puntualmente.

Un administrador puede habilitar o deshabilitar la posibilidad de que los usuarios que tengan asignada esta directiva envíen notificaciones prioritarias. Esta característica está activada de forma predeterminada. Es posible que el destinatario del mensaje de prioridad no tenga la misma directiva de mensajería y no tendrá la opción de deshabilitar la recepción de mensajes de prioridad. Para las aplicaciones de cuidado de la salud, recomendamos habilitar la característica para al menos algunos usuarios, pero tendrá que determinar cuáles.

*Ejemplo de uso:* Sofía Krause es readmisión de un paciente de alto riesgo, Jakob Roth. Manuela Carstens, médico, es el especialista principal para este paciente.  Sofía envía un mensaje a Manuela usando una notificación prioritaria que solicita ayuda inmediata con la evaluación de Jakob.  El teléfono de Manuela recibe el mensaje, pero Manuela no creo la vibración del teléfono y no responde. Teams vuelve a notificar a Manuela y continuará recomunicando de forma continuada hasta que lea el mensaje. Si las confirmaciones de lectura también están habilitadas, Sofía puede ser consciente de que el mensaje fue leído por Manuela, incluso antes de que Manuela decida cómo responder.

## <a name="related-topics"></a>Temas relacionados

- [Administrar directivas de mensajería de Teams](../../messaging-policies-in-teams.md)
- [Introducción a Teams para organizaciones sanitarias](teams-in-hc.md)
