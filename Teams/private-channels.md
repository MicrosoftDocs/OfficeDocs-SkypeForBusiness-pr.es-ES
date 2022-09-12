---
title: Canales privados en Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-securecollab
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Obtenga información acerca de cómo usar y administrar canales privados en Microsoft Teams.
ms.openlocfilehash: 2f6dd23c5f15d2c96a1a5bb7cec6f4b9107f436c
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647454"
---
# <a name="private-channels-in-microsoft-teams"></a>Canales privados en Microsoft Teams

Los canales privados de Microsoft Teams crean espacios prioritarios para la colaboración de los equipos. Solo los usuarios del equipo que sean propietarios o miembros del canal privado podrán acceder al canal. Cualquier persona, incluidos los invitados, puede agregarse como miembro de un canal privado siempre y cuando ya sean miembros del equipo.

Un canal privado puede ser útil para limitar la colaboración a solo aquellos usuarios que necesitan conocer una información o para facilitar la comunicación entre un grupo de personas asignadas a un proyecto específico, sin tener que crear un equipo adicional para administrar.

Por ejemplo, un canal privado es útil en estos escenarios:

- Un grupo de personas en un equipo desean un espacio prioritario para colaborar sin tener que crear un equipo independiente.
- Un subconjunto de personas de un equipo quiere que un canal privado discuta información confidencial, como presupuestos, recursos, posicionamiento estratégico, etc.

Un icono de bloqueo indica un canal privado. Solo los miembros de canales privados pueden ver y participar en canales privados a los que se agregan.

Cuando se crea un canal privado, está vinculado al equipo principal y no se puede mover a un equipo diferente. Además, los canales privados no se pueden convertir en canales estándar, y viceversa.

[Comparar canales privados con otros tipos de canales](/microsoftteams/teams-channels-overview#channel-feature-comparison).

![Captura de pantalla de canales privados en un equipo.](media/private-channels-in-teams.png)

## <a name="private-channel-creation"></a>Creación de canales privados

De forma predeterminada, los miembros del equipo o el propietario del equipo pueden crear un canal privado. Los invitados no pueden crear canales privados. La posibilidad de crear canales privados se puede administrar a nivel de equipo y de organización. Utilice las [directivas](teams-policies.md) para controlar qué usuarios de su organización pueden crear canales privados. Una vez que haya establecido las directivas, los propietarios del equipo podrán activar o desactivar la opción de que los miembros puedan crear canales privados en la pestaña **Configuración** para un equipo.

La persona que crea un canal privado es el propietario del canal privado y solo el propietario del canal privado puede agregar o quitar personas directamente. El propietario de un canal privado puede agregar cualquier miembro del equipo a un canal privado que haya creado, incluyendo invitados. Los miembros de un canal privado tienen un espacio de conversación seguro, y cuando se agregan nuevos miembros, pueden ver todas las conversaciones (incluso las conversaciones antiguas) en ese canal privado.

Los propietarios del equipo pueden ver los nombres de todos los canales privados de su equipo y también pueden quitar cualquier canal privado del equipo. (Los canales privados eliminados se pueden restaurar en un plazo de 30 días después de su eliminación). Los propietarios del equipo no pueden ver los archivos en un canal privado o en las conversaciones y la lista de miembros de un canal privado, a menos que sean miembros de ese canal privado.

Los miembros del equipo solo pueden ver los canales privados en los que han sido agregados.

## <a name="adding-and-removing-owners-and-members"></a>Agregar y quitar propietarios y miembros

El propietario de un canal privado no se puede eliminar a través del cliente Teams si es el último propietario de uno o más canales privados.

Si el propietario de un canal privado deja la organización o se quita del grupo de Microsoft 365 asociado al equipo, se promueve automáticamente un miembro del canal privado para que sea el propietario del canal privado.

Si un miembro del equipo lo abandona o es quitado de un equipo, también abandonará o se quitará de todos los canales privados del equipo. Si el usuario se vuelve a agregar al equipo, tiene que volver a agregarse a los canales privados del equipo.

## <a name="channel-owner-settings"></a>Configuración del propietario del canal

Cada canal privado dispone de su propia configuración que el propietario del canal puede administrar, como la posibilidad de agregar y quitar miembros, agregar pestañas y @mentioning para todo el canal. Estas opciones son independientes de la configuración del equipo principal. Cuando se crea un canal privado, hereda la configuración del equipo principal, tras lo cual se pueden cambiar las configuraciones independientemente de la configuración del equipo principal.

El propietario del canal privado puede hacer clic en **Administrar canal** y, después, usar las pestañas **Miembros** y **Configuración** para agregar o quitar miembros y editar la configuración.

![Captura de pantalla de la configuración de un canal privado.](media/private-channels-in-teams-channel-settings.png)

## <a name="private-channel-owner-and-member-actions"></a>Acciones de los miembros y propietarios de canales privados

En la siguiente tabla se describen las acciones que los propietarios, miembros e invitados pueden hacer en canales privados.

|Acción  |Propietario del equipo|Integrante de grupo|Invitado de equipo|Propietario del canal privado|Miembro de canal privado|Invitado de canal privado|
|---------|---------|---------|---------|---------|---------|---------|
|Crear un canal privado|Controlado por el administrador|Controlado por el administrador y el propietario del equipo|No|N/D|N/D|N/D|
|Quitar canal privado|Sí|No|No|Sí|No|No|
|Abandonar canal privado|N/D|N/D|N/D|Sí, a menos que sea el último usuario propietario|Sí|Sí|
|Editar canal privado|No|N/D|N/D|Sí|No|No|
|Restaurar el canal privado eliminado|Sí|No|No|Sí|No|No|
|Agregar miembros|No|N/D|N/D|Sí|No|No|
|Editar la configuración|No|N/D|N/D|Sí|No|No|
|Administrar pestañas y aplicaciones|No|N/D|N/D|Sí, las aplicaciones deben estar instaladas para el equipo|Controlado por el propietario del canal|No|

## <a name="private-channel-sharepoint-sites"></a>Sitios de SharePoint de canal privado

Cada canal privado tiene su propio sitio de SharePoint. La finalidad del sitio independiente es garantizar que el acceso a los archivos de canales privados esté restringido exclusivamente a los miembros del canal privado. Estos sitios se crean con una biblioteca de documentos de forma predeterminada y pueden ampliarse fácilmente a un sitio con todas las funciones mediante la [interfaz de administración de sitios](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Cada sitio se crea en la misma región geográfica que el sitio para el equipo principal. Estos sitios livianos tienen un identificador de plantilla personalizado, "TEAMCHANNEL # 0" o "TEAMCHANNEL#1", para facilitar la administración mediante la API de PowerShell y Graph. 

> [!NOTE]
> Solo las personas con permisos de propietario o miembro en el canal tendrán acceso al contenido del sitio del canal compartido. Las personas del equipo primario y los administradores no tendrán acceso a menos que también sean miembros del canal.

Un sitio de canal privado sincroniza la clasificación de datos y hereda los permisos de acceso de invitado del sitio del equipo principal. La pertenencia del propietario del sitio y los grupos de miembros se mantienen sincronizados con la membresía del canal privado dentro de Teams. Los permisos de sitio para un sitio de canal privado no se pueden administrar de forma independiente a través de SharePoint. 

Teams administra el ciclo de vida del sitio del canal privado. Si se elimina el sitio fuera de Teams, un trabajo en segundo plano lo restaura en un plazo de cuatro horas, siempre y cuando el canal privado aún esté activo.

Si se restaura un canal privado o un equipo que contiene un canal privado, los sitios se restaurarán con él. Si se restaura un sitio de canal privado y se encuentra fuera de la ventana de eliminación temporal de 30 días para el canal privado, el sitio funcionará como un sitio independiente.

> [!NOTE]
> Al crear un nuevo equipo, canal privado o canal compartido en Microsoft Teams, se crea automáticamente un sitio de grupo en SharePoint. Si desea editar la descripción o clasificación de este sitio de grupo, vaya a la [configuración del canal correspondiente en Microsoft Teams](https://support.microsoft.com/office/change-a-team-s-data-security-classification-in-teams-bf39798f-90d2-44fb-a750-55fa05a56f1d).
>
> Obtenga más información sobre cómo administrar los [Sitios de grupos conectados a Microsoft Teams](/SharePoint/teams-connected-sites).

## <a name="compliance-copies-of-private-channel-messages"></a>Copias de cumplimiento de mensajes de canal privado

Las copias de cumplimiento de los mensajes enviados en un canal privado se entregan al buzón de todos los miembros del canal privado, en lugar de a un buzón de grupo. Los títulos de las copias de cumplimiento tienen formato para indicar desde qué canal privado se enviaron.

Para obtener más información sobre cómo realizar búsquedas en eDiscovery para mensajes de canal privado, consulte [eDiscovery de canales privados](ediscovery-investigation.md#ediscovery-of-private-and-shared-channels).

## <a name="considerations-around-file-access-in-private-channels"></a>Consideraciones sobre el acceso a archivos en canales privados

Cuando se crea un nuevo Bloc de notas de OneNote en un canal privado, los usuarios adicionales aún pueden obtener acceso al bloc de notas, ya que este es el mismo comportamiento que comparte el acceso a cualquier otro elemento de un sitio de SharePoint de canal privado con un usuario.

Si se concede acceso a un usuario a un bloc de notas en un canal privado a través de SharePoint, al quitarlo del equipo o el canal privado, no se eliminará el acceso del usuario al bloc de notas.

Si se agrega un bloc de notas existente como una pestaña a un canal privado, no se cambiará el acceso al canal privado y el bloc de notas conservará los permisos existentes.

## <a name="private-channel-limitations"></a>Limitaciones de los canales privados

Actualmente, los canales privados son compatibles con conectores y pestañas (excepto Stream, Planner y Forms). Estamos trabajando para brindarle soporte completo de aplicaciones para canales privados, incluidas extensiones de mensajería y bots.

Cada equipo puede tener un máximo de 30 canales privados y cada canal privado puede tener un máximo de 250 miembros. El límite de 30 canales privados es adicional al límite de 200 canales estándar por equipo. 

Cuando se crea un equipo a partir de un equipo existente, los canales privados del equipo existente no se copiarán al nuevo equipo.

No es posible convertir un canal privado en otro tipo de canal.

Las notificaciones de canales privados no se incluyen en los correos electrónicos de actividad perdida.

No se pueden programar reuniones de canal.

Las reuniones de canal no se pueden personalizar con el título de la reunión.

## <a name="related-topics"></a>Temas relacionados

[Canales compartidos en Microsoft Teams](/MicrosoftTeams/shared-channels)

[Información general de los equipos y canales en Microsoft Teams](teams-channels-overview.md)

[Información general de PowerShell para Teams](teams-powershell-overview.md)

[Usar la API de Microsoft Graph para trabajar con Microsoft Teams](/graph/api/resources/teams-api-overview)

[Tipo de recurso de canal](/graph/api/resources/channel)
