---
title: 'Administrar equipos grandes en Microsoft Teams: procedimientos recomendados'
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Obtenga información sobre los procedimientos recomendados para administrar equipos grandes Microsoft Teams para satisfacer las necesidades de su organización.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fff84bd660eb19f01c6a7e3388f5289b09896401
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856349"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Administrar equipos grandes en Microsoft Teams: procedimientos recomendados

Microsoft Teams es igualmente eficaz para facilitar las comunicaciones entre grupos pequeños con docenas de miembros y grupos grandes con miles de miembros. Revise [Los límites y las especificaciones Teams](limits-specifications-teams.md) para las actualizaciones de los tamaños de equipo. El aumento del tamaño del equipo lleva a desafíos operativos y de administración únicos. En este artículo se describen los procedimientos recomendados para crear y administrar equipos grandes compuestos por miles de miembros.

## <a name="value-of-large-teams"></a>Valor de los equipos grandes

Los equipos grandes son muy útiles para habilitar los siguientes escenarios de colaboración:

- **Colaboración** en todo el departamento: si su organización tiene varios departamentos, como Finanzas, Operaciones, R&D, etc., puede crear un único equipo que incluya a todos los miembros de un departamento específico. Ahora todas las comunicaciones relevantes para un departamento se pueden compartir en este equipo, lo que facilita el acceso instantáneo y la participación de los miembros.

- **Colaboración en grupos de recursos de** empleados: las organizaciones suelen tener grandes grupos de personas con intereses mutuos que pertenecen a un departamento o grupo de trabajo diferente. Como ejemplo, puede haber un grupo de personas que comparten una pasión por las finanzas personales y la inversión. A menudo es difícil conectarse en una organización grande. Para desarrollar comunidades para estos grupos, los administradores de inquilinos pueden crear un equipo grande que actúa como un grupo de recursos de toda la empresa pública al que cualquier usuario puede unirse y aprovechar. Con el tiempo, estas comunidades recopilan información de la que pueden disfrutar tanto los miembros nuevos como los existentes.

- **Colaboración entre miembros** internos y externos: los productos populares a menudo desarrollan una comunidad de primeros usuarios que están ansiosos por probar nuevas versiones de productos y proporcionar comentarios. Los primeros usuarios desarrollan una relación con grupos de productos para ayudar a dar forma al producto. En estos escenarios, los administradores de inquilinos pueden configurar un equipo grande que incluya tanto grupos de productos internos como evaluadores de productos externos para facilitar un proceso de desarrollo de productos enriquecido. Estos equipos también pueden proporcionar asistencia al cliente a un conjunto selecto de clientes.

## <a name="create-teams-from-existing-groups"></a>Crear equipos a partir de grupos existentes

Use grupos de contactos, grupos de seguridad o Office para iniciar el equipo. Puede importar un grupo para crear un equipo o crear un equipo desde un Office grupo.

**Importar un** grupo para crear un equipo: al importar un grupo con hasta 3.500 miembros a Teams, Teams calcula automáticamente el número total de miembros del grupo. Se trata de una importación única y los cambios futuros en el grupo no se actualizarán automáticamente en Teams.

**Crear un** equipo a partir de un grupo de Microsoft 365 grande: al crear un equipo a partir de un grupo de Microsoft 365 grande, los miembros forman automáticamente parte del grupo Microsoft 365 y **del** equipo. En el futuro, a medida que los miembros del equipo se unen o abandonan el grupo Microsoft 365, se agregan o quitan automáticamente del equipo.

## <a name="bulk-importexportremove-members-in-a-team"></a>Importar, exportar o quitar miembros en masa en un equipo

Azure Portal permite a los usuarios importar, exportar o quitar miembros en masa en un Microsoft 365 grupo. Para obtener más información, vea [Importar en masa los miembros del grupo.](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)

Puesto que cada equipo cuenta con el respaldo de un grupo de Microsoft 365, puede usar Azure Portal para realizar estas operaciones en el grupo correspondiente al equipo. Las operaciones de miembro se reflejarán en el equipo en un plazo de 24 horas.

## <a name="create-channels-to-focus-discussions"></a>Crear canales para enfocar los debates

Puede restringir las discusiones de grupo creando canales centrados. Vea [Procedimientos recomendados para organizar equipos.](best-practices-organizing.md)

## <a name="restrict-channel-creation"></a>Restringir la creación de canales

Si se permite a cualquier miembro del equipo crear canales, ese equipo puede tener una expansión del canal. Los propietarios del equipo deben desactivar la creación, actualización, eliminación y restauración del canal para los miembros **Configuración > miembros.** Vea [Información general sobre equipos y canales.](teams-channels-overview.md)

![Imagen de pantalla que muestra la sección de permisos de miembro de la consola de administración Configuración pestaña.](media/no-channel-creation.png "Imagen de pantalla de la sección permisos de miembro de la consola de administración Configuración pestaña. Las opciones permitir a los miembros crear o eliminar canales están desactivadas.")

## <a name="add-favorite-channels"></a>Agregar canales favoritos

Para acelerar la nueva participación del usuario y la detección de contenido, puede seleccionar los canales favoritos que están disponibles para el usuario de forma predeterminada. En el **panel Canales** del centro de administración, compruebe los canales en la **columna Mostrar para** miembros.

![Imagen de pantalla que muestra el panel de canales de la consola de administración.](media/favorite-channels.png "Imagen de pantalla que muestra el panel de canales de la consola de administración. Algunos canales están activados para Mostrar para los miembros.")

 Vea [Crear los primeros equipos y canales para](get-started-with-teams-create-your-first-teams-and-channels.md) obtener más información.

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regular aplicaciones y bots en equipos grandes

Para evitar la adición de aplicaciones o bots que distraigan, los propietarios de equipos pueden deshabilitar, agregar, quitar y cargar aplicaciones y conectores para los miembros del equipo. En el centro de administración **Configuración > permisos** de miembro, desactive las tres opciones que permiten a los miembros agregar aplicaciones o conectores.

![Imagen de pantalla que muestra la sección Permisos de miembro del Configuración usuario.](media/disable-bots-connectors.png "Imagen de pantalla que muestra la sección Permisos de miembro del Configuración panel. Las opciones para permitir que los miembros agreguen aplicaciones o conectores están desactivadas.")

Vea [Aplicaciones, bots, & conectores](deploy-apps-microsoft-teams-landing-page.md).

## <a name="regulate-team-and-channel-mentions"></a>Regular las menciones de equipo y canal

Las menciones de equipo y canal se pueden usar para llamar la atención de todo el equipo a determinadas publicaciones del canal. Una vez que se usa una mención en una publicación, se envía una notificación a miles de miembros del equipo. Si las notificaciones son demasiado frecuentes, los miembros del equipo pueden sobrecargarse y pueden quejarse ante los propietarios del equipo. Para evitar las menciones de equipo o canal, desactive las menciones de equipo **y** canal para los miembros desactivando las casillas del panel de Configuración > @mentions equipos.

![Imagen de pantalla que muestra la sección En menciones del Configuración pantalla.](media/no-at-mentions.png "Imagen de pantalla que muestra la sección En menciones del Configuración pantalla. Las opciones para mostrar y dar acceso a los miembros en las menciones están desactivadas.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Considere la posibilidad de establecer la moderación en sus canales

Los propietarios de los equipos pueden activar la moderación de un canal para controlar quién puede iniciar nuevos mensajes y responder a los mensajes de ese canal. Cuando establezca la moderación, puede elegir a uno o más miembros del equipo para que sean moderadores. Los propietarios de equipos son moderadores de forma predeterminada. Para obtener más información, vea [Configurar y administrar la moderación del canal.](manage-channel-moderation-in-teams.md)

## <a name="related-topics"></a>Temas relacionados

- [Procedimientos recomendados para organizar Teams](best-practices-organizing.md)
- [Crear un equipo para toda la organización](create-an-org-wide-team.md)