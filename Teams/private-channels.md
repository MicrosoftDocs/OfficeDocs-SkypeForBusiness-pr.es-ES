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
description: Obtenga información acerca de cómo usar y administrar canales privados en Microsoft Teams.
ms.openlocfilehash: 54fd36bd78f1d9ea263fe3e79a3d12a08741c389
ms.sourcegitcommit: 8acc2ed4cb807f941a6526ec8aad562536f45aa6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44804694"
---
# <a name="private-channels-in-microsoft-teams"></a>Canales privados en Microsoft Teams

Los canales privados de Microsoft Teams crean espacios prioritarios para la colaboración de los equipos. Solo los usuarios del equipo que sean propietarios o miembros del canal privado podrán acceder al canal. Cualquier persona, incluidos los invitados, puede agregarse como miembro de un canal privado siempre y cuando ya sean miembros del equipo.

Un canal privado puede ser útil para limitar la colaboración a solo aquellos usuarios que necesitan conocer una información o para facilitar la comunicación entre un grupo de personas asignadas a un proyecto específico, sin tener que crear un equipo adicional para administrar.

Por ejemplo, un canal privado es útil en estos escenarios:

- Un grupo de personas en un equipo desean un espacio prioritario para colaborar sin tener que crear un equipo independiente.
- Un subconjunto de usuarios de un equipo desea un canal privado para analizar información confidencial, como presupuestos, reabastecimiento, colocación estratégica, etc.

Un icono de bloqueo indica un canal privado. Solo los miembros de canales privados pueden ver y participar en canales privados a los que se agregan.

![Captura de pantalla de canales privados en un equipo](media/private-channels-in-teams.png)

## <a name="what-you-need-to-know-about-private-channels"></a>Todo lo que debe saber sobre canales privados

Actualmente, los canales privados son compatibles con conectores y pestañas (excepto Stream, Planner y Forms). Estamos trabajando para brindarle soporte completo de aplicaciones para canales privados, incluidas extensiones de mensajería y bots.

Cada equipo puede tener un máximo de 30 canales privados y cada canal privado puede tener un máximo de 250 miembros. El límite de 30 canales privados es adicional al límite de 200 canales estándar por equipo. 

Al crear un equipo a partir de un equipo existente, los canales privados del equipo existente no se copiarán.


> [!NOTE]
> Continuamente estamos agregando capacidades a los canales privados, así que revise para obtener la información más actualizada sobre aplicaciones, reuniones de canales y escalar canales privados para equipos grandes.

## <a name="when-to-create-a-private-channel"></a>Cuándo crear un canal privado

Para determinar si un canal privado es adecuado, tenga en cuenta las siguientes dudas sobre quién tiene que trabajar conjuntamente y en qué consiste la colaboración.

|¿Ya hay un equipo que tiene estos usuarios como miembros del equipo?  |¿Es necesario mantener el trabajo privado de otras personas?  |¿Hay algún tema distinto que debatir?  |Recomendación  |
|---------|---------|---------|---------|
|Sí      |Sí         |Sí          |Cree un canal privado en el equipo existente o considere crear canales privados especializados para cada tema.         |
|Sí     |Sí         |Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos         |Cree un canal privado en el equipo existente.         |
|Sí     |No         |No         |Cree un canal en el equipo existente.         |
|No     |No         |No         |Considere la posibilidad de crear un nuevo equipo.         |
|No     |No         |Sí         |Considere la posibilidad de crear un nuevo equipo y, a continuación, en función de la confidencialidad de cada tema, considere la posibilidad de crear canales privados o estándares independientes para cada tema.         |
|No     |Sí         |Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos         |Cree un nuevo equipo y considere la posibilidad de crear un canal privado.         |

Cuando se crea un canal privado, está vinculado al equipo principal y no se puede mover a un equipo diferente. Además, los canales privados no se pueden convertir en canales estándar, y viceversa.

## <a name="private-channel-creation-and-membership"></a>Creación y suscripción de canales privados

### <a name="who-can-create-private-channels"></a>¿Quién puede crear canales privados?

De forma predeterminada, los miembros del equipo o el propietario del equipo pueden crear un canal privado. Los invitados no pueden crear canales privados. La capacidad de crear canales privados se puede administrar en el nivel del equipo y en el nivel de la organización.

 1. Vaya al centro de administración en <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

 2. Use [directivas](teams-policies.md) para controlar los usuarios de su organización que pueden crear canales privados.
    Una vez que haya establecido las directivas, los propietarios del equipo pueden desactivar o activar la posibilidad de que los miembros creen canales privados en la pestaña **configuración** de un equipo.

La persona que crea un canal privado es el propietario del canal privado y solo el propietario del canal privado puede agregar o quitar personas directamente. El propietario de un canal privado puede agregar cualquier miembro del equipo a un canal privado que haya creado, incluyendo invitados. Los miembros de un canal privado tienen un espacio de conversación seguro, y cuando se agregan nuevos miembros, pueden ver todas las conversaciones (incluso las conversaciones antiguas) en ese canal privado.

### <a name="what-happens-when-a-team-member-leaves-or-is-removed-from-a-team"></a>¿Qué ocurre cuando un miembro del equipo lo abandona o es quitado del equipo?

Si un miembro del equipo lo abandona o es quitado de un equipo, también abandonará o se quitará de todos los canales privados del equipo. Si el usuario se vuelve a agregar al equipo, tiene que volver a agregarse a los canales privados del equipo.

### <a name="what-happens-when-a-private-channel-owner-is-removed-from-a-private-channel"></a>¿Qué sucede cuando el propietario de un canal privado se quita de un canal privado?

El propietario de un canal privado no se puede eliminar a través del cliente Teams si es el último propietario de uno o más canales privados.

Si un propietario de un canal privado abandona su organización o se ha quitado del grupo de Microsoft 365 asociado al equipo, un miembro del canal privado se promueve automáticamente al propietario del canal privado.

### <a name="what-can-team-owners-and-team-members-see-in-a-private-channel"></a>¿Qué pueden ver los propietarios del equipo y los miembros del equipo en un canal privado?

Los propietarios del equipo pueden ver los nombres de todos los canales privados de su equipo y también pueden quitar cualquier canal privado del equipo. (Los canales privados eliminados se pueden restaurar en un plazo de 30 días después de su eliminación). Los propietarios del equipo no pueden ver los archivos en un canal privado o en las conversaciones y la lista de miembros de un canal privado, a menos que sean miembros de ese canal privado.

En la tabla siguiente se muestran las personas que pueden ver lo que se encuentra en un canal privado.

|Elemento  |El propietario del equipo puede ver |Los integrantes de grupo pueden ver |
|---------|---------|---------|
|Nombre y descripción    |Todos los canales privados del equipo         |Solo los canales privados a los que se agregan         |
|Conversaciones y pestañas     |Solo cuando se agregue al canal privado         |Solo cuando se agregue al canal privado         |
|Archivos y contenido    |Solo cuando se agregue al canal privado        |Solo cuando se agregue al canal privado         |
|Propietario del canal privado    |Todos los canales privados del equipo        |Solo cuando se agregue al canal privado         |
|Marca de tiempo de la última actividad  |Todos los canales privados del equipo       |Solo cuando se agregue al canal privado         |

## <a name="manage-private-channels"></a>Administrar canales privados

En la siguiente tabla se describen las acciones que los propietarios, miembros e invitados pueden hacer en canales privados.

|Acción  |Propietario del equipo|Integrante de grupo|Invitado de equipo|Propietario del canal privado|Miembro de canal privado|Invitado de canal privado|
|---------|---------|---------|---------|---------|---------|---------|
|Crear un canal privado|Sí<sup>1</sup>|Sí<sup>1, 2</sup>|No|N/D|No aplicable|No aplicable|
|Quitar canal privado|Sí|Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos|No|Sí|Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos|No|
|Abandonar canal privado|N/D|No aplicable|N/D|Sí<sup>3</sup>|Sí|Sí|
|Editar canal privado|No|N/D|No aplicable|Sí|Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos|No|
|Restaurar el canal privado eliminado|Sí|Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos|No|Sí|Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos|No|
|Agregar miembros|No|N/D|No aplicable|Sí|Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos|No|
|Editar la configuración|No|N/D|No aplicable|Sí|Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos|No|
|Administrar pestañas y aplicaciones|No|N/D|N/D|Sí<sup>4</sup>|Sí<sup>5</sup>|No|

<sup>1</sup> Suponiendo que la directiva que usted, el administrador, configuró permita al usuario crear canales privados.<br>
<sup>2</sup> Cada equipo tiene una configuración que los propietarios del equipo pueden activar o desactivar para permitir que los miembros del equipo creen canales privados. Los propietarios del equipo siempre podrán crear canales privados.<br>
<sup>3</sup> Suponiendo que el propietario del canal privado no es el último propietario del canal. <br>
<sup>4</sup> Requiere que el equipo tenga una aplicación instalada para un canal privado para usarlo.<br>
<sup>5</sup> Los propietarios de canales privados pueden configurarlo.

### <a name="manage-private-channel-membership-and-settings"></a>Administrar la pertenencia y la configuración de canales privados

Cada canal privado dispone de su propia configuración, como la posibilidad de agregar y quitar miembros, agregar pestañas y @mentioning para todo el canal. Estas opciones son independientes de la configuración del equipo principal. Cuando se crea un canal privado, hereda la configuración del equipo principal, tras lo cual se pueden cambiar las configuraciones independientemente de la configuración del equipo principal.

El propietario del canal privado puede hacer clic en **Administrar canal** y, después, usar las pestañas **Miembros** y **Configuración** para agregar o quitar miembros y editar la configuración.  

![Captura de pantalla de la configuración de canal privado](media/private-channels-in-teams-channel-settings.png)

## <a name="manage-the-life-cycle-of-private-channels"></a>Administrar el ciclo de vida de los canales privados

Consulte [administrar el ciclo de vida de canales privados en Teams](private-channels-life-cycle-management.md) para obtener instrucciones sobre cómo administrar el ciclo de vida de los canales privados de su organización. Esto incluye cómo controlar si los usuarios de su organización pueden crear canales privados, cómo crear un canal privado en nombre de un propietario del equipo, cómo obtener una lista de todos los mensajes de canales privados para propósitos de archivado y auditoría, y otras tareas de administración.  

## <a name="private-channel-sharepoint-sites"></a>Sitios de SharePoint de canal privado

Cada canal privado tiene su propia colección de sitios de SharePoint. La colección de sitios independiente es para garantizar que el acceso a los archivos de canales privados esté restringido únicamente a los miembros del canal privado en comparación con el sitio del equipo donde los propietarios de los equipos tienen acceso a todos los activos dentro de la colección de sitios. Estas colecciones de sitios se crean con una biblioteca de documentos de forma predeterminada y pueden ampliarse fácilmente a una colección de sitios con todas las funciones con la [interfaz de administración de sitios](https://support.office.com/article/Enable-or-disable-site-collection-features-A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Todas las colecciones de sitios se crean en la misma región geográfica que la colección de sitios del equipo principal. Estos sitios livianos tienen un identificador de plantilla personalizado, "TEAMCHANNEL # 0", para facilitar la administración mediante la API de PowerShell y Graph.  Por diseño, no están visibles en el Centro de administración de SharePoint.

Para dar cabida a un mayor número de colecciones de sitios por inquilino, el límite ha aumentado de 500.000 a 2 millones. Una colección de sitios de canal privado sincroniza la clasificación de datos y hereda los permisos de acceso de invitado de la colección de sitios del equipo principal.  La pertenencia del propietario de la colección de sitios y los grupos de miembros se mantienen sincronizados con la membresía del canal privado dentro de Teams. Todos los cambios que se realicen en la pertenencia a propietario o grupos de miembros en SharePoint Online se revertirán automáticamente en un plazo de cuatro horas. En escenarios donde ciertos usuarios necesitan acceder a documentos sin necesidad de acceder a mensajes de canales privados, agréguelos al grupo visitantes del sitio o a un grupo nuevo que sea independiente de los propietarios y miembros.

Teams administra el ciclo de vida de la colección de sitios de SharePoint de canal privado. Si la colección de sitios se elimina fuera de Teams, un trabajo en segundo plano restaura el sitio en un plazo de cuatro horas siempre y cuando el canal privado aún esté activo. Si se elimina el sitio y se elimina permanentemente, se aprovisionará una nueva colección de sitios para el canal privado.

Si se restaura un canal privado o un equipo que contiene un canal privado, las colecciones de sitios se restauran con él. Si se restaura una colección de sitios de canal privado y se encuentra fuera de la ventana de eliminación temporal de 30 días para el canal privado, la colección de sitios funciona como una colección de sitios independiente.

## <a name="private-channel-message-compliance-records"></a>Registros de cumplimiento de mensajes de canal privado

Los registros de los mensajes enviados en un canal privado se entregan en el buzón de todos los miembros del canal privado, en lugar de hacerlo en un buzón de grupo. Los títulos de los registros tienen un formato que indica desde qué canal privado fueron enviados.

Para obtener más información sobre cómo realizar búsquedas en eDiscovery para mensajes de canal privado, consulte [eDiscovery de canales privados](ediscovery-investigation.md#ediscovery-of-private-channels).

## <a name="considerations-around-access-in-private-channels"></a>Consideraciones sobre el acceso en canales privados

Cuando se crea un nuevo Bloc de notas de OneNote en un canal privado, los usuarios adicionales aún pueden obtener acceso al bloc de notas, ya que este es el mismo comportamiento que comparte el acceso a cualquier otro elemento de un sitio de SharePoint de canal privado con un usuario.

Si se concede acceso a un usuario a un bloc de notas en un canal privado a través de SharePoint, al quitarlo del equipo o el canal privado, no se eliminará el acceso del usuario al bloc de notas.

Si se agrega un bloc de notas existente como una pestaña a un canal privado, no se cambiará el acceso al canal privado. Esto significa lo siguiente:

- No todos los usuarios del canal privado tendrán acceso al bloc de notas de forma predeterminada. Esto se debe a que es posible que no tengan acceso al lugar donde está alojado el Bloc de notas, como el sitio de SharePoint de otro equipo.
- Los usuarios que no sean miembros del canal privado podrán ver el Bloc de notas.  

## <a name="related-topics"></a>Temas relacionados

- [Información general de los equipos y canales en Microsoft Teams](teams-channels-overview.md)
- [Información general de PowerShell para Teams](teams-powershell-overview.md)
- [Usar la API de Microsoft Graph para trabajar con Microsoft Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
