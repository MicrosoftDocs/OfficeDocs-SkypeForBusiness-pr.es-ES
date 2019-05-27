---
title: Tareas de Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1keywords: ms.teamsadmincenter.assignments.overview
description: Aprenda a administrar tareas en el centro de administración de Microsoft Teams en Teams para el ámbito educativo.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 188f4398136c2939ad2a84d75ab27942a5a4593b
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433434"
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
MakeCode es una plataforma de codificación basada en bloques que hace que la ciencia de su equipo cobre vida por todos los alumnos. 

Este es un producto o servicio de terceros sujeto a sus propios términos y política de privacidad. Usted es responsable de su uso de productos y servicios de terceros.

Esta opción está desactivada de forma predeterminada.

[Más información sobre MakeCode](https://www.microsoft.com/${locale}/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin es un servicio de detección de plagiarism. Este es un producto o servicio de terceros sujeto a sus propios términos y política de privacidad. Usted es responsable de su uso de productos y servicios de terceros.

Esta opción está desactivada de forma predeterminada.

Para habilitar correctamente Turnitin para su organización, necesitará ya una suscripción a Turnitin. Tendrá que introducir la siguiente información adicional, que puede encontrarse en su consola de administración de Turnitin:

  * _TurnitinApiKey_: se trata de un GUID de carácter 32 que se encuentra en la consola de administración en integraciones.
  * _TurnitinApiUrl_: esta es la dirección URL https de la consola de administración de Turnitin.

Estas son algunas instrucciones para ayudarle a obtener esta información.

La TurnitinApiUrl es la dirección de host de su consola de administración.
![Captura de pantalla que muestra la dirección de host](./educationImages/Assignments_mopo_turnitin1.png)

Vaya a la ficha integraciones y agregue una integración.
![Captura de pantalla que muestra cómo agregar una nueva integración](./educationImages/Assignments_mopo_turnitin2.png)

Después de seguir las indicaciones, se le dará la TurnitinApiKey. Copie esta clave y péguela en el centro de administración de Microsoft Teams. 
![Captura de pantalla que muestra la copia de la clave API](./educationImages/Assignments_mopo_turnitin3.png)

[Más información sobre la integración entre Turnitin y Microsoft Teams](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)

[Más información sobre Turnitin](https://www.turnitin.com/)
