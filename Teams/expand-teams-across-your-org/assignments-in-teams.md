---
title: Tareas de Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Aprenda a administrar tareas en el centro de administración de Microsoft Teams en Teams para el ámbito educativo.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78ce963b8d675aa6d5c851c1081472559d24c3a3
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256455"
---
# <a name="assignments-in-teams-for-education"></a>Tareas en Teams para educación

Las asignaciones son tareas o unidades de trabajo asignadas a un estudiante o miembro del equipo en una clase como parte de su estudio. Puede crear tareas dentro de la clase Teams.

[Más información sobre tareas](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Tareas en el centro de administración de Microsoft Teams

Con la configuración de administrador del centro de administración de Microsoft Teams, puede activar o desactivar las siguientes características para que los alumnos y los profesores de la organización puedan estar disponibles. A continuación se muestran los parámetros relacionados con las asignaciones:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Resumen de correo electrónico de tutor semanal

Los mensajes de correo electrónico de tutor son mensajes semanales enviados a padres o tutores. Los mensajes de correo electrónico contendrán información sobre tareas de la semana anterior y de la semana que viene, y se enviarán durante el fin de semana. Los administradores deben actualizar los mensajes de correo electrónico con la característica School Data Sync.

Esta opción está desactivada de forma predeterminada.

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode es una plataforma de codificación basada en bloques que hace que la ciencia de su equipo cobre vida por todos los alumnos. 

MakeCode es un producto de Microsoft que está sujeto a las [condiciones de uso](https://go.microsoft.com/fwlink/?LinkID=206977) y a las políticas de [privacidad](https://go.microsoft.com/fwlink/?LinkId=521839) de Microsoft.

Esta opción está desactivada de forma predeterminada. Para habilitar las tareas de MakeCode en Teams, en el **centro de administración de Teams**, **vaya a la**sección **tareas** y active la opción MakeCode. Haga clic en **Guardar** y deje que transcurran hasta 24 horas para que esta configuración surta efecto.

Para obtener más información sobre cómo funciona esta característica, vea esta [demostración en vídeo](https://makecode.com/blog/teams/teams-assignments).

[Más información sobre MakeCode](https://aka.ms/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin es un servicio de detección de plagiarism. Este es un producto o servicio de terceros sujeto a sus propios términos y política de privacidad. Usted es responsable de su uso de productos y servicios de terceros.

Esta opción está desactivada de forma predeterminada.

Para habilitar correctamente Turnitin para su organización, necesitará ya una suscripción a Turnitin. Tendrá que introducir la siguiente información adicional, que puede encontrarse en su consola de administración de Turnitin:

  * _TurnitinApiKey_: se trata de un GUID de carácter 32 que se encuentra en la consola de administración en integraciones.
  * _TurnitinApiUrl_: esta es la dirección URL https de la consola de administración de Turnitin.

Estas son algunas instrucciones para ayudarle a obtener esta información.

La TurnitinApiUrl es la dirección de host de su consola de administración.
Ejemplo. `https://your-tenant-name.turnitin.com`

La consola de administración es donde puede crear una integración y una clave de API asociada con la integración.

Seleccione **integraciones** en el menú lateral y, a continuación, seleccione **Agregar integración** y asigne un nombre a la integración.
![Captura de pantalla que muestra cómo agregar una nueva integración](./educationImages/Assignments_mopo_turnitin2.png)

Después de seguir las indicaciones, se le dará la TurnitinApiKey. Copie la clave de API y péguela en el centro de administración de Microsoft Teams.  Esta es la única vez que puedes ver la tecla.
![Captura de pantalla que muestra la copia de la clave API](./educationImages/Assignments_mopo_turnitin3.png)

Después de hacer clic en el botón **Guardar** en el centro de administración de esta configuración, espere hasta 24 horas para que esta configuración surta efecto.

¿Está listo para empezar a usar la integración de Turnitin en Teams? Suscribirse al [programa de acceso anticipado](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).
