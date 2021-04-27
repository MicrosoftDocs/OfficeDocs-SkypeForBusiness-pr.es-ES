---
title: Administrar etiquetas en Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Obtenga información sobre cómo se usan las etiquetas en su organización en Microsoft Teams.
ms.openlocfilehash: c63817f5b3ee9c736311982b54dbc9a220564229
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030110"
---
# <a name="manage-tags-in-microsoft-teams"></a>Administrar etiquetas en Microsoft Teams

## <a name="overview"></a>Información general

Las etiquetas de Microsoft Teams permiten a los usuarios conectarse de forma rápida y sencilla con un subconjunto de personas de un equipo. Puede crear y asignar etiquetas personalizadas para clasificar a las personas en función de atributos, como rol, proyecto, aptitudes o ubicación. O bien, las etiquetas se pueden asignar automáticamente a las personas en función de su programación y la información de turnos en la aplicación [Turnos](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (próximamente). Después de agregar una etiqueta a uno o varios miembros del equipo, puede ser usada en @mentions por cualquier persona del equipo en una publicación de canal o para iniciar una conversación solo con las personas a las que se les haya asignado esa etiqueta.

Como se mencionó anteriormente, hay dos tipos de etiquetas en Teams.

- **Etiquetas personalizadas:** los propietarios del equipo y los miembros del equipo (si la característica está habilitada para ellos) pueden crear y asignar etiquetas manualmente a personas. Por ejemplo, una etiqueta "Diseñador" o "Radiólogo" llegará a esos conjuntos de personas de un equipo sin tener que escribir sus nombres.
- **Etiquetado por turnos:** con esta característica, a los usuarios se les asignan automáticamente etiquetas que coinciden con su nombre de grupo de programación y turnos en la aplicación [Turnos](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) de Teams. Por ejemplo, la etiqueta "EngineerOnCall" llega a todos los ingenieros que están programados en Turnos para trabajar en el momento en que se usa la etiqueta en una publicación de chat o canal. Con el etiquetado por turnos, Teams quita las conjeturas de conocer el nombre del personal en turnos cuando los usuarios necesitan retransmitir información rápidamente. El etiquetado por turnos también se puede realizar con el respaldo de los principales sistemas de administración de la fuerza laboral como JDA, Kronos y AMiON integrándolos con Turnos en Teams. Para obtener más información sobre cómo configurar esta característica, vea [Configurar el etiquetado por turnos.](#set-up-tagging-by-shift)

> [!NOTE]
> Las etiquetas aún no son compatibles con los canales privados. Las etiquetas no están disponibles en organizaciones del GCC High o del Departamento de Defensa (DoD). 

## <a name="how-tags-work"></a>Cómo funcionan las etiquetas

Una etiqueta se puede agregar manualmente o asignar automáticamente a una persona de un equipo específico. A continuación, se puede usar @mentions en la línea **Para** de un chat o en una publicación en cualquier canal estándar del equipo. Estos son algunos ejemplos de cómo se pueden usar etiquetas en Teams:

- Un administrador de tienda publica un anuncio en un canal para notificar a todos los cajeros.
- Un administrador del hospital envía un mensaje a todos los radiólogos de un canal.
- Un administrador de marketing inicia un chat grupal con todos los diseñadores.
- Una enfermera envía un mensaje a todos los cardiólogos de llamadas. (próximamente)
- Un ingeniero de sistema publica un anuncio en un canal para notificar a todos los ingenieros de campo en turno. (próximamente)

Cuando una etiqueta se @mentioned en una conversación de canal, los miembros del equipo asociados con la etiqueta recibirán una notificación, igual que cualquier otra @mention.

## <a name="manage-custom-tags-for-your-organization"></a>Administrar etiquetas personalizadas para su organización

Como administrador, puede controlar cómo se usan las etiquetas en toda la organización en el Centro de administración de Microsoft Teams. Actualmente, no puede usar PowerShell para administrar etiquetas.

![Captura de pantalla de la configuración de etiquetado en el Centro de administración de Microsoft Teams](media/manage-tags-admin-settings.png)

Un equipo puede tener hasta 100 etiquetas, se pueden asignar hasta 100 miembros del equipo a una etiqueta y se pueden asignar hasta 25 etiquetas a un solo usuario. 

### <a name="set-who-can-add-custom-tags"></a>Establecer quién puede agregar etiquetas personalizadas

De forma predeterminada, los propietarios de equipos pueden agregar etiquetas personalizadas. Puede cambiar esta configuración para permitir a los propietarios del equipo y a los miembros del equipo crear, editar, eliminar y administrar etiquetas o puede desactivar etiquetas para su organización.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Configuración de** Toda la organización Configuración de  >  **Teams.**
2. En **Etiquetado**, junto a **Etiquetas se administra mediante**, seleccione una de las siguientes opciones:

    - **Propietarios y miembros del equipo:** permita que los propietarios y miembros del equipo administren etiquetas.
    - **Propietarios de equipos:** permitir que los propietarios de equipos administren etiquetas.
    - **Deshabilitado:** Desactive las etiquetas.

### <a name="configure-custom-tags-settings"></a>Configurar la configuración de etiquetas personalizadas

Puede configurar las siguientes opciones de etiquetas para controlar cómo se usan las etiquetas personalizadas en toda la organización.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Configuración de** Toda la organización Configuración de  >  **Teams.**
2. En **Etiquetado**, establezca lo siguiente, según las necesidades de su organización.

    - Permitir que los propietarios de equipos reemplacen quién puede administrar etiquetas: al activar esta configuración, los  propietarios del equipo pueden establecer si los miembros del equipo pueden crear y administrar etiquetas dentro de un equipo y el valor de las etiquetas se administra mediante la configuración es el valor predeterminado para cada equipo.  Si desactiva esta configuración, las etiquetas **se administran** mediante la configuración no se pueden cambiar por equipo.
    - **Etiquetas predeterminadas sugeridas:** Úsese esta opción para agregar un conjunto de etiquetas predeterminadas. Puede agregar hasta 25 etiquetas y cada etiqueta puede contener un máximo de 25 caracteres. Los propietarios y miembros del equipo (si la característica está habilitada para ellos) pueden usar estas sugerencias, agregarlas o crear un nuevo conjunto de etiquetas.
    - **Permitir la creación de etiquetas** personalizadas: active esta configuración para permitir que los usuarios agreguen etiquetas que no sean las etiquetas predeterminadas sugeridas que establezca. Si está desactivado, los usuarios solo pueden usar las etiquetas predeterminadas sugeridas. Si desactiva esta opción, asegúrese de agregar una o más etiquetas predeterminadas.

## <a name="manage-custom-tags-settings-for-a-team"></a>Administrar la configuración de etiquetas personalizadas para un equipo

Si ha activado  la opción Permitir a los propietarios de equipos reemplazar quién puede administrar etiquetas en el Centro de administración de Microsoft Teams, los propietarios de los equipos pueden establecer si los miembros pueden agregar etiquetas en el nivel de equipo. Para ello, en la **pestaña Configuración** de un equipo, vaya a **Etiquetas** y, a continuación, elija quién puede agregar etiquetas.

![Captura de pantalla de la configuración de etiquetas en el nivel de equipo](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>Usar etiquetas

Esta es la manera de agregar etiquetas personalizadas y cómo configurar el etiquetado por turnos (si usa la aplicación Turnos en Teams). Para obtener más información, consulte [Usar etiquetas en Teams.](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

### <a name="create-and-assign-custom-tags"></a>Crear y asignar etiquetas personalizadas

Para crear y asignar etiquetas personalizadas, seleccione **Teams** en el lado izquierdo de la aplicación y, a continuación, busque su equipo en la lista. Seleccione   Aquí puede crear etiquetas y asignarlas a personas de su equipo.

![Captura de pantalla de cómo aplicar etiquetas en el cliente de Teams ](media/manage-tags-teams.png)

Para eliminar una etiqueta, seleccione **además de** más opciones junto a la etiqueta y, a continuación, seleccione Eliminar **etiqueta.**

### <a name="set-up-tagging-by-shift"></a>Configurar el etiquetado por turnos

1. En Teams, vaya a la [aplicación Turnos.](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)
2. Cree [grupos de turnos](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) y asízándolos después de un atributo como un rol. Por ejemplo, EngineerOnCall. El nombre del grupo de turnos será el nombre de la etiqueta.
3. [Rellene una programación](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) asignando turnos a los miembros de sus equipos. Cuando haya terminado, en la esquina superior derecha de la aplicación Turnos, seleccione **Compartir con el equipo.**
4. Espere 15 minutos para que los turnos programados rellenen el servicio de etiquetado.
5. Use la etiqueta en cualquier lugar donde use etiquetas en Teams.

El etiquetado por turnos permite que los usuarios lleguen a las personas en turno en tiempo real. Las notificaciones solo se envían a aquellas personas que están de turno en el momento en que se usa una etiqueta para iniciar un chat o en una publicación de canal.

## <a name="related-topics"></a>Temas relacionados

[Usar etiquetas en Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Administrar la aplicación Turnos para su organización en Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentación de la Ayuda de Turnos](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
