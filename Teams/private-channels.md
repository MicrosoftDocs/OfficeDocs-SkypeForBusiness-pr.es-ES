---
title: Canales privados en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar canales privados en Microsoft Teams.
ms.openlocfilehash: 45d05f2dd726b340ac79ac11810d23d00c8b3e9d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837320"
---
# <a name="private-channels-in-microsoft-teams"></a>Canales privados en Microsoft Teams

Los canales privados de Microsoft Teams crean espacios prioritarios para la colaboración dentro de los equipos. Solo los usuarios del equipo que sean propietarios o miembros del canal privado pueden acceder al canal. Cualquier persona, incluidos los invitados, se puede agregar como miembro de un canal privado siempre que ya sean miembros del equipo.

Es posible que desee usar un canal privado si desea limitar la colaboración a aquellos que necesiten saber o si desea facilitar la comunicación entre un grupo de personas asignado a un proyecto específico, sin tener que crear un equipo adicional para administrar.

Por ejemplo, un canal privado es útil en estos escenarios:

- Un grupo de personas de un equipo desea tener un espacio prioritario para colaborar sin tener que crear un equipo independiente.
- Un subconjunto de personas de un equipo desea un canal privado para analizar información confidencial, como presupuestos, reaprovisionamiento, posicionamiento estratégico, etc.

Un icono de candado indica un canal privado. Solo los miembros de canales privados pueden ver y participar en canales privados a los que se agregan.

![Captura de pantalla de canales privados en un equipo](media/private-channels-in-teams.png)

## <a name="what-you-need-to-know-about-private-channels"></a>Lo que debe saber sobre los canales privados

Actualmente, los canales privados admiten conectores y fichas (excepto Stream, Planner y Forms). Estamos trabajando en la compatibilidad de aplicaciones completas para canales privados, incluidas las extensiones de mensajería y los bots.

Cada equipo puede tener un máximo de 30 canales privados y cada canal privado puede tener un máximo de 250 miembros. El límite de 30 canales privados se suma al límite de canales estándar de 200 por equipo.

> [!NOTE]
> Continuamente agregamos capacidades a los canales privados, de modo que vuelva a consultar la información más actualizada sobre aplicaciones, reuniones de canal y escala de canales privados para equipos grandes.

## <a name="when-to-create-a-private-channel"></a>Cuándo crear un canal privado

Para determinar si un canal privado es adecuado, tenga en cuenta las siguientes preguntas acerca de quién debe trabajar juntos y de qué trata la colaboración.

|¿Ya hay un equipo que tiene a estas personas como miembros del equipo?  |¿Este trabajo debe mantenerse en privado de los demás?  |¿Hay varios temas distintos que se deben discutir?  |Recomendación  |
|---------|---------|---------|---------|
|Sí       |Sí          |Sí          |Crear un canal privado en el equipo existente o considerar la creación de canales privados específicos para cada tema.         |
|Sí      |Sí         |No         |Crear un canal privado en el equipo existente.         |
|Sí     |No         |No         |Crear un canal en el equipo existente.         |
|No     |No         |No         |Considere la posibilidad de crear un equipo nuevo.         |
|No     |No         |Sí         |Considere la posibilidad de crear un equipo nuevo y, en función de la confidencialidad de cada tema, considere la posibilidad de crear canales estándar o privados independientes para cada tema.         |
|No     |Sí         |No         |Cree un nuevo equipo o cree un nuevo canal privado en un equipo existente.         |

Cuando se crea un canal privado, está vinculado al equipo principal y no se puede mover a otro equipo. Además, los canales privados no se pueden convertir en canales estándar y viceversa.

## <a name="private-channel-creation-and-membership"></a>Creación y pertenencia a canales privados

### <a name="who-can-create-private-channels"></a>¿Quién puede crear canales privados?

De forma predeterminada, cualquier propietario del equipo o miembro del equipo puede crear un canal privado. Los invitados no pueden crearlos. La capacidad de crear canales privados se puede administrar en el nivel de equipo y en el nivel de la organización:

- En la pestaña **configuración** de un equipo, los propietarios del equipo pueden desactivar o activar la posibilidad de que los miembros creen canales privados.
- Como administrador, puede usar [directivas](teams-policies.md) para controlar los usuarios de su organización que tienen permitido crear canales privados.

La persona que crea un canal privado es el propietario del canal privado y solo el propietario del canal privado puede Agregar o quitar personas directamente de él. Un propietario de canal privado puede agregar cualquier miembro del equipo a un canal privado que haya creado, incluidos los invitados. Los miembros de un canal privado tienen un espacio de conversación seguro y, cuando se agregan nuevos miembros, pueden ver todas las conversaciones (incluso las antiguas) en ese canal privado.

### <a name="what-happens-when-a-team-member-leaves-or-is-removed-from-a-team"></a>¿Qué sucede cuando un miembro del equipo abandona o se elimina de un equipo?

Si un miembro del equipo abandona o se elimina de un equipo, ese usuario también saldrá o se eliminará de todos los canales privados del equipo. Si el usuario vuelve a agregarse al equipo, debe volver a agregarse a los canales privados del equipo.

### <a name="what-happens-when-a-private-channel-owner-is-removed-from-a-private-channel"></a>¿Qué sucede cuando se quita un propietario de canal privado de un canal privado?

Un propietario de canal privado no se puede quitar a través del cliente de Teams si es el último propietario de uno o más canales privados.

Si un propietario de un canal privado abandona su organización o se quita del grupo de Office 365 asociado al equipo, un miembro del canal privado se promueve automáticamente al propietario del canal privado.

### <a name="what-can-team-owners-and-team-members-see-in-a-private-channel"></a>¿Qué pueden ver los propietarios del equipo y los miembros del equipo en un canal privado?

Los propietarios de equipo pueden ver los nombres de todos los canales privados de su equipo y también pueden eliminar cualquier canal privado del equipo. (Un canal privado eliminado puede restaurarse en un plazo de 30 días A partir de la eliminación). Los propietarios del equipo no pueden ver los archivos en un canal privado o en las conversaciones y la lista de miembros de un canal privado, a menos que sean miembros de ese canal privado.

En la tabla siguiente se muestra quién puede ver qué en un canal privado.

|Elemento  |Propietario del equipo puede ver |Los miembros del equipo pueden ver |
|---------|---------|---------|
|Nombre y descripción    |Todos los canales privados en el equipo         |Solo los canales privados a los que se agregan         |
|Conversaciones y pestañas     |Solo cuando se agrega al canal privado         |Solo cuando se agrega al canal privado         |
|Archivos y contenido    |Solo cuando se agrega al canal privado        |Solo cuando se agrega al canal privado         |
|Propietario del canal privado    |Todos los canales privados en el equipo        |Solo cuando se agrega al canal privado         |
|Marca de tiempo de la última actividad  |Todos los canales privados en el equipo       |Solo cuando se agrega al canal privado         |

## <a name="manage-private-channels"></a>Administrar canales privados

En la tabla siguiente se describen las acciones que pueden realizar los propietarios, los miembros y los invitados en los canales privados.

|Acción  |Propietario del equipo|Miembro del equipo|Invitado del equipo|Propietario del canal privado|Miembro de canal privado|Invitado de canal privado|
|---------|---------|---------|---------|---------|---------|---------|
|Crear un canal privado|Sí<sup>1</sup>|Sí<sup>, 1, 2</sup>|No|N/D|N/D|N/D|
|Eliminar canal privado|Sí|No|No|Sí|No|No|
|Abandonar canal privado|N/D|N/D|N/D|Sí<sup>3</sup>|Sí |Sí |
|Editar canal privado|No|N/D|N/D|Sí|No|No|
|Restaurar el canal privado eliminado|Sí|No|No|Sí|No|No|
|Agregar miembros|No|N/D|N/D|Sí|No|No|
|Editar configuración|No|N/D|N/D|Sí|No|No|
|Administrar pestañas y aplicaciones|No|N/D|N/D|Yes<sup>4</sup>|Sí<sup>5</sup>|No|

<sup>1</sup> suponiendo que la Directiva que usted, el administrador, configure permita al usuario crear canales privados.<br>
<sup>2</sup> cada equipo tiene una configuración que los propietarios del equipo pueden activar o desactivar para permitir que los miembros del equipo creen canales privados. Los propietarios del equipo siempre pueden crear canales privados.<br>
<sup>3</sup> suponiendo que el propietario del canal privado no es el último propietario del canal. <br>
<sup>4</sup> requiere que el equipo tenga instalada una aplicación para que un canal privado la use.<br>
<sup>5</sup> los propietarios de canales privados pueden configurarlo.

### <a name="manage-private-channel-membership-and-settings"></a>Administrar la pertenencia y la configuración de canales privados

Cada canal privado tiene su propia configuración, incluida la capacidad de agregar y quitar miembros, agregar pestañas y @mentioning para todo el canal. Esta configuración es independiente de la configuración del equipo principal. Cuando se crea un canal privado, hereda la configuración del equipo principal, después de la cual se puede cambiar la configuración de forma independiente de la configuración del equipo principal.

El propietario del canal privado puede hacer clic en **administrar canal**y, a continuación, usar las pestañas de **miembros** y **configuración** para agregar o quitar miembros y editar la configuración.  

![Captura de pantalla de configuración de canal privado](media/private-channels-in-teams-channel-settings.png)

## <a name="manage-the-life-cycle-of-private-channels"></a>Administrar el ciclo de vida de los canales privados

Consulte [administrar el ciclo de vida de canales privados en Teams](private-channels-life-cycle-management.md) para obtener información sobre cómo administrar el ciclo de vida de los canales privados de su organización. Esto incluye cómo controlar si los usuarios de su organización pueden crear canales privados, cómo crear un canal privado en nombre de un propietario del equipo, cómo obtener una lista de todos los mensajes de canal privado para archivar y auditar, y otras tareas de administración.  

## <a name="private-channel-sharepoint-sites"></a>Sitios de SharePoint de canal privado

Cada canal privado tiene su propia colección de sitios de SharePoint optimizada para el uso compartido de archivos y el aprovisionamiento rápido. La colección de sitios independiente es asegurarse de que el acceso a los archivos de canal privado está restringido solo a miembros del canal privado en comparación con el sitio de grupo en el que los propietarios del equipo tienen acceso a todos los activos de la colección de sitios. Estas colecciones de sitios se crean con una biblioteca de documentos de forma predeterminada y se pueden mejorar fácilmente en una colección de sitios completa a través de la [interfaz de administración de sitios](https://support.office.com/article/Enable-or-disable-site-collection-features-A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Cada colección de sitios se crea en la misma región geográfica que la colección de sitios del equipo principal. Estos sitios livianos tienen un identificador de plantilla personalizado, "TEAMCHANNEL # 0", para facilitar la administración a través de la API de PowerShell y Graph.  Por diseño, no están visibles en el centro de administración de SharePoint.

Para dar cabida a un número mayor de colecciones de sitios por inquilino, el límite ha aumentado de 500.000 a 2 millones. Una colección de sitios de canal privado sincroniza la clasificación de los datos y hereda los permisos de acceso de invitado de la colección de sitios del equipo principal.  La pertenencia a los grupos de miembros y el propietario de la colección de sitios se mantiene sincronizada con la pertenencia del canal privado dentro de Teams. Cualquier cambio en la pertenencia al propietario o los grupos de miembros de SharePoint Online se revertirá a la pertenencia a un canal privado dentro de cuatro horas automáticamente. En escenarios en los que determinados usuarios necesitan obtener acceso a documentos sin necesidad de tener acceso a los mensajes de canal privado, agréguelos al grupo visitantes del sitio o a un grupo nuevo que sea independiente de propietarios y miembros.

Teams administra el ciclo de vida de la colección de sitios de SharePoint del canal privado. Si la colección de sitios se elimina fuera de Teams, un trabajo en segundo plano restaura el sitio dentro de un plazo de cuatro horas, siempre que el canal privado aún esté activo. Si el sitio se elimina y se elimina de forma rígida, se aprovisionará una nueva colección de sitios para el canal privado.

Si se restaura un canal privado o un equipo que contiene un canal privado, se restauran las colecciones de sitios con él. Si se restaura una colección de sitios de canal privado y esta fuera de la ventana de eliminación de software de 30 días para el canal privado, la colección de sitios funciona como una colección de sitios independiente.

## <a name="private-channel-message-compliance-records"></a>Registros de cumplimiento de mensajes de canal privado

Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo. El formato de los títulos de los registros indica el canal privado desde el que se enviaron.

Para obtener más información sobre cómo realizar una búsqueda de exhibición de mensajes en el canal privado, consulte [eDiscovery of Private Channels](ediscovery-investigation.md#ediscovery-of-private-channels).

## <a name="considerations-around-access-in-private-channels"></a>Consideraciones sobre el acceso en canales privados

Cuando se crea un bloc de notas de OneNote en un canal privado, los usuarios adicionales pueden obtener acceso al bloc de notas porque el comportamiento es el mismo que compartir el acceso a cualquier otro elemento de un sitio de SharePoint de canal privado con un usuario.

Si a un usuario se le concede acceso a un bloc de notas en un canal privado a través de SharePoint, al quitar el usuario del equipo o del canal privado, no se quitará el acceso del usuario al bloc de notas.

Si se agrega un bloc de notas existente como una pestaña a un canal privado, no se cambiará el acceso al canal privado. Esto significa lo siguiente:

- No todos los usuarios del canal privado tendrán acceso al bloc de notas de forma predeterminada. Esto se debe a que es posible que no tengan acceso a dónde se hospeda el Bloc de notas, como el sitio de SharePoint de otro equipo.
- Los usuarios que no son miembros del canal privado pueden ver el Bloc de notas.  

## <a name="related-topics"></a>Temas relacionados

- [Información general de los equipos y canales en Microsoft Teams](teams-channels-overview.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
- [Usar la API de Microsoft Graph para trabajar con equipos](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
