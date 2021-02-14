---
title: Mensajería segura para organizaciones sanitarias con Microsoft Teams
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
ms.openlocfilehash: 77a2024184cb003d5d0ccb0f2b4715b3a3239955
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790633"
---
# <a name="secure-messaging-for-healthcare-organizations"></a>Mensajería segura para organizaciones sanitarias

Las directivas de mensajería se usan para controlar qué características de mensajería de chat y canal están disponibles para los usuarios en Microsoft Teams y forman parte de la implementación general de mensajería segura para organizaciones sanitarias como hospitales, clínicas o consultorios médicos, donde es crucial tener que recibir un mensaje y actuar en él de forma oportuna, como es saber cuándo se leen los mensajes cruciales.

Puede usar la directiva global (predeterminada para toda la organización) o crear una o más directivas de mensajería personalizadas para los usuarios de su organización. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada. Después de crear una directiva personalizada, asígnele un usuario o grupos de usuarios de su organización. Por ejemplo, puede optar por permitir que determinados roles de trabajo usen estas características (quizás solo médicos y enfermeras) y que otros trabajadores (como el personal de educación o de cocina) obtengan un conjunto más limitado de características. Decida por sí mismo qué necesidades tiene su organización, las instrucciones que se proporcionan aquí son como máximo una sugerencia.

Las directivas se pueden administrar fácilmente en el centro de administración de [Microsoft Teams](https://admin.teams.microsoft.com) iniciando sesión con credenciales de administrador y eligiendo Directivas de mensajería **en** el panel de navegación izquierdo.

 ![Captura de pantalla de la página Directivas de mensajería](../../media/hc-messaging-policy-admin-center.png)

Para editar la directiva de mensajería predeterminada existente para su organización, haga clic en **Global (predeterminada** para toda la organización) y realice los cambios. Para crear una nueva directiva de mensajería personalizada, haga clic **en Agregar** y, a continuación, seleccione la configuración. Elija **Guardar** cuando haya terminado.

![Captura de pantalla de la configuración de directiva de mensajería](../../media/hc-messaging-policy.png)

Los siguientes ajustes son de especial interés para las aplicaciones sanitarias y deben tenerse en cuenta al diseñar una directiva personalizada usada en el campo Salud:

## <a name="read-receipts"></a>Confirmaciones de lectura

Las confirmaciones de lectura permiten al remitente de un mensaje de chat saber cuándo el destinatario leyó el mensaje en uno a uno y los chats grupales de 20 personas o menos. Use esta opción para especificar si las confirmaciones de lectura son controladas por el usuario, por todos los usuarios o desactivadas para todos. Las confirmaciones de lectura de mensajes son importantes en las organizaciones sanitarias, ya que eliminan sin dudas si un mensaje se leyó.

En el caso de las aplicaciones sanitarias, **elija "Usuario controlado"** **o "On" para todos los usuarios.** Tenga en cuenta  que, al usar la configuración "Activa para todos los usuarios", la única forma de establecer confirmaciones para todo el espacio empresarial es tener una sola directiva de mensajería para todo el inquilino (la directiva predeterminada denominada "Global (predeterminado para toda la organización)" o que todas las directivas de mensajería del inquilino usen la misma configuración para los recibos. La característica de confirmaciones de lectura es más eficaz cuando la característica está habilitada para **activarse para todos los usuarios.**

*Ejemplo de uso sin confirmaciones de lectura:* Jakob Jakob, paciente de alto riesgo, es admitido en el hospital.  Sofía Krause es una enfermera que trabaja como parte del equipo intermedio (IDT) de trabajadores médicos, incluidos distintos especialistas, que se asigna como la cuidado principal responsable de este paciente.  Sofía envía correos electrónicos y otros mensajes instantáneos a un grupo de enfermeras y médicos que usan diversos clientes de mensajería y aplicaciones, y a menudo no recibe ninguna respuesta o indicación de si los miembros del equipo han leído un mensaje. Debido a los procesos de comunicación enredados, el medicamentos de Jakob se toma de forma errónea y su hospital permanece extendido.

*Ejemplo de uso con confirmaciones de lectura:* Jakob Jakob, paciente de alto riesgo, es admitido en el hospital.  Sofía Krause es una enfermera que trabaja como parte del equipo intermedio (IDT) de trabajadores médicos, incluidos distintos especialistas, que se asigna como la cuidado principal responsable de este paciente.  Sofía inicia un chat grupal con un conjunto de médicos y otras enfermeras que trabajarán con el paciente para coordinar la atención e inicia una tríada de emergencias.  Las enfermeras y los médicos se comunican y colaboran con el plan de atención al paciente durante el proceso de coordinación de la asistencia.  Los mensajes importantes y urgentes se envían a través de las conversaciones de chat grupales y uno a uno. Sofía usa la función de confirmaciones de lectura para determinar si los mensajes enviados solicitando soporte técnico se entregan y leen los médicos o enfermeras específicos. Los resultados del paciente de Jakob son casi óptimos y se va a casa antes porque su equipo de salud se comunica sin problemas.

## <a name="send-urgent-messages-using-priority-notifications"></a>Enviar mensajes urgentes con notificaciones de prioridad

Un usuario puede marcar un mensaje como *urgente al* enviar mensajes de chat a otros usuarios. Esta característica ayuda a que el personal hospitalario se alerte cuando un incidente crítico requiere su atención. A  diferencia de los mensajes importantes normales, [](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) las notificaciones de prioridad notifican a los usuarios cada dos minutos durante un máximo de 20 minutos o hasta que el destinatario toma el mensaje y lo lee, lo que aumenta la probabilidad de que el mensaje se ate parte de su tiempo.

Un administrador puede habilitar o deshabilitar la posibilidad de que los usuarios asignados a esta directiva envíen notificaciones de prioridad. Esta característica está predeterminada. Es posible que el destinatario del mensaje de prioridad no tenga la misma directiva de mensajería y no tenga una opción para deshabilitar la recepción de mensajes de prioridad. Para las aplicaciones sanitarias, recomendamos habilitar la característica para al menos algunos usuarios, pero tendrá que determinar cuáles.

*Ejemplo de uso:* Sofía Krause lee a un paciente de alto riesgo, Jakob Jakob Jakob. Esa persona, que es médico, es el médico principal de este paciente.  Ñam envía un mensaje a Arrais con una notificación de prioridad en la que se le pide ayuda inmediata con el tratamiento de Jakob.  El teléfono de Quebrada recibe el mensaje, pero Estaña no siente la vibración del teléfono y no responde. Teams vuelve a notificárselo a Adobe y seguirá notificando de forma persistente hasta que lea el mensaje. Si las confirmaciones de lectura también están habilitadas, Sofía puede ser consciente de que el mensaje lo leyó Ara, incluso antes de que Esaia decida cómo responder.

## <a name="related-topics"></a>Temas relacionados

- [Administrar directivas de mensajería de Teams](../../messaging-policies-in-teams.md)
- [Introducción a Teams para organizaciones sanitarias](teams-in-hc.md)
