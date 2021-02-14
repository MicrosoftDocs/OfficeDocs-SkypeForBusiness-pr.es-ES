---
title: 'Administrar equipos grandes en Microsoft Teams: procedimientos recomendados'
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Obtenga información sobre los procedimientos recomendados para administrar equipos grandes en Microsoft Teams para satisfacer las necesidades de su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 90345578ceb6bbf8d8752b561511d8df85023bf1
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582667"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Administrar equipos grandes en Microsoft Teams: procedimientos recomendados
======================================================

Microsoft Teams es igualmente eficaz para facilitar las comunicaciones entre grupos pequeños con docenas de miembros y grupos grandes con miles de miembros. Revise [los límites y las especificaciones de Teams para](limits-specifications-teams.md) ver las actualizaciones de los tamaños de los equipos. Aumentar el tamaño del equipo lleva a desafíos de administración y funcionamiento únicos. En este artículo se describen los procedimientos recomendados para crear y administrar equipos grandes formados por miles de miembros.

## <a name="value-of-large-teams"></a>Valor de los equipos grandes

Los equipos de gran tamaño son muy útiles para habilitar los siguientes escenarios de colaboración:

- Colaboración para todo el **departamento:** si su organización tiene varios departamentos como Finanzas, Operaciones, R&D, etc., puede crear un único equipo que incluya todos los miembros de un departamento específico. Ahora se pueden compartir todas las comunicaciones relevantes para un departamento en este equipo, que facilita el acceso instantáneo y la participación de los miembros.

- **Colaboración en grupos de recursos de** empleados: las organizaciones a menudo tienen grandes grupos de personas con intereses mutuos que pertenecen a un departamento o grupo de trabajo diferente. Como ejemplo, puede haber un grupo de personas que comparten una pasión por las finanzas personales y la inversión. En muchas ocasiones, resulta difícil conectarse en una organización grande. Para desarrollar comunidades para estos grupos, los administradores de inquilinos pueden crear un gran equipo que actúa como un grupo de recursos para toda la empresa pública al que cualquier persona puede unirse y aprovechar. Finalmente, estas comunidades recopilan información que pueden disfrutar tanto los miembros nuevos como los existentes.

- **Colaboración entre miembros internos** y externos: los productos más populares suelen desarrollar una comunidad de usuarios primeros que están ansiosos por probar la publicación de nuevos productos y proporcionar comentarios. Los primeros usuarios desarrollan una relación con los grupos de productos para ayudar a dar forma al producto. En estos escenarios, los administradores de inquilinos pueden configurar un gran equipo que incluya grupos de productos internos y evaluadores de productos externos para facilitar un proceso de desarrollo de productos enriquecidos. Estos equipos también pueden proporcionar asistencia al cliente a un conjunto selecto de clientes.

## <a name="create-teams-from-existing-groups"></a>Crear equipos a partir de grupos existentes

Use grupos de contactos, grupos de seguridad o grupos de Office para iniciar su equipo. Puede importar un grupo para crear un equipo o un equipo desde un grupo de Office.

**Importar un grupo** para crear un equipo: Al importar un grupo con hasta 3500 miembros a Teams, Teams calcula automáticamente el número total de miembros en el grupo. Se trata de una importación única y los cambios futuros en el grupo no se actualizarán automáticamente en Teams.

Crear un equipo a partir de un grupo grande de **Microsoft 365:** al crear un equipo desde un grupo  grande de Microsoft 365, los miembros forman automáticamente parte del grupo de Microsoft 365 y del equipo. En el futuro, a medida que los miembros del equipo se unan o abandonen el grupo de Microsoft 365, se agregarán o quitarán automáticamente del equipo.

## <a name="create-channels-to-focus-discussions"></a>Crear canales para enfocar los debates

Puede restringir las discusiones de grupo creando canales centrados. Consulte [Procedimientos recomendados para organizar equipos.](best-practices-organizing.md)

## <a name="restrict-channel-creation"></a>Restringir la creación de canales

Si cualquier miembro del equipo puede crear canales, ese equipo puede tener acceso a canal. Los propietarios del equipo deben desactivar la creación, actualización, eliminación y restauración de canales de los miembros en **Configuración > de miembro.** Consulte [Información general de los equipos y canales.](teams-channels-overview.md)

![Imagen de pantalla que muestra la sección de permisos de miembro de la pestaña Configuración de la consola de administración.](media/no-channel-creation.png "Imagen de la sección de permisos de miembro de la pestaña Configuración de la consola de administración. Las opciones permitir que los miembros creen o eliminen canales están desactivadas.")

## <a name="add-favorite-channels"></a>Agregar canales favoritos

Para acelerar la participación del nuevo usuario y el descubrimiento de contenido, puede seleccionar canales favoritos que están disponibles para el usuario de forma predeterminada. En el **panel Canales** del centro de administración, compruebe los canales en la **columna Mostrar para miembros.**

![Imagen de pantalla que muestra el panel de canales de la consola de administración.](media/favorite-channels.png "Imagen de pantalla que muestra el panel de canales de la consola de administración. Algunos canales están activados para mostrar los miembros.")

 Consulte [Crear sus primeros equipos y canales](get-started-with-teams-create-your-first-teams-and-channels.md) para obtener más información.

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regular las aplicaciones y los bots en equipos grandes

Para evitar que se agreguen bots o aplicaciones que distraigan, los propietarios del equipo pueden deshabilitar, agregar, quitar y cargar aplicaciones y conectores para los miembros del equipo. En el centro de administración, **en Configuración > de miembro,** desactive las tres opciones que permiten a los miembros agregar aplicaciones o conectores.

![Imagen de pantalla que muestra la sección Permisos de miembro del panel Configuración.](media/disable-bots-connectors.png "Imagen de pantalla que muestra la sección Permisos de miembro del panel Configuración. Las opciones para permitir que los miembros agreguen aplicaciones o conectores están desactivadas.")

Vea [Aplicaciones, bots y & conectores.](deploy-apps-microsoft-teams-landing-page.md)

## <a name="regulate-team-and-channel-mentions"></a>Regular las menciones de equipos y canales

Las menciones de canales y equipos se pueden usar para llamar la atención de todo el equipo sobre determinadas publicaciones del canal. Una vez que se usa una mención en una publicación, se envía una notificación a miles de miembros del equipo. Si las notificaciones son demasiado frecuentes, los miembros del equipo pueden sobrecargarse y podrían quejarse de los propietarios del equipo. Para evitar las menciones de canal o equipo, desactive las menciones de canal y equipo para los miembros desactivando las casillas en el panel Configuración **> @mentions** teams.

![Imagen de pantalla que muestra la sección En Menciones del panel Configuración.](media/no-at-mentions.png "Imagen de pantalla que muestra la sección En Menciones del panel Configuración. Las opciones para mostrar y dar acceso a los miembros en las menciones están desactivadas.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Considere la posibilidad de establecer la moderación en sus canales

Los propietarios de los equipos pueden activar la moderación de un canal para controlar quién puede iniciar nuevos mensajes y responder a los mensajes de ese canal. Cuando establezca la moderación, puede elegir a uno o más miembros del equipo para que sean moderadores. De forma predeterminada, los propietarios de equipos son moderadores. Para obtener más información, [vea Configurar y administrar la moderación de canales.](manage-channel-moderation-in-teams.md)

## <a name="related-topics"></a>Temas relacionados

- [Procedimientos recomendados para organizar Teams](best-practices-organizing.md)
- [Crear un equipo para toda la organización](create-an-org-wide-team.md)
