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
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dd9bd57f815079fd80a58b739b927b900305725b
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046630"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Administrar la aplicación Turnos para su organización en Microsoft Teams

## <a name="overview-of-shifts"></a>Información general sobre Turnos

La aplicación Turnos de Microsoft Teams mantiene conectados y sincronizados a los trabajadores de primera línea. Se ha diseñado primero para dispositivos móviles para una gestión del tiempo y una comunicación rápidas y eficaces para los equipos. Los turnos permiten a los trabajadores de primera línea y a sus directores usar sus dispositivos móviles para administrar programaciones y mantenerse en contacto.

- Los administradores pueden crear, actualizar y administrar la programación de los turnos del equipo. También pueden enviar mensajes únicamente a un usuario ("se ha caído algo al suelo") o a todo el equipo ("el director general regional llegará en 20 minutos"). Pueden enviar documentos de directivas, boletines de noticias y vídeos.
- Los empleados pueden consultar sus próximos turnos, ver quién más está en la programación del día, solicitar permutas de turnos y solicitar licencias.

Es importante saber que los turnos actualmente no admiten invitados. Esto significa que los invitados de un equipo no se pueden agregar ni usar horarios de turnos cuando el acceso de invitado está activado en Teams.

> [!Note]
> Para obtener más información sobre las capacidades de Turnos en las distintas plataformas, consulte [Características de Teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Disponibilidad de Turnos

Turnos está disponible en todas las SKUs de Enterprise donde Teams esté disponible.

> [!NOTE]
> Turnos está disponible en entornos de Government Community Cloud (GCC), pero no en entornos de GCC High o DoD.

## <a name="location-of-shifts-data"></a>Ubicaciones de datos de Turnos

Actualmente, los datos de turnos se almacenan en Azure en centros de datos de Asia Pacífico (APAC), la Unión Europea (UE) y Norteamérica. Para obtener más información acerca de la ubicación en la que se almacenan los datos, consulte [¿Dónde están mis datos](http://o365datacentermap.azurewebsites.net/)?

Para obtener más información sobre los datos de Turnos, incluidos el almacenamiento, la retención, la recuperación y el cifrado de datos de [Turnos, vea Preguntas frecuentes sobre los datos de Turnos](shifts-data-faq.md).

## <a name="set-up-shifts"></a>Confirgurar Turnos

### <a name="enable-or-disable-shifts-in-your-organization"></a>Deshabilitar o habilitar Turnos en la organización

De forma predeterminada, Turnos está habilitado para todos los usuarios de Teams de su organización. Puede desactivar o activar la aplicación en el nivel de organización en la página [Administrar aplicaciones](../../manage-apps.md) del Centro de administración de Microsoft Teams.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. En la lista de aplicaciones, busca la aplicación Turnos, selecciónala y cambia el botón de alternancia **Estado** a **Bloqueado** o **Permitido**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Habilitar o deshabilitar Turnos para usuarios específicos de su organización

Para permitir o impedir que determinados usuarios de su organización usen Turnos, asegúrese de que Turnos esté activado para su organización en la página [Administrar aplicaciones](../../manage-apps.md) . A continuación, cree una directiva de permisos de aplicación personalizada y asígnela a esos usuarios. Para obtener más información, consulte [Administrar configuración y directivas de aplicación personalizadas en Teams](../../teams-app-permission-policies.md).

### <a name="pin-shifts-to-teams"></a>Anclar Turnos a Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-shifts-and-other-apps-to-teams"></a>Usar la experiencia de la aplicación frontline adaptada para anclar Turnos y otras aplicaciones a Teams

La experiencia de aplicación de primera línea adaptada en Teams ancla las aplicaciones más relevantes en Teams para los usuarios que tienen una [licencia F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Entre las aplicaciones ancladas se incluyen Turnos, Walkie Talkie, Tareas y Aprobaciones. De forma predeterminada, esta característica está activada, lo que ofrece a sus trabajadores de primera línea una experiencia predefinida que se adapta a sus necesidades.

Las aplicaciones se anclan en la barra de aplicaciones (la barra situada en el lateral del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams), donde los usuarios pueden acceder a ellas de forma rápida y sencilla.

Para obtener más información, incluido cómo funciona la experiencia con las directivas de aplicaciones que establezca, consulte [Personalizar las aplicaciones de Teams para los trabajadores de primera línea](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).  

#### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>Usar una directiva de configuración de aplicaciones para anclar Turnos a Teams

Las directivas de configuración de aplicaciones le permiten personalizar Teams para anclar las aplicaciones más importantes para los usuarios.

Puede crear una [directiva de configuración de aplicación personalizada](../../teams-app-setup-policies.md) agregando la aplicación Turnos y, a continuación, [asignando la directiva](../../assign-policies-users-and-groups.md) a los usuarios. O bien, puede usar la directiva de configuración de la aplicación que forma parte de los paquetes de directiva Frontline Worker y Frontline Manager.

Un [paquete de directivas](../../manage-policy-packages.md) en Teams es una colección de directivas predefinidas y configuraciones de directiva que puede asignar a los usuarios que tienen roles similares en su organización. El conjunto de directivas de los paquetes de directiva Frontline Worker y Frontline Manager incluye una directiva de configuración de aplicaciones que ancla la aplicación Turnos y otras aplicaciones que admiten actividades de comunicación y colaboración para ese rol.

Se recomienda usar los paquetes de directivas Frontline Worker y Frontline Manager para simplificar, simplificar y ayudar a proporcionar coherencia al administrar directivas para su personal de primera línea.

### <a name="enable-shift-based-tags-in-teams"></a>Habilitar etiquetas basadas en turnos en Teams

[Las etiquetas](https://support.microsoft.com/office/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e) de Teams permiten a los usuarios conectarse fácilmente con un subconjunto de personas de un equipo. Con las etiquetas basadas en turnos, a los usuarios se les asignan automáticamente etiquetas que coinciden con su nombre de grupo de turnos y programación en Turnos. La etiqueta se puede usar en @mentions en la línea **Para** de un chat o en una publicación en cualquier canal estándar del equipo.

Las etiquetas basadas en turnos permiten a los usuarios ponerse en contacto con personas que están en turno en tiempo real. Las notificaciones se envían solo a aquellas personas que están de turno en el momento en que se usa la etiqueta en un chat o publicación de canal. Por ejemplo:

- Un administrador de store usa la etiqueta @Cashiers para publicar un anuncio en un canal para todos los cajeros a turnos.
- Una enfermera usa la etiqueta @CardiologistsOnCall para iniciar un chat con todos los cardiólogos de llamada.

Puede activar o desactivar la característica en el Centro de administración de Microsoft Teams. Para obtener más información, consulte [Administración de etiquetas en Teams](../../manage-tags.md).

## <a name="search-the-audit-log-for-shifts-events"></a>Buscar eventos de Turnos en el registro de auditoría

**(En versión preliminar)**

Puede busca el registro de auditoría para ver la actividad de Turnos en su organización.  Para obtener más información sobre cómo buscar en el registro de auditoría y ver una lista de las [actividades de Turnos](../../audit-log-events.md#shifts-in-teams-activities) que se registran en el registro de auditoría, consulte [Buscar eventos en Teams en el registro de auditoría](../../audit-log-events.md).

Para que pueda buscar en el registro de auditoría, primero debe activar la característica de auditoría en el [Centro de seguridad y cumplimiento](https://protection.office.com). Para obtener más información, consulte [Activar o desactivar la búsqueda de registros de auditoría](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Tenga en cuenta que los datos de auditoría solo están disponibles desde el momento en que activó la característica de auditoría.

## <a name="related-articles"></a>Artículos relacionados

- [Turnos para Teams](/microsoft-365/frontline/shifts-for-teams-landing-page)
- [Preguntas más frecuentes sobre los datos de Turnos](shifts-data-faq.md)
- [Conectores de Turnos](/microsoft-365/frontline/shifts-connectors)
- [Ayuda de turnos para los trabajadores de primera línea](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Asignar directivas a los usuarios en Teams](../../policy-assignment-overview.md)
