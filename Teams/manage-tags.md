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
description: Aprenda a administrar cómo se usan las etiquetas en su organización en Microsoft Teams.
ms.openlocfilehash: e5222a820a3a721c3692b0cdb272d1c4f3aaea6d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145857"
---
# <a name="manage-tags-in-microsoft-teams"></a>Administrar etiquetas en Microsoft Teams

> [!NOTE]
> Se está implementando una de las características analizadas en este artículo, **etiquetar** por turnos. Si es administrador, puede averiguar cuándo se lanzará esta característica para su región en el Centro de mensajes (en el Centro de administración de [Microsoft 365).](https://portal.office.com/adminportal/home) Para estar al tanto de las próximas características de Teams, consulte el mapa de [ruta de Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)

## <a name="overview"></a>Información general

Las etiquetas de Microsoft Teams permiten a los usuarios conectarse rápida y fácilmente con un subconjunto de personas en un equipo. Puede crear y asignar etiquetas personalizadas para clasificar personas en función de atributos, como rol, proyecto, aptitud o ubicación. O bien, las etiquetas se pueden asignar automáticamente a personas en función de su programación y la información de turnos en la aplicación [Turnos](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (próximamente). Una vez que se agrega una etiqueta a uno o varios miembros del equipo, cualquiera en una publicación de canal la puede usar en @mentions o para iniciar una conversación solo con las personas a las que se les haya asignado esa etiqueta.

Como se ha mencionado anteriormente, hay dos tipos de etiquetas en Teams.

- **Etiquetas personalizadas:** los propietarios del equipo y los miembros del equipo (si la característica está habilitada para ellos) pueden crear y asignar etiquetas manualmente a los usuarios. Por ejemplo, una etiqueta "Diseñador" o "Radiólogo" llegará a esos conjuntos de personas de un equipo sin tener que escribir sus nombres.
- **Etiquetado por turnos:** con esta característica, a los usuarios se les asignan automáticamente etiquetas que coinciden con su programación y el nombre de grupo de turnos en la aplicación [Turnos](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) en Teams. Por ejemplo, la etiqueta "EngineerOnCall" llega a todos los ingenieros que están programados en Turnos para que trabajen en el momento en que se usa la etiqueta en una publicación de canal o chat. Al etiquetar por turnos, Teams quita las conjeturas de conocer el nombre del personal en turnos cuando los usuarios necesitan retransmitir información rápidamente. Las etiquetas por turnos también pueden estar copiadas por los principales sistemas de administración de recursos, como JDA, Kronos y AMiON, integrándolos con Turnos en Teams. Para obtener más información sobre cómo configurar esta característica, vea Configurar el etiquetado [por turnos.](#set-up-tagging-by-shift)

> [!NOTE]
> Las etiquetas aún no se admiten en canales privados. Las etiquetas se están implementando en US Government Community Cloud (GCC). Las etiquetas no están disponibles en las organizaciones GCC High ni Department of Defense (DoD). 

## <a name="how-tags-work"></a>Cómo funcionan las etiquetas

Una etiqueta se puede agregar manualmente o asignar automáticamente a una persona de un equipo específico. A continuación, se puede usar  @mentions en la línea Para de un chat o en una publicación de cualquier canal estándar del equipo. Estos son algunos ejemplos de cómo se pueden usar las etiquetas en Teams:

- Un administrador de la tienda publica un anuncio en un canal para notificar a todos los cajadores.
- Un administrador hospitalario envía un mensaje a todos los radiólogos de un canal.
- Un administrador de marketing inicia un chat grupal con todos los diseñadores.
- Una enfermera envía un mensaje a todos los cardiólogos que están en llamada. (próximamente)
- Un ingeniero de sistema publica un anuncio en un canal para notificar a todos los ingenieros de campo de turno. (próximamente)

Cuando se utiliza una etiqueta @mentioned en una conversación del canal, los miembros del equipo asociados con la etiqueta recibirán una notificación, igual que cualquier otro @mention.

## <a name="manage-custom-tags-for-your-organization"></a>Administrar etiquetas personalizadas para su organización

Como administrador, puede controlar cómo se usan las etiquetas en toda la organización en el Centro de administración de Microsoft Teams. Actualmente, no puede usar PowerShell para administrar etiquetas.

![Captura de pantalla de la configuración de etiquetado en el Centro de administración de Microsoft Teams](media/manage-tags-admin-settings.png)

Un equipo puede tener hasta 100 etiquetas, hasta 100 miembros del equipo pueden asignarse a una etiqueta y hasta 25 etiquetas pueden asignarse a un solo usuario. 

### <a name="set-who-can-add-custom-tags"></a>Establecer quién puede agregar etiquetas personalizadas

De forma predeterminada, los propietarios del equipo pueden agregar etiquetas personalizadas. Puede cambiar esta configuración para permitir que los propietarios del equipo y los miembros del equipo creen, editan, eliminen y administren etiquetas, o bien puede desactivar las etiquetas de su organización.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga **clic** en Configuración de Teams para  >  **toda la organización.**
2. En **Etiquetas,** junto **a Etiquetas son administradas por,** seleccione una de las siguientes opciones:

    - **Propietarios y miembros del equipo:** permita que los propietarios y miembros del equipo administren etiquetas.
    - **Propietarios de** equipo: permita que los propietarios del equipo administren etiquetas.
    - **Deshabilitada:** Desactive las etiquetas.

### <a name="configure-custom-tags-settings"></a>Configurar las opciones de etiquetas personalizadas

Puede configurar las siguientes opciones de etiquetas para controlar cómo se usan las etiquetas personalizadas en toda la organización.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga **clic** en Configuración de Teams para  >  **toda la organización.**
2. En **Etiquetado,** establezca lo siguiente, dependiendo de las necesidades de su organización.

    - Permitir que los propietarios del equipo invalide quién puede administrar las etiquetas: al activar esta configuración,  los propietarios del equipo pueden establecer si los miembros del equipo pueden crear y administrar etiquetas dentro de un equipo y el valor de las etiquetas se administra estableciendo el valor predeterminado para cada equipo.  Si desactiva esta configuración, la configuración **Etiquetas se administra** mediante una configuración que no se puede cambiar por equipo.
    - **Etiquetas predeterminadas sugeridas:** use esta opción para agregar un conjunto de etiquetas predeterminadas. Puede agregar hasta 25 etiquetas y cada una de ellas puede contener un máximo de 25 caracteres. Los propietarios y miembros del equipo (si la característica está habilitada para ellos) pueden usar estas sugerencias, agregarles o crear un nuevo conjunto de etiquetas.
    - **Permitir la creación de etiquetas** personalizadas: active esta configuración para permitir que los usuarios agreguen etiquetas que no sean las etiquetas predeterminadas sugeridas que establezca. Si está desactivada, los usuarios solo podrán usar las etiquetas predeterminadas sugeridas. Si lo desactiva, asegúrese de agregar una o más etiquetas predeterminadas.

## <a name="manage-custom-tags-settings-for-a-team"></a>Administrar la configuración de etiquetas personalizadas para un equipo

Si ha activado  la opción Permitir que los propietarios del equipo invalide quién puede administrar la configuración de etiquetas en el Centro de administración de Microsoft Teams, los propietarios del equipo pueden establecer si los miembros pueden agregar etiquetas en el nivel de equipo. Para ello, en la **pestaña** Configuración de un equipo, vaya a Etiquetas y **elija** quién puede agregar etiquetas.

![Captura de pantalla de la configuración de etiquetas en el nivel de equipo](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>Usar etiquetas

A continuación se explica cómo agregar etiquetas personalizadas y cómo configurar el etiquetado por turnos (si usa la aplicación Turnos en Teams). Para obtener más información, consulte [Usar etiquetas en Teams.](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

### <a name="create-and-assign-custom-tags"></a>Crear y asignar etiquetas personalizadas

Para crear y asignar etiquetas personalizadas, seleccione **Teams** en el lado izquierdo de la aplicación y, a continuación, busque su equipo en la lista. Seleccione **usted ndo ndo más opciones y,** a continuación, elija **Administrar etiquetas.** Aquí puede crear etiquetas y asignarlas a los miembros de su equipo.

![Captura de pantalla de cómo aplicar etiquetas en el cliente de Teams ](media/manage-tags-teams.png)

Para eliminar una etiqueta, seleccione **además de "Eliminar** etiqueta" y "Eliminar **etiqueta".**

### <a name="set-up-tagging-by-shift"></a>Configurar el etiquetado por turnos

1. En Teams, vaya a la [aplicación Turnos.](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)
2. Crear [grupos de turnos](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) y nombrarlos después de un atributo como un rol. Por ejemplo, EngineerOnCall. El nombre del grupo de turnos será el nombre de la etiqueta.
3. [Rellene una programación](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) asignando turnos a los miembros de sus equipos. Cuando haya terminado, en la esquina superior derecha de la aplicación Turnos, seleccione **Compartir con el equipo.**
4. Espere 15 minutos hasta que los turnos programados rellenen el servicio de etiquetado.
5. Use la etiqueta en cualquier lugar donde use etiquetas en Teams.

El etiquetado por turnos permite a los usuarios contactar con los usuarios en el turno en tiempo real. Las notificaciones se envían solo a aquellas personas que están en un turno en el momento en que se usa una etiqueta para iniciar un chat o una publicación de canal.

## <a name="related-topics"></a>Temas relacionados

[Usar etiquetas en Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Administrar la aplicación Turnos para su organización en Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentación de la Ayuda de Turnos](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
