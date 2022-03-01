---
title: Administrar la aplicación Turnos para su organización
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: Obtenga información sobre cómo configurar y administrar la aplicación Turnos en Teams para los trabajadores de primera línea de su organización.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d38af9f55f1620a1f38ad5860c71366201bb9444
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039908"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Administrar la aplicación Turnos para su organización en Microsoft Teams

## <a name="overview-of-shifts"></a>Información general sobre Turnos

La aplicación Turnos de Microsoft Teams mantiene a los trabajadores de primera línea conectados y sincronizados. Se ha creado en primer lugar para la administración del tiempo y la comunicación rápidas y eficaces para los equipos. Los turnos permiten a los trabajadores de primera línea y a sus jefes usar sus dispositivos móviles para administrar las programaciones y mantenerse en contacto.

- Los administradores pueden crear, actualizar y administrar la programación de los turnos del equipo. También pueden enviar mensajes únicamente a un usuario ("se ha caído algo al suelo") o a todo el equipo ("el director general regional llegará en 20 minutos"). Pueden enviar documentos de directivas, boletines de noticias y vídeos.
- Los empleados pueden consultar sus próximos turnos, ver quién más está en la programación del día, solicitar permutas de turnos y solicitar licencias.

Es importante saber que los turnos actualmente no admiten invitados. Esto significa que los invitados de un equipo no se pueden agregar ni usar horarios de turnos cuando el acceso de invitado está activado en Teams.

> [!Note]
> Para obtener más información sobre las capacidades de Turnos en las distintas plataformas, consulte [Características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Disponibilidad de Turnos

Turnos está disponible en todas las SKUs de Enterprise donde Teams esté disponible.

> [!NOTE]
> Los turnos están disponibles en Government Community Cloud (GCC) pero no en GCC altos o doD.

## <a name="location-of-shifts-data"></a>Ubicaciones de datos de Turnos

Los datos de turnos se almacenan actualmente en Azure en centros de datos de Asia Pacífico (APAC), la Unión Europea (UE) y Norteamérica. Para obtener más información acerca de la ubicación en la que se almacenan los datos, consulte [¿Dónde están mis datos](http://o365datacentermap.azurewebsites.net/)?

Para obtener más información sobre los datos de Turnos, incluido el almacenamiento, la retención, la recuperación y el cifrado de los datos de Turnos, vea Preguntas [más frecuentes sobre los datos de turnos](shifts-data-faq.md).

## <a name="set-up-shifts"></a>Confirgurar Turnos

### <a name="enable-or-disable-shifts-in-your-organization"></a>Deshabilitar o habilitar Turnos en la organización

De forma predeterminada, Turnos está habilitado para todos los usuarios de Teams de su organización. Puede desactivar o activar la aplicación en el nivel de organización en la página [Administrar aplicaciones](../../manage-apps.md) del Centro de administración de Microsoft Teams.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. En la lista de aplicaciones, busque la aplicación Turnos, selecciónelo y, después, cambie el  botón de alternancia Estado a **Bloqueado** o **Permitido**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Habilitar o deshabilitar Turnos para usuarios específicos de su organización

Para permitir o bloquear usuarios específicos de su organización de usar Turnos, asegúrese de que Turnos está activado para su organización en la [página Administrar aplicaciones](../../manage-apps.md) . A continuación, cree una directiva de permisos de aplicación personalizada y asígnela a esos usuarios. Para obtener más información, consulte [Administrar configuración y directivas de aplicación personalizadas en Teams](../../teams-app-permission-policies.md).

### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>Use una directiva de configuración de la aplicación para anclar Turnos a Teams

Las directivas de configuración de aplicaciones le permiten personalizar Teams para resaltar las aplicaciones que sean más importantes para los usuarios de su organización. Las aplicaciones que establecen en una directiva se anclan a la barra de aplicaciones &mdash;situada en el lateral en el cliente de escritorio de Teams y en la parte inferior para los clientes móviles de Teams&mdash; donde los usuarios pueden acceder a ellas rápida y fácilmente.

Puede crear una directiva [de configuración de aplicaciones personalizada](../../teams-app-setup-policies.md) agregando la aplicación Turnos y, a continuación, [asigne la directiva](../../assign-policies-users-and-groups.md) a los usuarios. O bien, puede usar la directiva de configuración de la aplicación que forma parte de los paquetes de directiva De frontline worker y Frontline Manager.

Un [paquete de](../../manage-policy-packages.md) directivas Teams es una colección de directivas predefinidas y configuraciones de directiva que puede asignar a usuarios que tienen roles similares en su organización. El conjunto de directivas de los paquetes de directivas de Frontline Worker y Frontline Manager incluye una directiva de configuración de aplicaciones que ancla la aplicación Turnos y otras aplicaciones que admiten actividades de comunicación y colaboración para ese rol.

Se recomienda usar los paquetes de directivas de Frontline Worker y Frontline Manager a medida que simplifican, simplifican y ayudan a proporcionar coherencia al administrar directivas para los empleados de frontline.

## <a name="search-the-audit-log-for-shifts-events"></a>Buscar eventos de Turnos en el registro de auditoría

**(en la versión preliminar)**

Puede busca el registro de auditoría para ver la actividad de Turnos en su organización.  Para obtener más información sobre cómo buscar en el registro de auditoría y ver una lista de las [actividades de Turnos](../../audit-log-events.md#shifts-in-teams-activities) que se registran en el registro de auditoría, consulte [Buscar eventos en Teams en el registro de auditoría](../../audit-log-events.md).

Para que pueda buscar en el registro de auditoría, primero debe activar la característica de auditoría en el [Centro de seguridad y cumplimiento](https://protection.office.com). Para obtener más información, consulte [Activar o desactivar la búsqueda de registros de auditoría](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Tenga en cuenta que los datos de auditoría solo están disponibles desde el momento en que activó la característica de auditoría.

## <a name="related-articles"></a>Artículos relacionados

- [Turnos para Teams](../shifts-for-teams-landing-page.md)
- [Preguntas más frecuentes sobre los datos de turnos](shifts-data-faq.md)
- [Conectores de turnos](shifts-connectors.md)
- [Ayuda de turnos para los trabajadores de primera línea](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Asignar directivas a los usuarios en Teams](../../policy-assignment-overview.md)
