---
title: 'Administrar equipos grandes en Microsoft Teams: procedimientos recomendados'
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Obtenga más información sobre los procedimientos recomendados para administrar equipos grandes en Microsoft Teams para satisfacer las necesidades de su organización.
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

Microsoft Teams es igualmente eficaz para facilitar la comunicación entre grupos pequeños con docenas de miembros y grupos grandes con miles de miembros. Revise los [límites y las especificaciones de Teams](limits-specifications-teams.md) para obtener actualizaciones de los tamaños de equipo. El aumento en el tamaño del equipo conlleva desafíos únicos de administración y operativos. Este artículo describe los procedimientos recomendados para crear y administrar equipos grandes compuestos por miles de miembros.

## <a name="value-of-large-teams"></a>Valor de equipos grandes

Los equipos grandes son muy útiles para habilitar los siguientes escenarios de colaboración:

- **Colaboración en todo el Departamento**: Si su organización tiene varios departamentos, como finanzas, operaciones, R&D, etc., puede crear un único equipo que incluya a todos los miembros de un departamento específico. Ahora todas las comunicaciones relacionadas con un departamento pueden compartirse en este equipo, lo que facilita el acceso instantáneo y la participación de miembros.

- **Colaboración en grupos de recursos para empleados**: a menudo, las organizaciones tienen grupos grandes de personas con intereses mutuos que pertenecen a otro departamento o grupo de trabajo. A modo de ejemplo, puede haber un grupo de personas que comparten una pasión por la financiación personal y la inversión. A menudo es difícil conectarse en una organización grande. Para desarrollar comunidades para esos grupos, los administradores de espacios empresariales pueden crear un gran equipo que sirva como grupo de recursos de toda la empresa al que cualquier persona se pueda unir y aprovechar. Finalmente, estas comunidades recopilan información que pueden disfrutar tanto de miembros nuevos como de miembros existentes.

- **Colaboración entre miembros internos y externos**: los productos populares a menudo desarrollan una comunidad de primeros usuarios que desean probar nuevas versiones de productos y enviar comentarios. Los primeros pioneros desarrollan una relación con los grupos de productos para ayudar a dar forma al producto. En estos casos, los administradores de inquilinos pueden configurar un equipo grande que incluya tanto los grupos de productos internos como los evaluadores de producto externos para facilitar un completo proceso de desarrollo de productos. Estos equipos también pueden ofrecer asistencia al cliente a un conjunto seleccionado de clientes.

## <a name="create-teams-from-existing-groups"></a>Crear equipos a partir de grupos existentes

Use grupos de contactos, grupos de seguridad o grupos de Office para iniciar el equipo. Puede importar un grupo para crear un equipo o crear un equipo desde un grupo de Office.

**Importar un grupo para crear un equipo**: Cuando importa un grupo con un máximo de 3.500 miembros a Teams, Teams calcula automáticamente el número total de miembros del grupo. Esta es una importación única y los cambios futuros del grupo no se actualizarán automáticamente en Teams.

**Crear un equipo a partir de un grupo grande de microsoft 365**: cuando se crea un equipo a partir de un grupo de Microsoft 365 de gran tamaño, los miembros forman parte automáticamente del grupo Microsoft 365 **y** del equipo. En el futuro, a medida que los miembros del equipo se unen o salen del grupo de Microsoft 365, se agregan o quitan automáticamente del equipo.

## <a name="create-channels-to-focus-discussions"></a>Crear canales para enfocar los debates

Puede restringir las discusiones grupales creando canales prioritarios. Vea [procedimientos recomendados para organizar equipos](best-practices-organizing.md).

## <a name="restrict-channel-creation"></a>Restringir la creación de canales

Si se permite a algún miembro del equipo crear canales, ese equipo puede tener la proliferación de canales. Los propietarios de equipos deben desactivar el canal: crear, actualizar, eliminar y restaurar para miembros en **configuración > permisos de miembro**. Consulte [información general de los equipos y los canales](teams-channels-overview.md).

![Imagen de la pantalla que muestra la sección permisos de miembro de la pestaña Configuración de la consola de administración.](media/no-channel-creation.png "Imagen de la sección permisos de miembros de la pestaña Configuración de la consola de administración. Las opciones permitir a los miembros crear o eliminar canales están desactivadas.")

## <a name="add-favorite-channels"></a>Agregar canales favoritos

Para acelerar la negociación de nuevos usuarios y el descubrimiento de contenido, puede seleccionar canales favoritos que estén disponibles para el usuario de forma predeterminada. En el panel **canales** del centro de administración, compruebe los canales en la columna **Mostrar para miembros** .

![Imagen en pantalla que muestra el panel canales de la consola de administración.](media/favorite-channels.png "Imagen de pantalla que muestra el panel de canales de la consola de administración. Algunos canales están marcados para mostrar a los miembros.")

 Para obtener más información [, consulte crear sus primeros equipos y canales](get-started-with-teams-create-your-first-teams-and-channels.md) .

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regular las aplicaciones y los bots en equipos grandes

Para evitar agregar aplicaciones o bots que distraigan, los propietarios del equipo pueden deshabilitar, agregar, quitar y cargar aplicaciones y conectores para los miembros del equipo. En el centro de administración, en **configuración > permisos**de los miembros, desactive las tres opciones que permiten a los miembros agregar aplicaciones o conectores.

![Imagen de la pantalla que muestra la sección permisos de miembro del panel Configuración.](media/disable-bots-connectors.png "Imagen de la pantalla que muestra la sección de permisos de miembro del panel Configuración. Las opciones para permitir que los miembros puedan agregar aplicaciones o conectores están desactivadas.")

Consulte [aplicaciones, bots, conectores de &](deploy-apps-microsoft-teams-landing-page.md).

## <a name="regulate-team-and-channel-mentions"></a>Regular las menciones de los canales y el equipo

Las menciones para el equipo y el canal se pueden usar para atraer la atención de todo el equipo a determinadas publicaciones de canales. Una vez que se usa una mención en una publicación, se envía una notificación a miles de miembros del equipo. Si las notificaciones son demasiado frecuentes, los miembros del equipo pueden sobrecargarse y podrían quejarse a los propietarios del equipo. Para evitar las menciones en el canal o el equipo, desactive las menciones de canales y equipos de los miembros desactivando las casillas de la configuración de Teams > panel de **@mentions** .

![Imagen de pantalla que muestra la sección de menciones en el panel de configuración.](media/no-at-mentions.png "Imagen de pantalla que muestra la sección de menciones en el panel de configuración. Las opciones para mostrar y conceder acceso a los miembros a las menciones están desactivadas.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Considere la posibilidad de establecer la moderación en sus canales

Los propietarios de los equipos pueden activar la moderación de un canal para controlar quién puede iniciar nuevos mensajes y responder a los mensajes de ese canal. Cuando establezca la moderación, puede elegir a uno o más miembros del equipo para que sean moderadores. Los propietarios de equipo son moderadores de forma predeterminada. Para obtener más información, vea [configurar y administrar la moderación de canales](manage-channel-moderation-in-teams.md).

## <a name="related-topics"></a>Temas relacionados

- [Procedimientos recomendados para organizar equipos](best-practices-organizing.md)
- [Crear un equipo para toda la organización](create-an-org-wide-team.md)
