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
description: Obtenga información sobre cómo configurar y administrar la aplicación Turnos en Teams para trabajadores de primera línea de su organización.
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
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909094"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Administrar la aplicación Turnos para su organización en Microsoft Teams

> [!IMPORTANT]
> A partir del 30 de junio de 2020, Se ha retirado Microsoft StaffHub. Estamos creando funciones de StaffHub en Microsoft Teams. Hoy en día, Teams incluye la aplicación Turnos para la administración de programación y otras funcionalidades se irán lanzando a lo largo del tiempo. StaffHub dejó de funcionar para todos los usuarios el 30 de junio de 2020. Cualquier persona que intente abrir StaffHub se mostrará un mensaje que le dirigirá a descargar Teams. Para obtener más información, [vea Microsoft StaffHub se ha retirado.](microsoft-staffhub-to-be-retired.md)  

## <a name="overview-of-shifts"></a>Información general sobre turnos

La aplicación Turnos de Microsoft Teams mantiene a los Trabajadores de Frontline Workers conectados y sincronizados. Se ha creado para dispositivos móviles, lo que ofrece una administración del tiempo y una comunicación rápida y eficaz para los equipos. Turnos permite a los trabajadores de frontline workers y sus administradores usar sus dispositivos móviles para administrar programaciones y mantenerse en contacto.

- Los administradores crean, actualizan y administran las programaciones de turnos de los equipos. Pueden enviar mensajes a una persona ("se ha desbordado algo al suelo") o a todo el equipo ("el director general regional llegará en 20 minutos"). También pueden enviar documentos de directiva, boletines de noticias y vídeos. 
- Los empleados ven sus próximos turnos, ven quién más está programado para el día, solicitan permutar u ofrecer un turno y solicitan un permiso. 

Es importante saber que Turnos no admite actualmente usuarios invitados. Esto significa que no se pueden agregar invitados en un equipo ni usar las programaciones de turnos cuando se ha activado el acceso de invitado en Teams. 

> [!Note]
> Para obtener más información sobre las capacidades de Turnos en distintas plataformas, consulte [Características de Teams por plataforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="availability-of-shifts"></a>Disponibilidad de los turnos

Turnos está disponible en todas las SKU empresariales donde Teams está disponible.

## <a name="location-of-shifts-data"></a>Ubicación de los datos de Turnos

Los datos de Turnos se almacenan actualmente en Azure en los centros de datos de Norteamérica, Europa occidental y Asia Pacífico. Para obtener más información sobre dónde se almacenan los datos, vea [¿Dónde están mis datos?](http://o365datacentermap.azurewebsites.net/)

## <a name="set-up-shifts"></a>Configurar turnos

### <a name="enable-or-disable-shifts-in-your-organization"></a>Habilitar o deshabilitar Turnos en su organización

Turnos está habilitado de forma predeterminada para todos los usuarios de Teams en su organización. Puede desactivar o activar la aplicación en el [](../../manage-apps.md) nivel de la organización en la página Administrar aplicaciones del Centro de administración de Microsoft Teams.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Administrar aplicaciones de Teams.**  >  
2. En la lista de aplicaciones, realice una de las siguientes acciones:

    - Para desactivar Turnos para su organización, busque la aplicación Turnos, selecciónelo y, a continuación, **seleccione Bloquear.**
    - Para activar Turnos para su organización, busque la aplicación Turnos, selecciónelo y, a continuación, **seleccione Permitir.**

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Habilitar o deshabilitar Turnos para usuarios específicos de su organización

Para permitir o impedir que determinados usuarios de su organización utilicen Turnos, asegúrese de que Turnos está activado para su organización en la página Administrar aplicaciones y, a continuación, cree una directiva de permisos de aplicación personalizada y asígnela a esos usuarios. [](../../manage-apps.md) Para obtener más información, consulte [Administrar directivas de permisos de aplicaciones en Teams.](../../teams-app-permission-policies.md)

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Usar la directiva de configuración de la aplicación FrontlineWorker para anclar Turnos a Teams

Las directivas de configuración de aplicaciones le permiten personalizar Teams para resaltar las aplicaciones más importantes para los usuarios de su organización. Las aplicaciones establecidas en una directiva se anclan en la barra de aplicaciones situada en el lado del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams, donde los usuarios pueden acceder a ellos de forma rápida y &mdash; &mdash; sencilla.
 
Teams incluye una directiva de configuración de la aplicación FrontlineWorker integrada que puede asignar a los trabajadores de frontline workers de su organización. De forma predeterminada, la directiva incluye las aplicaciones Actividad, Turnos, Chat y Llamadas. 

Para ver la directiva de FrontlineWorker, en el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a las directivas de configuración de la  >  **aplicación Teams.**

![Captura de pantalla de la directiva de configuración de la aplicación FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Captura de pantalla de la directiva de configuración de la aplicación FrontlineWorker en el Centro de administración de Microsoft Teams")

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a>Asignar la directiva de configuración de la aplicación FrontlineWorker a los usuarios

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Buscar eventos de Turnos en el registro de auditoría

**(en la versión preliminar)**

Puede buscar en el registro de auditoría para ver la actividad de Turnos en su organización.  Para obtener más información sobre cómo buscar en el registro de auditoría y para ver una lista de las actividades de [Turnos](../../audit-log-events.md#shifts-in-teams-activities) que se registran en el registro de auditoría, consulte Buscar eventos en el registro de auditoría [en Teams.](../../audit-log-events.md)

Antes de poder buscar en el registro de auditoría, primero tiene que activar la auditoría en el Centro de seguridad y [& cumplimiento.](https://protection.office.com) Para obtener más información, vea Activar o desactivar la búsqueda [del registro de auditoría.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014) Tenga en cuenta que los datos de auditoría solo están disponibles desde el punto en el que ha activado la auditoría.

## <a name="related-topics"></a>Temas relacionados

- [Ayuda de turnos para los trabajadores de primera línea](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Asignar directivas a los usuarios en Teams](../../assign-policies.md)
