---
title: Administrar etiquetas en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a administrar cómo se usan las etiquetas en su organización en Microsoft Teams.
ms.openlocfilehash: 718a2401aa8e015a6dec2b6a4c6116a567aaf82d
ms.sourcegitcommit: 20f881285edf699ebf36320664166c95ccd6df35
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919062"
---
# <a name="manage-tags-in-microsoft-teams"></a>Administrar etiquetas en Microsoft Teams

> [!NOTE]
> Una de las características descritas en este artículo, **etiquetado por turnos** , todavía no se ha soltado. Se ha anunciado y pronto estará disponible. Si es un administrador, puede averiguar cuándo se publicará esta característica en el centro de mensajes (en el centro de [Administración de Microsoft 365](https://portal.office.com/adminportal/home)). Para estar al día de las próximas características de Teams, consulte la [hoja de ruta de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="overview"></a>Información general

Las etiquetas de Microsoft Teams permiten a los usuarios conectarse de forma rápida y sencilla a un subconjunto de personas de un equipo. Puede crear y asignar etiquetas personalizadas para clasificar personas en función de los atributos, como el rol, el proyecto, el conocimiento o la ubicación. O bien, las etiquetas se pueden asignar automáticamente a las personas en función de su programación y la información de Mayús en la [aplicación turnos](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (próximamente). Después de agregar una etiqueta a uno o varios miembros del equipo, puede usarla en @mentions por cualquier persona del equipo en una publicación de canal o para iniciar una conversación con solo las personas que tienen asignada esa etiqueta.

Como se mencionó anteriormente, hay dos tipos de etiquetas en Teams.

- **Etiquetas personalizadas** : los propietarios del equipo y los miembros del equipo (si la característica está habilitada) pueden crear y asignar etiquetas de forma manual a las personas. Por ejemplo, una etiqueta "diseñador" o "Radiologist" llegará a esos conjuntos de personas en un equipo sin necesidad de escribir sus nombres.
- **Etiquetado por turnos** (próximamente): con esta característica, a las personas se les asignan automáticamente las etiquetas que coinciden con su programación y el nombre del grupo de turnos en la [aplicación turnos](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) de Teams. Por ejemplo, la etiqueta "EngineerOnCall" llega a todos los ingenieros programados en turnos para trabajar en el momento en que se usa la etiqueta en una publicación de chat o canal. Con el etiquetado por turnos, Teams elimina las conjeturas de conocer el nombre del personal que está en turno cuando los usuarios necesitan retransmitir información rápidamente. El etiquetado por turno también se puede respaldar por sistemas de administración de personal principales, como JDA, Kronos y AMiON, al integrarlos con turnos en Teams. Para obtener más información sobre cómo configurar esta característica, consulte [Configurar etiquetas por turno](#set-up-tagging-by-shift-coming-soon).

> [!NOTE]
> Las etiquetas aún no son compatibles con los canales privados. Las etiquetas aún no están disponibles en las organizaciones de la nube de la comunidad de administración de Estados Unidos (GCC), GCC High o Department of Defense (DoD). 

## <a name="how-tags-work"></a>Cómo funcionan las etiquetas

Se puede Agregar una etiqueta de forma manual o asignarla automáticamente a una persona en un equipo específico. Puede usarse en @mentions en la línea **para** de un chat o en una publicación en cualquier canal estándar del equipo. Estos son algunos ejemplos de cómo se pueden usar etiquetas en Teams:

- El administrador de la tienda publica un anuncio en un canal para notificar a todos los cajeros.
- Un administrador de un hospital envía un mensaje a todos los radiologists de un canal.
- Un administrador de marketing inicia una conversación grupal con todos los diseñadores.
- Un enfermera envía un mensaje a todas las llamadas de cardiologists. (próximamente)
- Un ingeniero de sistemas publica un anuncio en un canal para notificar a todos los ingenieros de campo en turno. (próximamente)

Cuando se @mentioned una etiqueta en una conversación de canales, se notificarán los miembros del equipo asociados con la etiqueta, como cualquier otro @mention.

## <a name="manage-custom-tags-for-your-organization"></a>Administrar etiquetas personalizadas para su organización

Como administrador, puede controlar cómo se usan las etiquetas en la organización en el centro de administración de Microsoft Teams. Por el momento, no puede usar PowerShell para administrar etiquetas.

![Captura de pantalla de la configuración de etiquetado en el centro de administración de Microsoft Teams](media/manage-tags-admin-settings.png)

Un equipo puede tener hasta 100 etiquetas, hasta 100 miembros del equipo pueden asignarse a una etiqueta y se pueden asignar hasta 25 etiquetas a un solo usuario. 

### <a name="set-who-can-add-custom-tags"></a>Establecer quién puede agregar etiquetas personalizadas

De forma predeterminada, los propietarios del equipo pueden agregar etiquetas personalizadas. Puede cambiar esta configuración para permitir que los propietarios del equipo y los miembros del equipo puedan crear, editar, eliminar y administrar etiquetas o puede desactivar las etiquetas para su organización.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en configuración de la **organización** de  >  **Teams**.
2. En **etiquetado** , junto a **etiquetas son gestionadas por** , seleccione una de las siguientes opciones:

    - **Miembros y propietarios del equipo** : permita que los propietarios y miembros del equipo administren etiquetas.
    - **Propietarios de equipo** : permita que los propietarios de equipo administren etiquetas.
    - **Desactivado** : desactivar etiquetas.

### <a name="configure-custom-tags-settings"></a>Configurar las etiquetas personalizadas

Puede configurar las siguientes opciones de etiquetas para controlar cómo se usan las etiquetas personalizadas en toda la organización.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en configuración de la **organización** de  >  **Teams**.
2. En **etiquetado** , defina lo siguiente según las necesidades de su organización.

    - **Permitir que los propietarios del equipo invaliden quién puede administrar las etiquetas** : cuando se activa esta configuración, los propietarios del equipo pueden establecer si los miembros del equipo pueden crear y administrar etiquetas dentro de un equipo y el valor de las **etiquetas se administra por** configuración es el valor predeterminado de cada equipo. Si desactiva esta configuración, las **etiquetas se administran mediante** la configuración no se puede cambiar por equipo.
    - **Sugerencias de etiquetas predeterminadas** : Use esta opción para agregar un conjunto de etiquetas predeterminadas. Puede Agregar hasta 25 etiquetas y cada etiqueta puede contener un máximo de 25 caracteres. Los miembros y propietarios del equipo (si la característica está habilitada) pueden usar estas sugerencias, agregarlas o crear un nuevo conjunto de etiquetas.
    - **Permitir la creación de etiquetas personalizadas** : Active esta configuración para permitir que los usuarios agreguen etiquetas distintas de las sugerencias predeterminadas que haya establecido. Si esta opción está desactivada, los usuarios solo podrán usar las etiquetas predeterminadas sugeridas. Si desactiva esta opción, asegúrese de agregar una o más etiquetas predeterminadas.

## <a name="manage-custom-tags-settings-for-a-team"></a>Administrar la configuración de etiquetas personalizadas para un equipo

Si activó la opción **permitir que los propietarios del equipo invaliden quién puede administrar las etiquetas** en el centro de administración de Microsoft Teams, los propietarios del equipo pueden establecer si los miembros pueden agregar etiquetas en el nivel de equipo. Para ello, en la pestaña **configuración** de un equipo, vaya a **etiquetas** y, después, elija quién puede agregar etiquetas.

![Captura de pantalla de la configuración de etiquetas en el nivel de equipo](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>Usar etiquetas

A continuación se explica cómo agregar etiquetas personalizadas y cómo configurar el etiquetado mediante Mayús (si usa la aplicación de turnos en Teams). Para obtener más información, consulte [usar las etiquetas en Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

### <a name="create-and-assign-custom-tags"></a>Crear y asignar etiquetas personalizadas

Para crear y asignar etiquetas personalizadas, seleccione **Teams** en el lado izquierdo de la aplicación y, a continuación, busque su equipo en la lista. Seleccione **̇ ̇ ̇ más opciones** y, a continuación, elija **administrar etiquetas**. Aquí puede crear etiquetas y asignarlas a personas de su equipo.

![Captura de pantalla de cómo aplicar etiquetas en el cliente de Teams ](media/manage-tags-teams.png)

Para eliminar una etiqueta, seleccione **̇ ̇ ̇ más opciones** junto a la etiqueta y, a continuación, seleccione **Eliminar etiqueta**.

### <a name="set-up-tagging-by-shift-coming-soon"></a>Configurar el etiquetado por turno (próximamente)

1. En Teams, vaya a la [aplicación turnos](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).
2. Crear [grupos de turnos](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) y nombrarlos después de un atributo como un rol. Por ejemplo, EngineerOnCall. El nombre del grupo de turnos será el nombre de la etiqueta.
3. Para [rellenar una programación](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) , asigne turnos a los miembros de su equipo. Cuando haya terminado, en la esquina superior derecha de la aplicación turnos, seleccione **compartir con el equipo**.
4. Espere 15 minutos para que los turnos programados rellenen el servicio de etiquetado.
5. Use la etiqueta en cualquier lugar en el que use etiquetas en Teams.

El etiquetado por turno permite que los usuarios puedan comunicarse con las personas que se desplazan en tiempo real. Las notificaciones se envían solo a las personas que están en turno en el momento en que se usa una etiqueta para iniciar un chat o en una publicación de canal.

## <a name="related-topics"></a>Temas relacionados

[Usar etiquetas en Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Administrar la aplicación Turnos para su organización en Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Desplaza la documentación de ayuda](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
