---
title: Plantilla de reunión de cita virtual en Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
searchScope:
- Microsoft Teams
audience: admin
description: Obtenga información sobre cómo administrar la plantilla de reunión de citas virtuales para los usuarios de Teams de su organización.
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 459845115d8a705673f21b5e8a57dadac59841f6
ms.sourcegitcommit: f8da8f613fc3902d2607e322ad9dfbdeb8838c4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2022
ms.locfileid: "69624926"
---
# <a name="virtual-appointment-meeting-template-in-microsoft-teams"></a>Plantilla de reunión de cita virtual en Microsoft Teams

## <a name="overview"></a>Información general

La plantilla Cita virtual es una plantilla de reunión predeterminada en Microsoft Teams que los usuarios pueden usar para programar citas virtuales con clientes, clientes y otras personas de fuera de su organización. Por ejemplo, úselo para programar y realizar entrevistas, sesiones de mentoría, consultas financieras, experiencias de compras virtuales y mucho más.

La plantilla le permite especificar valores para la configuración de reuniones que controlan normalmente los organizadores de la reunión. Le ofrece la flexibilidad de aplicar la configuración predeterminada y aplicar la configuración. Puede elegir bloquear la configuración para que los organizadores de la reunión no puedan cambiarla cuando usen la plantilla.

Con esta plantilla, puede habilitar una experiencia coherente en toda la organización para citas virtuales programadas en Teams y ayudar a aplicar los requisitos de cumplimiento.

En este artículo se proporciona información general sobre cómo ver y administrar la plantilla de reunión de cita virtual en el Centro de administración de Teams.

## <a name="view-or-change-virtual-appointment-meeting-template-settings"></a>Ver o cambiar la configuración de la plantilla de reunión de cita virtual

1. En el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Plantillas de reunión de** **reuniones** > .
1. Elija **Cita virtual** y, a continuación, seleccione **Editar**.
1. Para realizar cambios, seleccione una opción y, a continuación, configure las opciones que desee. Para cada opción, puede definir las siguientes opciones:
    - **Valor predeterminado**: el valor que se aplica a la cita virtual cuando se usa la plantilla.
    - **Visibilidad**: Elija **Ocultar** o **Mostrar** para especificar si la opción está visible para los organizadores de la reunión en las opciones de reunión de Teams.
    - **Estado de bloqueo**: para evitar que los organizadores de la reunión cambien el valor que estableció, elija **Bloquear**. Para permitir que los organizadores de la reunión cambien el valor establecido, elija **Desbloquear**.
1. Revise los cambios y, después, elija **Guardar**.

## <a name="manage-the-virtual-appointment-meeting-template"></a>Administrar la plantilla de reunión de cita virtual

Las directivas de plantillas de reunión se usan en el Centro de administración de Teams para controlar qué plantillas de reunión están disponibles para los usuarios de su organización. De forma predeterminada, la directiva global permite a los usuarios ver y usar todas las plantillas de reunión, incluida la plantilla Cita virtual y las plantillas personalizadas que haya creado.

Si quiere que la plantilla Cita virtual esté disponible para usuarios o grupos específicos de usuarios de su organización, puede crear una directiva de plantilla de reunión personalizada y asignarla a esos usuarios o grupos.

Para obtener más información, consulte [Administrar plantillas de reunión en Teams](manage-meeting-templates.md).

## <a name="user-experience"></a>Experiencia de usuario

Cuando los usuarios de su organización usan la plantilla de reunión para programar una cita virtual, las personas de fuera de su organización (invitados externos) reciben una invitación de reunión personalizada que incluye un botón **Unirse a una cita como invitado** y otros detalles de la cita. Pueden usar este botón para unirse fácilmente desde cualquier dispositivo sin tener que descargar e instalar Teams.

Tenga en cuenta que es posible que algunas opciones de reunión de Teams no se apliquen a invitados externos ni a ninguna persona que se una con el botón **Unirse a la cita como invitado** . Las siguientes opciones de reunión son compatibles con la unión de invitados:

- **Quién puede omitir la sala de espera**: la configuración **Todos** permite a los invitados externos omitir la sala de espera.
- **Elegir organizadores colaboradores**
- **Grabar automáticamente**
- **Permitir el chat** de la reunión: establezca esta opción en **Deshabilitado** si desea evitar el chat de la reunión antes, durante y después de la reunión.

Personas dentro de su organización reciben una invitación de reunión y la cita aparece en su calendario de Teams y Outlook, donde pueden unirse fácilmente como en cualquier otra reunión de Teams. Todas las opciones de reunión de Teams se aplican a los asistentes que se unen mediante el vínculo de la reunión de Teams en la invitación a la reunión o desde el calendario de Teams o Outlook.

Para obtener más información sobre cómo usar la plantilla de reunión de cita virtual y la experiencia del usuario, vea [Usar una plantilla de reunión de Teams para crear una cita virtual](https://support.microsoft.com/office/6a9e8cbb-c0ed-4598-851e-3b1750a4a747).

## <a name="related-articles"></a>Artículos relacionados

- [Información general sobre las plantillas de reunión personalizadas en Teams](custom-meeting-templates-overview.md)
