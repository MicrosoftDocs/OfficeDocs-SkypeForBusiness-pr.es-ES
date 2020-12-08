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
ms.openlocfilehash: 64be355da30feb3c629569f583897353c21cfa37
ms.sourcegitcommit: 481d18b76304adfa340b5f1b2f1b7965e9ff4993
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2020
ms.locfileid: "49586623"
---
# <a name="assignments-in-teams-for-education"></a>Tareas en Teams para educación

Las características asignaciones y calificaciones de Teams para el ámbito educativo permiten a los educadores asignar tareas, trabajos o cuestionarios a sus alumnos. Los educadores pueden administrar escalas temporales de asignaciones, instrucciones, agregar recursos para entregar, calificar con indicaciones y mucho más. También pueden realizar un seguimiento de la clase y del curso de un estudiante individual en la pestaña calificaciones.

[Obtenga más información sobre tareas y calificaciones en Teams para el ámbito educativo](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> Para obtener más información acerca de las tareas de Teams en diferentes plataformas, consulte [características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Integraciones integraciones en el centro de administración de Microsoft Teams

Con la configuración de administrador del centro de administración de Microsoft Teams, puede activar o desactivar las características para educadores de su organización y sus alumnos. A continuación se muestran los parámetros relacionados con las asignaciones:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Resumen de correo electrónico de tutor semanal


Los mensajes de correo electrónico de tutor se envían cada fin de semana a padres o tutores. El correo electrónico contiene información sobre tareas de la semana anterior y de la semana que viene. La sincronización de padres y tutores puede configurarse con [School Data Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync).

1. Importar información de contacto principal a través de la sincronización de padres y tutores en SDS. Para obtener instrucciones sobre cómo habilitar la sincronización de padres y tutores, consulta [Habilitar la sincronización de padres y tutores](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. Active la configuración del tutor en el centro de administración de Microsoft Teams, ya que la configuración está desactivada de forma predeterminada. Esto permitirá que los profesores envíen un resumen semanal.

   > [!NOTE]
   > Los profesores pueden optar por no recibir la síntesis desmarcando la configuración dentro de su equipo de clase personal (**configuración de asignación > correos electrónicos de padres o tutores**).

Para comprobar que los padres recibirán el correo electrónico, los tres elementos siguientes deben ser verdaderos:

 - Dirección de correo electrónico adjunta al perfil de estudiante en SDS y etiquetado como _padre_ o _tutor_. Para obtener más información, consulta el [formato de archivo de sincronización de padres y tutores](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).

 - Los alumnos pertenecen al menos a una clase en la que el profesor no ha deshabilitado el correo electrónico en la [configuración de asignaciones](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).

 - Los mensajes de correo electrónico contendrán información sobre tareas con una fecha de vencimiento de la semana anterior o de la semana próxima.

La configuración predeterminada para esta característica es **deshabilitada**.


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode es una plataforma de codificación basada en bloques que hace que la ciencia de su equipo cobre vida por todos los alumnos. 

MakeCode es un producto de Microsoft que está sujeto a las [condiciones de uso](https://go.microsoft.com/fwlink/?LinkID=206977) y a las políticas de [privacidad](https://go.microsoft.com/fwlink/?LinkId=521839) de Microsoft.

La configuración predeterminada para esta característica es **deshabilitada**.

Para habilitar las tareas de MakeCode en Teams, vaya al **centro de administración de Teams**, vaya a la sección **tareas** y active la opción **de alternancia de** MakeCode. Haga clic en **Guardar**. Deje que haya unas horas para que esta configuración se aplique.

Para obtener más información sobre cómo funciona esta característica, vea esta [demostración en vídeo](https://makecode.com/blog/teams/teams-assignments).

[Más información sobre MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) es un servicio de integridad académica. Este es un producto o servicio de terceros sujeto a sus propios términos y política de privacidad. Usted es responsable de su uso de todos los productos y servicios de terceros.

El valor predeterminado de esta característica es: **deshabilitado**..

Para habilitar Turnitin para su organización, necesitará una suscripción de Turnitin. Después, puede escribir la siguiente información, que puede encontrarse en su consola de administración de Turnitin:

  * **TurnitinApiKey**: se trata de un GUID de carácter 32 que se encuentra en la consola de administración en integraciones.
  * **TurnitinApiUrl**: esta es la dirección URL https de la consola de administración de Turnitin.

Estas son algunas instrucciones para ayudarle a obtener esta información.

La **TurnitinApiUrl** es la dirección de host de su consola de administración.
Ejemplo `https://your-tenant-name.turnitin.com`

La consola de administración es donde puede crear una integración y una clave de API asociada con la integración.

Seleccione **integraciones** en el menú lateral y, a continuación, seleccione **Agregar integración** y asigne un nombre a la integración.

![Captura de pantalla que muestra cómo agregar una nueva integración](./educationImages/Assignments_mopo_turnitin2.png)

Después de seguir las indicaciones, se le dará la **TurnitinApiKey** . Copie la clave de API y péguela en el centro de administración de Microsoft Teams.  Esta es la única vez que puedes ver la tecla.

![Captura de pantalla que muestra la copia de la clave API](./educationImages/Assignments_mopo_turnitin3.png)

Después de hacer clic en el botón **Guardar** en el centro de administración para esta configuración, deje que se apliquen estas horas para la configuración.

