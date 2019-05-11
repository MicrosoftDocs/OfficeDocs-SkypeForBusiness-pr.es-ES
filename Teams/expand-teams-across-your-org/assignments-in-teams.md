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
description: Obtenga información sobre cómo administrar las asignaciones en el centro de administración de Microsoft Teams en los equipos para el ámbito educativo.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 263b9dda6929bd6956df803a33764634808cddf3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914026"
---
# <a name="assignments-in-teams-for-education"></a>Tareas en Teams para educación

Las asignaciones son tareas o unidades de trabajo asignados a un miembro de estudiantes o equipo en una clase como parte de sus estudios. Puede crear asignaciones dentro de la clase de los equipos.

[Encontrará más información acerca de las asignaciones](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Asignaciones en el centro de administración de Microsoft Teams

Con la administración de configuración en el centro de administración de Microsoft Teams puede activar las siguientes características o desactivar para que esté disponible para los alumnos y profesores dentro de la organización. Los siguientes son la configuración relacionada con las asignaciones:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Resumen de correo electrónico semanal guardián
El guardián los correos electrónicos son semanales correos electrónicos enviados a los alumnos los padres o tutores. Los mensajes de correo electrónico va a contener información acerca de las asignaciones de la semana anterior y para la próxima semana y se enviarán a través de los fines de semana. Los mensajes de correo electrónico necesitan actualizarse por los administradores de uso de la característica de sincronización de datos de School.

Esta opción está desactivada de forma predeterminada.

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
MakeCode es una plataforma de codificación basada en bloques que aporta informática a la vida de todos los alumnos. 

Esto es un producto de terceros o el servicio que está sujeto a sus propios términos y la directiva de privacidad. Usted es responsable de su uso de los servicios y productos de terceros.

Esta opción está desactivada de forma predeterminada.

[Encontrará más información acerca de MakeCode](https://www.microsoft.com/${locale}/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin es un servicio de detección de plagio. Esto es un producto de terceros o el servicio que está sujeto a sus propios términos y la directiva de privacidad. Usted es responsable de su uso de los servicios y productos de terceros.

Esta opción está desactivada de forma predeterminada.

Con el fin de habilitar correctamente Turnitin para su organización, necesita ya tiene una suscripción de Turnitin. Necesitará la siguiente información adicional, que se encuentra en la consola de administración de Turnitin de entrada:

  * _TurnitinApiKey_: se trata de un GUID de 32 caracteres que se encuentran en la consola de administración en aplicaciones integradas.
  * _TurnitinApiUrl_: esta es la dirección URL de HTTPS de la consola de administración de Turnitin.

A continuación presentamos algunas instrucciones que le ayudarán a obtener esta información.

El TurnitinApiUrl es la dirección de host de la consola de administración.
![Buscar el TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin1.png)

Vaya a la ficha aplicaciones integradas y agregue una integración.
![Buscar el TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin2.png)

El TurnitinApiKey se le dará a usted después de seguir las instrucciones. Copie esta clave y péguelo en el centro de administración de Microsoft Teams. 
![Buscar el TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin3.png)

[Encontrará más información acerca de la integración entre Turnitin y Microsoft Teams](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)

[Encontrará más información acerca de Turnitin](https://www.turnitin.com/)
