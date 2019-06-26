---
title: Crear un equipo que abarque toda la organización en Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Aprenda a crear y administrar un equipo de toda la organización en Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c139efb2079a010c802b1c49ab18e0297cd8520
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221910"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Crear un equipo que abarque toda la organización en Microsoft Teams

Los equipos de toda la organización ofrecen una manera automática de que todos los usuarios de una organización pequeña o mediana formen parte de un único equipo para la colaboración.

Con los equipos de toda la organización, los administradores globales pueden crear fácilmente un equipo público que extrae a todos los usuarios de la organización y mantener la pertenencia actualizada con Active Directory a la vez que los usuarios se unen y salen de la organización. Solo los administradores globales pueden crear equipos de toda la organización y actualmente el equipo de toda la organización está limitado a organizaciones con un máximo de 5.000 usuarios. También hay un límite de cinco equipos de toda la organización por cada inquilino. Si se cumplen estos requisitos, los administradores globales verán **toda la organización** como una opción cuando seleccionen **crear un equipo desde cero** al crear un equipo. 

![Captura de pantalla de la opción de toda la organización para crear un equipo para toda la organización] (media/create-org-wide-team.png "Captura de pantalla de la opción de toda la organización para crear un equipo para toda la organización")

Cuando se crea un equipo de toda la organización, todos los administradores globales se agregan como propietarios del equipo y todos los usuarios activos se agregan como miembros del equipo. Los usuarios sin licencia también se agregan al equipo. La primera vez que un usuario sin licencia inicia sesión en Teams, se asigna al usuario una licencia de prueba de la nube comercial de Microsoft Teams. Para obtener más información sobre la licencia de prueba, consulte [administrar la oferta de evaluación de la nube comercial](iw-trial-teams.md). 

Estos tipos de cuentas no se agregarán al equipo de su organización:

- Cuentas que están bloqueadas para iniciar sesión
- Usuarios invitados
- Cuentas de servicio
- Cuentas de sala o de equipo
- Cuentas respaldadas por un buzón de correo compartido

Puesto que el directorio de su organización se actualiza para incluir nuevos usuarios activos o si los usuarios ya no trabajan en su empresa y su licencia de equipos está deshabilitada, los cambios se sincronizan automáticamente y se agregan o quitan los usuarios del equipo. Los miembros del equipo no pueden abandonar el equipo de toda la organización. Como propietario de un equipo, puede Agregar o quitar usuarios de forma manual si es necesario.

> [!NOTE]
> - Si no ve la opción **en toda la organización** al crear un equipo y es un administrador global, es posible que la característica aún se esté implementando o que su organización tenga más de lo que el límite actual de tamaño de 5.000 miembros. Estamos buscando aumentar este límite en el futuro.
> - Las salas que no forman parte de una lista de salas, equipos y cuentas de recursos se pueden agregar o sincronizar con el equipo de la organización. Los propietarios del equipo pueden quitar fácilmente estas cuentas del equipo.

## <a name="best-practices"></a>Procedimientos recomendados

Para sacar el máximo provecho del equipo de su organización, recomendamos que los propietarios del equipo hagan lo siguiente.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Permitir que solo los propietarios del equipo publiquen en el canal general

Reduzca el ruido del canal haciendo que solo los propietarios del equipo publiquen en el canal general. Vaya al equipo y haga clic en **más opciones** > **administrar equipo**. En la pestaña **configuración** , haga clic en **permisos de miembro**y, a continuación, seleccione **solo los propietarios pueden publicar mensajes**.

### <a name="turn-off-team-and-team-name-mentions"></a>Desactivar las menciones @team y @ [nombre del equipo]

Reduzca @mentions para evitar que se sobrecargue toda la organización. Vaya al equipo y haga clic en **más opciones** > **administrar equipo**. En la pestaña **configuración** , haga clic en <strong>@mentions</strong>y, a continuación, desactive **mostrar miembros la opción de @team o @ [nombre del equipo]**.

### <a name="automatically-favorite-important-channels"></a>Marcar automáticamente como favoritos los canales importantes

Marcar canales importantes como favoritos para asegurarse de que todos los miembros de la organización participen en conversaciones específicas. Para obtener más información, consulte [la opción canales de favoritos automáticos para todo el equipo](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).

### <a name="remove-accounts-that-might-not-belong"></a>Quitar cuentas que podrían no pertenecer

Aunque los miembros no pueden abandonar un equipo de organización en toda la organización, como propietario de un equipo, puede administrar la lista de equipos eliminando las cuentas que no pertenecen. Asegúrese de usar Teams para quitar usuarios del equipo de su organización. Si usa otra forma de quitar un usuario, como el centro de administración de Microsoft 365 o un grupo en Outlook, el usuario podría volver a agregarse al equipo de toda la organización.

## <a name="faq"></a>Preguntas frecuentes

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>¿Hay alguna forma de crear un equipo para toda la organización que no sea usar el cliente de Teams?

Los administradores globales solo pueden crear un equipo de organización a través del cliente de Teams. Si su organización limita la creación de Teams para usar PowerShell, la solución recomendada es agregar los administradores globales al grupo de seguridad de los usuarios que pueden crear un equipo. Si desea más información, consulte [Administrar quién puede crear grupos de Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups).

Si esta opción no es una opción, puede usar PowerShell para crear un equipo público y agregar un administrador global como propietario del equipo. Después, haga clic en el administrador global y en **más opciones** junto al nombre del equipo, haga clic en **Editar equipo**y cambie la privacidad a **toda la organización; todos los usuarios de la organización se agregarán automáticamente**. Tenga en cuenta que solo los propietarios del equipo pueden tener acceso a la opción **Editar equipo** y solo los administradores globales pueden ver la opción **en toda la organización** .

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>¿Hay alguna forma de convertir un equipo existente en un equipo de toda la organización?

Los administradores globales pueden convertir un equipo existente en un equipo de organización mediante su edición en el cliente de Teams. Vaya al nombre del equipo y haga clic en **más opciones** > **Editar equipo**.
