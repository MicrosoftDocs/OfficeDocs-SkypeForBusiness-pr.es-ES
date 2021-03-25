---
title: Tareas de Teams
author: cichur
ms.author: v-cichur
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
description: Obtenga información sobre cómo administrar tareas en el Centro de administración de Microsoft Teams en Teams para el sector educativo.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 410f5d32dd8af4775639a080725cd5680b6a70c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121378"
---
# <a name="assignments-in-teams-for-education"></a>Tareas en Teams para educación

Las características Tareas y calificaciones de Teams para el sector educativo permiten a los profesores asignar tareas, trabajos o cuestionarios a sus alumnos. Los formadores pueden administrar las escalas de tiempo de las tareas, las instrucciones, agregar recursos para entregar, calificar con las indicaciones y mucho más. También pueden realizar un seguimiento del progreso de clase y de alumno individual en la pestaña Calificaciones.

[Obtenga más información sobre tareas y calificaciones en Teams para el sector educativo.](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> Para obtener más información sobre las tareas de Teams en diferentes plataformas, vea [Características de Teams por plataforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Integraciones de tareas en el Centro de administración de Microsoft Teams

Con la configuración de administrador del Centro de administración de Microsoft Teams, puede activar o desactivar las características para los profesores de su organización y sus alumnos. A continuación se muestra la configuración relacionada con Tareas:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Resumen de correo electrónico de tutor semanal


Los correos electrónicos de los tutores se envían cada fin de semana a los padres o tutores. El correo electrónico contiene información sobre las tareas de la semana anterior y de la semana siguiente. La sincronización de padres y tutores se puede configurar con [School Data Sync.](/schooldatasync/parent-contact-sync)

1. Importar la información de contacto de los padres a través de La sincronización de padres y tutores en SDS. Para obtener instrucciones sobre cómo habilitar la sincronización de padres y tutores, vea Habilitar la sincronización de padres [y tutores.](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)

2. Active la configuración de Tutor en el Centro de administración de Microsoft Teams, ya que la configuración está desactivada de forma predeterminada. Esto permitirá a los profesores enviar un resumen semanal.

   > [!NOTE]
   > Los profesores pueden optar por no participar en el resumen anulando la selección de la configuración dentro de su propio equipo personal de clase (Configuración de tareas > correo electrónico de padres **y tutores).**

Para comprobar que los padres recibirán el correo electrónico, los tres elementos siguientes deben ser verdaderos:

 - Dirección de correo electrónico adjunta al perfil de alumno en SDS y etiquetada como _Padres_ o _Tutores._ Para obtener más información, vea [Formato de archivo de sincronización de padres y tutores.](/schooldatasync/parent-contact-sync-file-format)

 - Los alumnos pertenecen al menos a una clase en la que el profesor no deshabilita el correo electrónico en la configuración [de la tarea.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)

 - Los correos electrónicos contendrán información sobre las tareas que tuvieron una fecha de vencimiento en la semana anterior o en la semana siguiente.

La configuración predeterminada para esta característica es - **Desactivado**.


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode es una plataforma de codificación basada en bloques que da vida a la informática para todos los alumnos. 

MakeCode es un producto de Microsoft que está sujeto a las condiciones de uso [y](https://go.microsoft.com/fwlink/?LinkID=206977) las directivas de privacidad [de](https://go.microsoft.com/fwlink/?LinkId=521839) Microsoft.

La configuración predeterminada para esta característica es - **Desactivado**.

Para habilitar las asignaciones de MakeCode en Teams,  vaya al Centro de administración de **Teams,** vaya a la sección Tareas y active la opción de alternancia MakeCode en **Activar**. Haga clic en **Guardar**. Espere unas horas para que esta configuración suba a efecto.

Para obtener más información sobre cómo funciona esta característica, vea esta [demostración en vídeo.](https://makecode.com/blog/teams/teams-assignments)

[Más información sobre MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin es](https://www.turnitin.com/) un servicio de integridad académica. Este es un producto o servicio de terceros que está sujeto a sus propios términos y política de privacidad. Usted es responsable del uso de los productos y servicios de terceros.

La configuración predeterminada de esta característica es - **Desactivado**..

Para habilitar Turnitin para su organización, necesitará una suscripción a Turnitin. A continuación, puede introducir la siguiente información, que se puede encontrar en la consola de administración de Turnitin:

  * **TurnitinApiKey:** se trata de un GUID de 32 caracteres que se encuentra en la consola de administración en Integraciones.
  * **TurnitinApiUrl:** esta es la dirección URL HTTPS de la consola de administración de Turnitin.

Estas son algunas instrucciones para ayudarle a obtener esta información.

**TurnitinApiUrl** es la dirección de host de la consola de administración.
Ejemplo: `https://your-tenant-name.turnitin.com`

La consola de administración es donde puede crear una integración y una clave de API asociada a la integración.

Seleccione **Integraciones en** el menú lateral, seleccione **Agregar integración** y asigne un nombre a la integración.

![Captura de pantalla que muestra cómo agregar una nueva integración](./educationImages/Assignments_mopo_turnitin2.png)

El **TurnitinApiKey** se le dará después de seguir las indicaciones. Copie la clave de API y péguela en el Centro de administración de Microsoft Teams.  Esta es la única vez que puede ver la clave.

![Captura de pantalla que muestra cómo copiar la clave de API](./educationImages/Assignments_mopo_turnitin3.png)

Al hacer clic en **el botón** Guardar del Centro de administración para esta configuración, espere unas horas para que esta configuración suba a efecto.