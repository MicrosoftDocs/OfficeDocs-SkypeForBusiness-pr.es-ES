---
title: 'Administrar equipos grandes en Microsoft Teams: procedimientos recomendados'
ms.reviewer: abgupta
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Obtenga información sobre los procedimientos recomendados para administrar equipos grandes en Microsoft Teams para satisfacer las necesidades de su organización.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- chat-teams-channels-revamp
ms.openlocfilehash: fddf4b5cf80c51977b2a57ceceac8a07e529c51f
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199082"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Administrar equipos grandes en Microsoft Teams: procedimientos recomendados

Microsoft Teams es igualmente eficaz para facilitar las comunicaciones entre pequeños grupos con decenas de miembros y grandes grupos con miles de miembros. Revise [los límites y las especificaciones de Teams para](limits-specifications-teams.md) ver las actualizaciones de los tamaños de los equipos. El aumento del tamaño del equipo conduce a desafíos operativos y de gestión únicos. En este artículo se describen los procedimientos recomendados para crear y administrar equipos grandes compuestos por miles de miembros.

## <a name="value-of-large-teams"></a>Valor de los equipos grandes

Los equipos grandes son muy útiles para habilitar los siguientes escenarios de colaboración:

- **Colaboración en todo el departamento**: si su organización tiene varios departamentos, como Finanzas, Operaciones, R&D, etc., puede crear un único equipo que incluya a todos los miembros de un departamento específico. Ahora todas las comunicaciones relevantes para un departamento se pueden compartir en este equipo, lo que facilita el alcance instantáneo y la participación de los miembros.

- **Colaboración en grupos de recursos de empleados**: las organizaciones suelen tener grandes grupos de personas con intereses mutuos que pertenecen a otro departamento o grupo de trabajo. Por ejemplo, puede haber un grupo de personas que comparten la pasión por las finanzas personales y la inversión. A menudo es difícil conectarse en una organización grande. Para desarrollar comunidades para estos grupos, los administradores de inquilinos pueden crear un equipo grande que sirva como un grupo de recursos público para toda la empresa al que cualquier persona pueda unirse y aprovechar. Finalmente, estas comunidades recopilan información que pueden disfrutar tanto los miembros nuevos como los existentes.

- **Colaboración entre miembros internos y externos**: los productos populares suelen desarrollar una comunidad de usuarios pioneros que están ansiosos por probar nuevas versiones de productos y proporcionar comentarios. Los usuarios pioneros desarrollan una relación con los grupos de productos para ayudar a dar forma al producto. En estos escenarios, los administradores de inquilinos pueden configurar un equipo grande que incluya grupos de productos internos y evaluadores de productos externos para facilitar un proceso de desarrollo de productos enriquecido. Estos equipos también pueden proporcionar asistencia al cliente a un conjunto seleccionado de clientes.

## <a name="create-teams-from-existing-groups"></a>Crear equipos a partir de grupos existentes

Use grupos de contactos, grupos de seguridad o grupos de Office para iniciar el equipo. Puede importar un grupo para crear un equipo o crear uno desde un grupo de Office.

**Importar un grupo para crear un equipo**: al importar un grupo con hasta 3500 miembros a Teams, Teams calcula automáticamente el número total de miembros del grupo. Se trata de una importación única y los futuros cambios en el grupo no se actualizarán automáticamente en Teams.

**Crear un equipo a partir de un gran grupo de Microsoft 365**: al crear un equipo a partir de un grupo grande Microsoft 365, los miembros forman automáticamente parte del grupo Microsoft 365 **y** del equipo. En el futuro, a medida que los miembros del equipo se unan o abandonen el grupo de Microsoft 365, se agregarán o quitarán automáticamente del equipo.

## <a name="bulk-importexportremove-members-in-a-team"></a>Importar, exportar o quitar miembros en masa en un equipo

La Azure Portal permite a los usuarios importar, exportar o quitar miembros en masa en un grupo de Microsoft 365. Para obtener más información, vea [To bulk import group members (Para importar en masa miembros del grupo](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)).

Como cada equipo está respaldado por un grupo de Microsoft 365, puede usar el Azure Portal para realizar estas operaciones en el grupo correspondiente al equipo. Las operaciones de los miembros se reflejarán en el equipo en 24 horas.

## <a name="create-channels-to-focus-discussions"></a>Crear canales para enfocar los debates

Puede restringir las discusiones de grupo creando canales enfocados. Consulte [Procedimientos recomendados para organizar equipos](best-practices-organizing.md).

## <a name="restrict-channel-creation"></a>Restringir la creación de canales

Si cualquier miembro del equipo puede crear canales, ese equipo puede tener un expansión de canales. Los propietarios de equipos deben desactivar la creación, actualización, eliminación y restauración de canales para los miembros en **Configuración > Permisos de miembros**. Consulte [Información general sobre equipos y canales](teams-channels-overview.md).

![Imagen de pantalla que muestra la sección de permisos de miembro de la pestaña Configuración de la consola de administración.](media/no-channel-creation.png "Imagen de pantalla que la sección de permisos de los miembros de la pestaña Configuración de la consola de administración. Las opciones permitir que los miembros creen o eliminen canales no están activadas.")

## <a name="add-favorite-channels"></a>Agregar canales favoritos

Para acelerar la participación de los nuevos usuarios y la detección de contenido, puede seleccionar los canales favoritos que están disponibles para el usuario de forma predeterminada. En el panel **Canales** del centro de administración, compruebe los canales en la columna **Mostrar para miembros** .

![Imagen de pantalla que muestra el panel de canales de la consola de administración.](media/favorite-channels.png "Imagen de pantalla que muestra el panel de canales de la consola de administración. Algunos canales están marcados como Mostrar para miembros.")

 Consulte [Crear sus primeros equipos y canales](get-started-with-teams-create-your-first-teams-and-channels.md) para obtener más información.

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regular las aplicaciones y los bots en equipos grandes

Para evitar que se agreguen bots o aplicaciones que distraigan, los propietarios del equipo pueden deshabilitar, agregar, quitar y cargar aplicaciones y conectores para los miembros del equipo. En el Centro de administración, en **Configuración > Permisos de miembros**, desactive las tres opciones que permiten a los miembros agregar aplicaciones o conectores.

![Imagen de pantalla que muestra la sección Permisos de miembro del panel Configuración.](media/disable-bots-connectors.png "Imagen de pantalla que muestra la sección Permisos de miembro del panel Configuración. Las opciones para permitir que los miembros agreguen aplicaciones o conectores están desactivadas.")

Consulte [información general sobre las aplicaciones de Teams](deploy-apps-microsoft-teams-landing-page.md).

## <a name="regulate-team-and-channel-mentions"></a>Regular las menciones de equipos y canales

Las menciones de equipos y canales se pueden usar para llamar la atención de todo el equipo sobre determinadas publicaciones del canal. Una vez que se usa una mención en una publicación, se envía una notificación a miles de miembros del equipo. Si las notificaciones son demasiado frecuentes, los miembros del equipo pueden sobrecargarse y pueden quejarse a los propietarios del equipo. Para evitar las menciones de equipos o canales, desactive las menciones de equipos y canales para los miembros desactivando las casillas en el panel **de > @mentions configuración** de equipos.

![Imagen de pantalla que muestra la sección en Menciones del panel Configuración.](media/no-at-mentions.png "Imagen de pantalla que muestra la sección en Menciones del panel Configuración. Las opciones para mostrar y conceder acceso a los miembros en menciones no están activadas.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Considere la posibilidad de establecer la moderación en sus canales

Los propietarios de los equipos pueden activar la moderación de un canal para controlar quién puede iniciar nuevos mensajes y responder a los mensajes de ese canal. Cuando establezca la moderación, puede elegir a uno o más miembros del equipo para que sean moderadores. Los propietarios de equipos son moderadores de forma predeterminada. Para obtener más información, vea [Configurar y administrar la moderación del canal](manage-channel-moderation-in-teams.md).

## <a name="related-topics"></a>Temas relacionados

- [Procedimientos recomendados para organizar Teams](best-practices-organizing.md)
- [Crear un equipo para toda la organización](create-an-org-wide-team.md)