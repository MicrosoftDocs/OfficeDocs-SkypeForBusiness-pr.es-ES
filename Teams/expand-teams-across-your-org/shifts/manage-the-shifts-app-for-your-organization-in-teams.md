---
title: Administrar la aplicación Turnos para su organización
author: cichur
ms.author: v-cichur
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Aprenda a configurar y administrar la aplicación Turnos en Teams para los trabajadores de primera línea en su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909094"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Administrar la aplicación Turnos para su organización en Microsoft Teams

> [!IMPORTANT]
> Desde el 30 de junio de 2020 Microsoft StaffHub ha sido retirado. Estamos creando las funciones de StaffHub en Microsoft Teams. En la actualidad, Teams incluye la aplicación Turnos para la administración de la programación y a medida que pase el tiempo se implementarán funciones adicionales StaffHub dejó de proveer servicios a todos los usuarios el 30 de junio de 2020. A cualquier usuario que intente abrir StaffHub se mostrará un mensaje en el que se le indicará que descargue Teams. Para obtener más información, consulte [Microsoft StaffHub se ha retirado](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Información general sobre Turnos

La aplicación Turnos en Microsoft Teams mantiene a los trabajadores de primera línea conectados y sincronizados. Fue creado pensando en los dispositivos móviles para tener una comunicación y manejo del tiempo más ágiles y efectivas para los equipos. Turnos permite a los trabajadores de primera línea y sus administradores usar sus dispositivos móviles para administrar programaciones y mantenerse en contacto.

- Los administradores pueden crear, actualizar y administrar la programación de los turnos del equipo. También pueden enviar mensajes únicamente a un usuario ("se ha caído algo al suelo") o a todo el equipo ("el director general regional llegará en 20 minutos"). Pueden enviar documentos de directivas, boletines de noticias y vídeos. 
- Los empleados pueden consultar sus próximos turnos, ver quién más está en la programación del día, solicitar permutas de turnos y solicitar licencias. 

Es importante saber que actualmente Turnos no admite usuarios invitados. Esto significa que los invitados de un equipo no se pueden agregar ni usar horarios de turnos cuando el acceso de invitado está activado en Teams. 

> [!Note]
> Para obtener más información sobre las capacidades de Turnos en las distintas plataformas, consulte [Características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Disponibilidad de Turnos

Turnos está disponible en todas las SKUs de Enterprise donde Teams esté disponible.

## <a name="location-of-shifts-data"></a>Ubicaciones de datos de Turnos

Actualmente, los datos de Turnos se almacenan en los centros de datos de Azure de Norteamérica y Europa occidental y Asia pacífico. Para obtener más información acerca de la ubicación en la que se almacenan los datos, consulte [¿Dónde están mis datos](http://o365datacentermap.azurewebsites.net/)?

## <a name="set-up-shifts"></a>Confirgurar Turnos

### <a name="enable-or-disable-shifts-in-your-organization"></a>Deshabilitar o habilitar Turnos en la organización

De forma predeterminada, Turnos está habilitado para todos los usuarios de Teams de su organización. Puede desactivar o activar la aplicación en el nivel de organización en la página [Administrar aplicaciones](../../manage-apps.md) del Centro de administración de Microsoft Teams.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. En la lista de aplicaciones, siga uno de estos pasos:

    - Para desactivar Turnos para su organización, busque la aplicación de Turnos, selecciónela y después haga clic en **Bloquear**.
    - Para activar Turnos para su organización, busque la aplicación de Turnos, selecciónela y después haga clic en **Permitir**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Habilitar o deshabilitar Turnos para usuarios específicos de su organización

Para permitir o impedir que usuarios específicos de la organización puedan usar Turnos, asegúrese de que la aplicación esté activada para su organización en la página [Administrar aplicaciones](../../manage-apps.md) y después cree una directiva de permisos de aplicación personalizada y asígnela a esos usuarios. Para obtener más información, consulte [Administrar configuración y directivas de aplicación personalizadas en Teams](../../teams-app-permission-policies.md).

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Usar una directiva de configuración de aplicación para anclar Turnos a Teams

Las directivas de configuración de aplicaciones le permiten personalizar Teams para resaltar las aplicaciones que sean más importantes para los usuarios de su organización. Las aplicaciones que establecen en una directiva se anclan a la barra de aplicaciones &mdash;situada en el lateral en el cliente de escritorio de Teams y en la parte inferior para los clientes móviles de Teams&mdash; donde los usuarios pueden acceder a ellas rápida y fácilmente.
 
Teams incluye una política de configuración de la aplicación FrontlineWorker incorporada que puede asignar a los trabajadores de primera línea en su organización. De forma predeterminada, la directiva incluye las aplicaciones Actividad, Turnos, Chat y Llamadas. 

Para ver la directiva de FrontlineWorker, en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **aplicación de Teams** > **Directivas de configuración de la aplicación**.

![Captura de pantalla de la directiva de configuración de la aplicación FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Captura de pantalla de la directiva de configuración de ña aplicación FrontlineWorker en el Centro de administración de Microsoft Teams")

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a>Asignar la directiva de configuración de la aplicación FirstlineWorker a los usuarios

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Buscar eventos de Turnos en el registro de auditoría

**(en la versión preliminar)**

Puede busca el registro de auditoría para ver la actividad de Turnos en su organización.  Para obtener más información sobre cómo buscar en el registro de auditoría y ver una lista de las [actividades de Turnos](../../audit-log-events.md#shifts-in-teams-activities) que se registran en el registro de auditoría, consulte [Buscar eventos en Teams en el registro de auditoría](../../audit-log-events.md).

Para que pueda buscar en el registro de auditoría, primero debe activar la característica de auditoría en el [Centro de seguridad y cumplimiento](https://protection.office.com). Para obtener más información, consulte [Activar o desactivar la búsqueda de registros de auditoría](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Tenga en cuenta que los datos de auditoría solo están disponibles desde el momento en que activó la característica de auditoría.

## <a name="related-topics"></a>Temas relacionados

- [Ayuda de Turnos para los trabajadores de primera línea](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Asignar directivas a los usuarios en Teams](../../assign-policies.md)
