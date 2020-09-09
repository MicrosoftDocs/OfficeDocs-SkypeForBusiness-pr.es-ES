---
title: Crear un equipo de la organización en Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Aprenda a crear y administrar un equipo de todo el mundo en Teams para ofrecer una forma automática para que todos los usuarios de una pequeña y mediana empresa puedan colaborar.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1950c395c61bd1f6d70741e3d9a8a26553f3445a
ms.sourcegitcommit: 207c58563b7b2aba274b067cf64242abd7a33c2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405797"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Crear un equipo de la organización en Microsoft Teams

Los equipos de la organización proporcionan una forma automática para que todos los miembros de una organización de tamaño pequeño o mediano formen parte de un único equipo de colaboración.

Con los equipos de la organización, los administradores globales pueden crear fácilmente un equipo público que atraiga a todos los usuarios de la organización y mantenga a los miembros al día con el Active Directory a medida que los usuarios entran y salen de la organización. Solo los administradores globales pueden crear equipos de toda la organización y, en la actualidad, el equipo de toda la organización está limitado a organizaciones con un máximo de 5.000 usuarios. También hay un límite de cinco equipos de la organización por inquilino. Si se cumplen estos requisitos, los administradores globales verán la opción **toda la organización** cuando seleccione **Construir un equipo desde cero** al crear un equipo. 

![Captura de pantalla de la opción de crear un equipo de la organización](media/create-org-wide-team.png "Captura de pantalla de la opción Toda la organización para crear un equipo de la organización")

Cuando se crea un equipo a nivel de la organización, todos los administradores globales se añaden como propietarios del equipo y todos los usuarios activos se añaden como miembros del equipo. Los usuarios sin licencia también se agregan al equipo. La primera vez que un usuario sin licencia inicia sesión en Teams, se asigna al usuario una licencia de exploratorias de Microsoft Teams. Para obtener más información sobre la licencia de exploratorias, consulte [administrar la licencia de exploración de Microsoft Teams](teams-exploratory.md). 

Este tipo de cuentas no se añadirán a su equipo de la organización:

- Las cuentas que están bloqueadas para iniciar sesión
- Usuarios invitados
- Cuentas de servicio 
- Cuentas de sala o equipamiento
- Cuentas respaldadas por un buzón compartido

A medida que el directorio de su organización se actualiza para incluir nuevos usuarios activos o si los usuarios ya no trabajan en su empresa y su cuenta está desactivada, los cambios se sincronizan automáticamente y los usuarios se agregan o eliminan del equipo. Los miembros del equipo no pueden dejar un equipo de la organización. Como propietario del equipo, puede añadir o eliminar usuarios manualmente si es necesario.

> [!NOTE]
> - Si no ve la opción **en toda la organización** al crear un equipo y es administrador global, es posible que haya alcanzado el límite de equipos de cinco organizaciones, o que su organización tenga más del límite de tamaño actual de miembros de 5.000. Buscamos aumentar este límite en el futuro. Los equipos de toda la organización aún no están disponibles para Teams educativo.
> - Las habitaciones que no son parte de una lista de habitaciones, equipo, y cuentas de recursos pueden ser agregadas o sincronizadas con el equipo de toda la organización. Los dueños de los equipos pueden eliminar fácilmente estas cuentas del equipo.
> - Todas las acciones del sistema para añadir o eliminar miembros se publican en el Canal general. El canal también será marcado como con nueva actividad en el cliente de Teams.
> - Crearemos automáticamente un equipo de la organización, si su organización es nueva en Teams y no tiene más de 5 000 usuarios. El nombre del equipo reflejará el nombre del inquilino y tendrá un Canal general. Los administradores globales pueden editar este equipo como cualquier otro equipo. 

## <a name="best-practices"></a>Procedimientos recomendados

Para sacar el máximo provecho de su equipo de toda la organización, recomendamos a los propietarios de los equipos que hagan lo siguiente.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Permitir que sólo los propietarios de los equipos publiquen en el canal general

Reducir el ruido del canal haciendo que sólo los propietarios de los equipos publiquen en el canal general. Vaya al equipo, busque el canal general y, a continuación, seleccione **̇ ̇ ̇ más opciones**  >  **administrar canal**. En la pestaña **configuración de canal** , haga clic en **permisos**y, a continuación, seleccione **solo los propietarios pueden publicar mensajes**.

### <a name="turn-off-team-and-team-name-mentions"></a>Desactivar menciones @equipo y @[nombre del equipo]

 Reducir las @menciones para evitar que sobrecarguen toda la organización. Diríjase al equipo y haga clic en **˙˙˙ Más opciones** > ** Administrar equipo**. En la pestaña **Configuración**, haga clic en <strong>@menciones</strong> > desactivar **Mostrar a los miembros la opción de @equipo o @[nombre del equipo]**. 

### <a name="automatically-show-important-channels"></a>Mostrar automáticamente los canales importantes

Muestre canales importantes para asegurarse de que todos los miembros de su organización participen en conversaciones específicas. Para obtener más información, consulte [Canales favoritos automáticos para todo el equipo](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6). 

### <a name="set-up-channel-moderation"></a>Configurar la moderación del canal

Considere la posibilidad de establecer la moderación del canal y dar capacidad de moderación a ciertos miembros del equipo. (Cuando se establece la moderación, los dueños de los equipos reciben automáticamente la capacidad de moderar.) Los moderadores pueden controlar quién puede iniciar un nuevo mensaje en un canal, añadir y eliminar moderadores, controlar si los miembros del equipo pueden responder a los mensajes existentes del canal y controlar si los bots y conectores pueden enviar mensajes del canal. Parara más información, consulte[Configurar y administrar la moderación de canales en Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Eliminar las cuentas que podrían no pertenecer

Aunque los miembros no pueden abandonar un equipo de organización en toda la organización, como propietario de un equipo, puede administrar la lista de equipos eliminando las cuentas que no pertenecen. ** Asegúrese de usar Teams para eliminar a los usuarios de su equipo de la organización**. Si usa otra forma de eliminar un usuario, como el Centro de administración de Microsoft 365 o de un grupo en Outlook, el usuario puede ser añadido de nuevo al equipo de la organización.

## <a name="faq"></a>Preguntas más frecuentes

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>¿Hay alguna manera de crear un equipo de toda la organización aparte de usar el cliente de Teams?

Los administradores globales sólo pueden crear un equipo de toda la organización usando el cliente de Teams. Si su organización limita la creación de equipos al uso de PowerShell, la solución recomendada es agregar sus administradores globales al grupo de seguridad de usuarios que pueden crear un equipo. Para obtener más información, vea [administrar quién puede crear grupos](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups).

Si esto no es una opción, puede usar PowerShell para crear un equipo público y agregar un administrador global como propietario del equipo. Luego, haga que el administrador global haga clic en **Más opciones** junto al nombre del equipo, haga clic en **Editar equipo**, y luego cambie la privacidad a **Toda la organización - Todos en su organización serán agregados automáticamente**. Tenga en cuenta que sólo los propietarios de los equipos pueden acceder a la opción **Editar equipo** y sólo los administradores globales pueden ver la opción **Toda la organización**.

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>¿Hay alguna manera de convertir un equipo existente en un equipo de toda la organización?

Los administradores globales pueden convertir un equipo existente en un equipo de toda la organización editándolo en el cliente de Teams. Vaya al nombre del equipo, haga clic en**más opciones** > **Editar equipo**.

### <a name="can-i-create-an-org-wide-team-using-a-team-template"></a>¿Puedo crear un equipo para toda la organización con una plantilla de equipo?

Las plantillas de equipo no se pueden usar para crear un equipo de toda la organización. El trabajo para esta característica está actualmente en curso. 

## <a name="see-also"></a>Vea también

Vea un vídeo sobre cómo [crear un equipo de toda la empresa en Microsoft Teams](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).
