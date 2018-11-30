---
title: Crear un equipo que abarque toda la organización en Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.date: 09/27/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo crear y administrar un equipo de toda la organización en los equipos.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cefcf6cb4d1710935e6448e4babd7a284165e767
ms.sourcegitcommit: f7b706f8ac9647ba854ae3457018d3007edf6f6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2018
ms.locfileid: "26993421"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Crear un equipo que abarque toda la organización en Microsoft Teams

Los equipos de toda la organización proporcionan una forma automática para todos los usuarios en una organización pequeña a mediana forme parte de un único equipo para la colaboración. 
 
Con los equipos de toda la organización, los administradores globales pueden crear fácilmente un equipo público que extrae en todos los usuarios de la organización y mantiene la pertenencia al día con Active Directory como unirse a los usuarios y salir de la organización. Sólo los administradores globales pueden crear los equipos de toda la organización y actualmente se limita a las organizaciones con no más de 2.500 a los usuarios un equipo de toda la organización. Si se cumplen estos requisitos, los administradores globales vea **toda la organización** como una opción en **privacidad** al crear un equipo.

![Captura de pantalla de la opción de toda la organización para crear un equipo de toda la organización] (media/create-org-wide-team.png "Captura de pantalla de la opción de toda la organización para crear un equipo de toda la organización")

> [!NOTE]
> Si no ve la opción de **toda la organización** al crear un equipo y es un administrador global, la característica aún es posible que implantar o su organización puede tener más que el límite de tamaño actual de 2.500 miembros. Buscamos para aumentar este límite en el futuro.

Cuando se crea un equipo de toda la organización, todos los administradores globales se agregan como propietarios de equipo y todos los usuarios activos se agregan como miembros del equipo. Los usuarios que están deshabilitados para los equipos, los usuarios invitados y salas mayoría no se agregan al equipo. Como Active directory de su organización se ha actualizado para incluir nuevos usuarios activos o si los usuarios ya no funcionan en su empresa y su licencia de los equipos está deshabilitada, los cambios son automáticamente sincronizado y se agregan o se quitan del equipo de los usuarios. Los miembros del equipo no pueden dejar un equipo de toda la organización. Como propietario de un equipo, puede agregar manualmente o quitar los usuarios si es necesario.

> [!NOTE]
> Es posible que se agreguen o sincronizados con el equipo de toda la organización salones que no forman parte de un cuentas de lista, equipamiento y recursos de sala. Los propietarios de equipo pueden quitar fácilmente estas cuentas desde el equipo.

## <a name="best-practices"></a>Procedimientos recomendados
Para obtener el máximo partido de su equipo de toda la organización, se recomienda que los propietarios de equipo haga lo siguiente.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Permitir que sólo los propietarios de equipo registrar en el canal de General
Reducir el ruido de canal por tener solo del equipo que los propietarios de entrada para el canal General. Vaya al equipo y haga clic en **más opciones (…)**  >  **Administrar equipo**. En la ficha **configuración** , haga clic en **permisos de miembro** > seleccione **sólo los propietarios pueden publicar mensajes**.
### <a name="turn-off-team-and-team-name-mentions"></a>Desactivar @team y @ menciones de [nombre de equipo]
 Reducir @mentions para evitar la sobrecarga de toda la organización. Vaya al equipo y haga clic en **más opciones (…)**  >  **Administrar equipo**. En la ficha **configuración** , haga clic en **@mentions** > desactivar **Mostrar (miembros de) la opción de @team o @[nombre de equipo]**. 
### <a name="automatically-favorite-important-channels"></a>Canales importantes automáticamente favoritos
 Canales importantes favoritos para asegurarse de que todas las personas de su organización se activa en las conversaciones de específicas. Para obtener más información, vea [canales automático favorito para todo el equipo](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).

### <a name="remove-accounts-that-might-not-belong"></a>Quitar las cuentas que no es posible que pertenecen
Aunque los miembros no pueden dejar un equipo de toda la organización, como propietario de un equipo, puede administrar la lista de participantes de equipo mediante la eliminación de las cuentas que no pertenecen. Asegúrese de que usar los equipos para quitar los usuarios de su equipo de toda la organización.  Si usa otra forma de quitar un usuario, como el centro de administración de Microsoft 365 o desde un grupo en Outlook, el usuario podría agregarse al equipo de toda la organización. 

## <a name="faq"></a>Preguntas más frecuentes

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>¿Hay alguna forma para crear un equipo de toda la organización que no sea mediante el cliente de los equipos? 

Los administradores globales sólo pueden crear un equipo de toda la organización mediante el cliente de los equipos. Si su organización limita los equipos de creación para uso de PowerShell, la solución recomendada es agregar los administradores globales para el grupo de seguridad de los usuarios que puede crear un equipo. Si desea más información, consulte [Administrar quién puede crear grupos de Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups). 

Si esto no es una opción, puede crear un equipo público con PowerShell y agregar un administrador global como el propietario del equipo. A continuación, tienen el administrador global haga clic en **... Más opciones** junto al nombre de equipo, haga clic en **Editar equipo**y, a continuación, cambie la privacidad a **toda la organización - todas las personas de su organización se agregará automáticamente**. Tenga en cuenta que sólo los propietarios de equipo pueden tener acceso a la opción **Editar equipo** y los administradores globales sólo pueden ver la opción de **toda la organización** .
