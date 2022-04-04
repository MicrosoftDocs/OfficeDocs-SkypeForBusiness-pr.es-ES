---
title: Canales compartidos en Microsoft Teams (versión preliminar)
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: arundas
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
ms.localizationpriority: high
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar canales compartidos en Microsoft Teams (versión preliminar).
ms.openlocfilehash: 0c66d308ef5182c6ace69a7bdcd004c865109bec
ms.sourcegitcommit: 3e7c491d2bb13c86ac8e73b1c6c9735660c673e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64590388"
---
# <a name="shared-channels-in-microsoft-teams-preview"></a>Canales compartidos en Microsoft Teams (versión preliminar)

Los canales compartidos en Microsoft Teams crean espacios de colaboración donde se puede invitar a usuarios que no forman parte del equipo. Solo los usuarios que sean propietarios o miembros del canal compartido pueden acceder al canal. Aunque los invitados (usuarios con cuentas de invitado de Azure Active Directory de la organización) no se pueden agregar a un canal compartido, se puede invitar a usuarios de fuera de la organización a participar en un canal compartido mediante Azure AD conexión directa B2B.

Es posible que quiera usar un canal compartido si desea colaborar con un grupo de usuarios que son miembros de distintos equipos. Por ejemplo, los empleados del área de ingeniería, de ventas y soporte técnico que trabajen en diferentes aspectos del mismo proyecto o producto podrían usar un canal compartido para colaborar.

Solo los miembros de los canales compartidos pueden ver y participar en los canales compartidos a los que se les ha agregado. Otros miembros del equipo al que está conectado el canal compartido no verán el canal.

Cuando se crea un canal compartido, se vincula al equipo primario y no se puede mover a otro equipo. Además, los canales compartidos no se pueden convertir en canales estándar y viceversa.

## <a name="best-practices-for-the-shared-channels-preview"></a>Procedimientos recomendados para la versión preliminar de canales compartidos

Los canales compartidos están en versión preliminar y requieren que se haya configurado la [Versión preliminar pública de Microsoft Teams](/MicrosoftTeams/public-preview-doc-updates). Si planea compartir canales con otras organizaciones, también deben tener configurada la versión preliminar pública de Teams.

Se recomienda habilitar la versión preliminar para todos los usuarios. Los usuarios para los que la versión preliminar no está habilitada no pueden crear canales compartidos, pero sí se pueden agregar a los canales compartidos. Habilitar la versión preliminar para todos los usuarios puede ayudar a garantizar una experiencia correcta.

## <a name="getting-started-with-shared-channels"></a>Introducción a los canales compartidos

Los canales compartidos están habilitados de forma predeterminada en Teams. Puede elegir darles permiso a los usuarios para crear canales compartidos, si pueden compartirlos con personas fuera de la organización y si pueden participar en canales compartidos externos [creando una directiva de canal](/MicrosoftTeams/teams-policies).

Si tiene previsto compartir canales con personas ajenas a la organización, lea [Planear la colaboración externa](/microsoft-365/solutions/plan-external-collaboration) para obtener información importante sobre la planificación.

El uso compartido de canales con usuarios ajenos a la organización también requiere que se configuren las opciones de acceso entre inquilinos en Azure AD. Cada organización con la que se quiera compartir canales también deberá llevar a cabo esta configuración. Consulte [Colaborar con participantes externos en un canal](/microsoft-365/solutions/collaborate-teams-direct-connect) para obtener más detalles.

## <a name="shared-channel-creation"></a>Creación de canales compartidos

Solo los propietarios del equipo pueden crear un canal compartido. Los miembros del equipo y los invitados no pueden crearlos. La capacidad de crear canales compartidos se puede administrar en el nivel de organización. Utilice [directivas](teams-policies.md) para controlar qué usuarios de la organización pueden crear canales compartidos.

El usuario que crea un canal compartido se convierte en el propietario de dicho canal y solo el propietario puede agregar o quitar personas de forma directa. (Si lo desea, puede agregar más de un propietario). Un propietario del canal compartido puede agregar a cualquier usuario de la organización a un canal compartido que haya creado. Los miembros de un canal compartido tienen un espacio de conversación seguro y, si se agregan nuevos miembros, estos pueden ver todas las conversaciones (incluso las antiguas) del canal compartido.

Los propietarios del equipo pueden ver los nombres de todos los canales compartidos de su equipo así como eliminar cualquier canal compartido del equipo. Los propietarios del equipo no pueden ver los archivos en un canal compartido ni las conversaciones y la lista de miembros de un canal compartido a menos que sean miembros de ese canal.

Los miembros del equipo solo pueden ver los canales compartidos a los que se les ha agregado.

La clonación de un equipo no clonará los canales compartidos asociados.

## <a name="shared-channel-deletion"></a>Eliminación de canal compartido

El canal compartido eliminado se puede restaurar en un plazo de 30 días después de la eliminación. Cuando se restaura un canal compartido eliminado, se restaurarán todas las pertenencias anteriores (uso compartido individual y de equipo).

Los equipos eliminados se pueden restaurar en un plazo de 30 días después de la eliminación. Cuando se elimina un equipo, también se eliminarán todos los canales compartidos. Cuando se restaura un equipo eliminado, se restauran todos los canales compartidos con las relaciones de uso compartido.

Cuando se archiva un equipo, el uso compartido individual permanecerá intacto, pero se quitará el uso compartido con equipos distintos del equipo primario. Cuando se anula el archivado del equipo, todos los canales compartidos se restaurarán solo con uso compartido individual.

## <a name="adding-and-removing-owners-and-members"></a>Agregar y quitar propietarios y miembros

No se puede quitar a un propietario de un canal compartido a través del cliente de Teams si es el último propietario que queda de uno o más canales compartidos.

Si el último propietario del canal compartido abandona la organización o si se quita del grupo de Microsoft 365 asociado al equipo, se promoverá automáticamente a otro miembro del canal compartido para que sea el propietario de dicho canal. Considere agregar más de un propietario para evitar esta situación.

## <a name="channel-owner-settings"></a>Configuración del propietario del canal

Cada canal compartido tiene su propia configuración que el propietario del canal puede administrar, incluida la capacidad de agregar y quitar miembros, agregar pestañas y @mencionar para todo el canal. Estas opciones son independientes de la configuración del equipo principal. Cuando se crea un canal compartido, hereda la configuración del equipo primario. La configuración se podrá cambiar independientemente de la configuración del equipo primario.

El propietario del canal compartido podrá hacer clic en **Administrar canal** y usar las pestañas **Miembros** y **Configuración** para agregar o quitar miembros y editar la configuración.

## <a name="shared-channel-owner-and-member-actions"></a>Acciones de propietarios y miembros de canal compartido

En la siguiente tabla se describen las acciones que los propietarios, miembros e invitados pueden hacer en canales compartidos.

|Acción  |Propietario del equipo|Integrante de grupo|Invitado de equipo|Propietario del canal compartido|Miembro del canal compartido|Participante externo del canal compartido|
|---------|---------|---------|---------|---------|---------|---------|
|Crear un canal compartido|Controlado por el administrador|Controlado por el administrador y el propietario del equipo|No|N/D|No|No|
|Eliminar un canal compartido|Sí|No|No|Sí|No|No|
|Salir de un canal compartido|N/D|N/D|N/D|Sí, a menos que sea el último usuario propietario|Sí|Sí|
|Editar un canal compartido|No|N/D|N/D|Sí|No|No|
|Restaurar un canal compartido eliminado|Sí|No|No|Sí|No|No|
|Agregar miembros|No|N/D|N/D|Sí|No|No|
|Editar la configuración|No|N/D|N/D|Sí|No|No|
|Administrar pestañas y aplicaciones|No|N/D|N/D|Sí, las aplicaciones deben estar instaladas para el equipo|Controlado por el propietario del canal|No|

## <a name="shared-channel-sharepoint-sites"></a>Sitios de SharePoint de canal compartido

Cada canal compartido tiene [su propio sitio de SharePoint](/SharePoint/teams-connected-sites). La finalidad del sitio independiente es garantizar que el acceso a los archivos de un canal compartido esté restringido exclusivamente a los miembros de dicho canal. Estos sitios se crean con una biblioteca de documentos de forma predeterminada y pueden ampliarse fácilmente a un sitio con todas las funciones mediante la [interfaz de administración de sitios](https://support.office.com/article/A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Cada sitio se crea en la misma región geográfica que el sitio para el equipo principal. Estos sitios livianos tienen un identificador de plantilla personalizado, "TEAMCHANNEL # 0", para facilitar la administración mediante la API de PowerShell y Graph. 

> [!NOTE]
> Solo las personas con permisos de propietario o miembro en el canal tendrán acceso al contenido del sitio del canal compartido. Las personas del equipo primario y los administradores no tendrán acceso a menos que también sean miembros del canal.

Un sitio de canal compartido sincroniza la clasificación de datos del sitio del equipo primario. La pertenencia del propietario del sitio y los grupos de miembros se mantiene sincronizada con la pertenencia del canal compartido. Los permisos de sitio para un sitio de canal compartido no se pueden administrar de forma independiente a través de SharePoint. 

Teams administra el ciclo de vida del sitio del canal compartido. Si el sitio se elimina fuera de Teams, se restaura automáticamente en un plazo de cuatro horas, siempre y cuando el canal compartido siga activo. Si el sitio se elimina de forma permanente, se aprovisiona un nuevo sitio para el canal compartido.

Si se restaura un canal compartido o un equipo que contiene un canal compartido, los sitios también se restauran. Si se restaura un sitio de canal compartido y está fuera del periodo de eliminación temporal de 30 días para el canal compartido, el sitio funciona como un sitio independiente.

## <a name="shared-channel-messages"></a>Mensajes de canal compartido

Los mensajes de canal compartido se almacenan en un buzón de sistema dedicado asociado al canal compartido y no en el buzón de grupo.

Para obtener más información sobre cómo realizar una búsqueda de exhibición de documentos electrónicos para mensajes de canal compartido, vea [Realizar una investigación de exhibición de documentos electrónicos de contenido en Microsoft Teams](ediscovery-investigation.md).

## <a name="considerations-around-file-access-in-shared-channels"></a>Consideraciones sobre el acceso a archivos en canales compartidos

Los archivos, carpetas y blocs de notas de OneNote de un canal compartido se pueden compartir con usuarios ajenos al canal mediante el [uso compartido de archivos estándar de SharePoint](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c).

Si se concede acceso a un usuario a un archivo, carpeta o bloc de notas en un canal compartido a través de SharePoint, quitar al usuario del equipo o del canal compartido no quitará el acceso del usuario a dicho archivo, carpeta o bloc de notas.

Si un bloc de notas existente se agrega como una pestaña a un canal compartido, no se cambia el acceso al canal compartido y el bloc de notas conserva sus permisos existentes.

## <a name="resources-for-your-users"></a>Recursos para los usuarios

Los siguientes artículos pueden ser útiles para los usuarios de su organización cuando usen canales compartidos.

[Crear un canal compartido en Teams](https://support.microsoft.com/office/80712457-579e-42b2-b54f-112329578aaa)

[Compartir un canal con usuarios de Teams](https://support.microsoft.com/office/5f60de2d-0080-4e55-b26f-33a9dafa120e)

[Compartir un canal con un equipo](https://support.microsoft.com/office/b2e89992-2708-4583-b11e-bbb6edb4f1c3)

[¿Por qué usar un canal compartido frente a otros tipos de canal en Teams?](https://support.microsoft.com/office/e6ad61d0-6b3f-4e1b-baac-63e2978bd92e)

[Invitados y canales compartidos en Teams](https://support.microsoft.com/office/612de4ce-e7a3-4579-b086-bb8ff9f2d11e)

[Roles de propietario del canal compartido y miembro en Teams](https://support.microsoft.com/office/75b379f4-8e9c-4202-acf1-6ffc3878a2d7)

## <a name="limits-for-shared-channels-preview"></a>Límites para los canales compartidos (versión preliminar)

En la tabla siguiente se describe el número máximo de canales y miembros.

|Máximo...|Valor|Notas|
|:---------|:----|:----|
|Miembros de un equipo|25 000|Incluye todos los usuarios del equipo y miembros directos en canales compartidos.|
|Canales compartidos por equipo|50|Hospedado y compartido con el equipo. (Incluye los canales eliminados durante el período de recuperación de 30 días).|
|Equipos con los que se puede compartir un canal|50|Excluyendo el equipo primario|
|Miembros en un canal compartido|1000 miembros directos, incluidos hasta 50 equipos. (Cada equipo con el que se comparte el canal cuenta como un miembro para este límite).|Las actualizaciones en tiempo real solo están disponibles para 25 000 usuarios a la vez y solo 25 000 usuarios aparecerán en la lista de canales.|

También se aplican las siguientes limitaciones:

- Los canales compartidos admiten pestañas excepto Stream, Planner y Forms.

- Las aplicaciones LOB, los bots, los conectores y las extensiones de mensaje no se admiten en la versión preliminar pública.

- Cuando se crea un equipo a partir de un equipo existente, los canales compartidos del equipo existente no se copiarán.

- Las notificaciones de canales compartidos no se incluyen en los correos electrónicos sobre actividad perdida.

## <a name="related-topics"></a>Temas relacionados

[Información general sobre la conexión directa B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Configurar las opciones de acceso entre inquilinos para la conexión directa B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Información general de los equipos y canales en Microsoft Teams](teams-channels-overview.md)

[Canales privados en Microsoft Teams](/microsoftteams/private-channels)
