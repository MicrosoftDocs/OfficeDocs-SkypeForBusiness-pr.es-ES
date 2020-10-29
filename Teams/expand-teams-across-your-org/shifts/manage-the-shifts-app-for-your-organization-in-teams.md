---
title: Administrar la aplicación de turnos para su organización
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Obtenga información sobre cómo configurar y administrar la aplicación de turnos en Teams para trabajadores de los Firstline de su organización.
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
ms.openlocfilehash: d89ca8938c80b2afb8c1b32a395ab4a984327dcc
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790512"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Administrar la aplicación Turnos para su organización en Microsoft Teams

> [!IMPORTANT]
> A partir del 30 de junio de 2020, se ha retirado a Microsoft StaffHub. Estamos construyendo las capacidades de StaffHub en Microsoft Teams. En la actualidad, Teams incluye la aplicación de turnos para la administración de la programación, y las funciones adicionales se aplicarán a lo largo del tiempo. StaffHub ha dejado de funcionar para todos los usuarios el 30 de junio de 2020. Cualquier persona que intente abrir StaffHub verá un mensaje que le indica que debe descargar Teams. Para obtener más información, vea se ha [retirado Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Descripción general de los turnos

La aplicación turnos en Microsoft Teams mantiene a los trabajadores de los Firstline conectados y sincronizados. En primer lugar, se ha creado un teléfono móvil para una administración y comunicación rápidas y eficaces de los equipos. Turnos permite que los trabajadores de los Firstline y sus gerentes usen sus dispositivos móviles para administrar las programaciones y mantenerse en contacto.

- Los administradores crean, actualizan y administran programaciones de turnos para Teams. Pueden enviar mensajes a una persona ("hay un derrame en el piso") o todo el equipo ("el GM regional está llegando en 20 minutos"). También pueden enviar documentos de directivas, boletines de noticias y videos. 
- Los empleados ven sus próximos turnos, pueden ver quién más está programado para el día, solicitar intercambiar o ofrecer un turno, y solicitar un tiempo. 

Es importante saber que los turnos actualmente no admiten usuarios invitados. Esto significa que los invitados de un equipo no se pueden agregar o usar programaciones de turno cuando el acceso de invitados está activado en Teams. 

> [!Note]
> Para obtener más información sobre las capacidades de los turnos en diferentes plataformas, vea [características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Disponibilidad de los turnos

Turnos está disponible en todas las SKU de Enterprise donde está disponible Teams.

## <a name="location-of-shifts-data"></a>Ubicación de los datos de turnos

Mayús los datos están almacenados actualmente en Azure en centros de datos en Norteamérica, Europa occidental y Asia Pacífico. Para obtener más información sobre dónde se almacenan los datos, vea ¿ [dónde están mis datos](http://o365datacentermap.azurewebsites.net/)?

## <a name="set-up-shifts"></a>Configurar turnos

### <a name="enable-or-disable-shifts-in-your-organization"></a>Habilitar o deshabilitar turnos en su organización

Turnos está habilitado de forma predeterminada para todos los usuarios de los equipos de su organización. Puede desactivar o activar la aplicación en el nivel de organización en la página [Administrar aplicaciones](../../manage-apps.md) del centro de administración de Microsoft Teams.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps** .
2. En la lista de aplicaciones, realice una de las siguientes acciones:

    - Para desactivar los turnos de su organización, busque la aplicación turnos, selecciónela y haga clic en **bloquear** .
    - Para activar los turnos de su organización, busque la aplicación turnos, selecciónela y, a continuación, haga clic en **permitir** .

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Habilitar o deshabilitar turnos para usuarios específicos de su organización

Para permitir o bloquear a determinados usuarios de su organización el uso de turnos, asegúrese de que la opción turnos está activada para su organización en la página [Administrar aplicaciones](../../manage-apps.md) y, después, cree una directiva de permisos de aplicaciones personalizada y asígnela a esos usuarios. Para obtener más información, vea [Administrar directivas de permisos de aplicaciones en Teams](../../teams-app-permission-policies.md).

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Use la Directiva de configuración de la aplicación de FirstlineWorker para anclar turnos a teams

Las directivas de configuración de la aplicación le permiten personalizar Teams para resaltar las aplicaciones más importantes para los usuarios de su organización. Las aplicaciones establecidas en una directiva se anclan a la barra de la aplicación, que se &mdash; encuentra en el costado del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams &mdash; donde los usuarios puedan acceder a ellas de forma rápida y fácil.
 
Teams incluye una directiva de configuración de aplicaciones de FirstlineWorker integrada que puede asignar a los trabajadores de los Firstline de su organización. De forma predeterminada, la Directiva incluye las aplicaciones actividad, turnos, chat y llamadas. 

Para ver la Directiva de FirstlineWorker, en el navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de configuración de la aplicación de **aplicación de Teams**  >  **App setup policies** .

![Captura de pantalla de la Directiva de configuración de la aplicación de FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Captura de pantalla de la Directiva de configuración de la aplicación de FirstlineWorker en el centro de administración de Microsoft Teams")

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>Asignar la Directiva de configuración de la aplicación de FirstlineWorker a los usuarios

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Buscar eventos de turnos en el registro de auditoría

**(en la versión preliminar)**

Puede buscar en el registro de auditoría para ver la actividad de los turnos en su organización.  Para obtener más información sobre cómo buscar en el registro de auditoría y ver una lista de [las actividades de turnos](../../audit-log-events.md#shifts-in-teams-activities) registradas en el registro de auditoría, consulte [buscar eventos en el registro de auditoría de los equipos](../../audit-log-events.md).

Antes de poder buscar en el registro de auditoría, primero debe activar la auditoría en el [centro de cumplimiento de & de seguridad](https://protection.office.com). Para obtener más información, vea [activar o desactivar la búsqueda de registros de auditoría](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Tenga en cuenta que los datos de auditoría solo están disponibles desde el punto en el que activó la auditoría.

## <a name="related-topics"></a>Temas relacionados

- [Desplaza la ayuda para los trabajadores de los Firstline](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Asignar directivas a los usuarios de Teams](../../assign-policies.md)
