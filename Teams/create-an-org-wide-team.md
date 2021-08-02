---
title: Crear un equipo de toda la organización en Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo crear y administrar un equipo de toda la organización en Teams proporcionar una forma automática para que todos los miembros de una organización pequeña y mediana colaboren.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 99847583e547deeb2732b88036d4a7a469590ba9
ms.sourcegitcommit: ad215c120d7e550a7aebf2e1bb620c69039e5d8d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2021
ms.locfileid: "53679745"
---
# <a name="create-an-organization-wide-team-in-microsoft-teams"></a>Crear un equipo de toda la organización en Microsoft Teams

Los equipos de toda la organización proporcionan una forma automática para que todos los miembros de una organización pequeña y mediana forme parte de un único equipo de colaboración.

Con equipos de toda la organización, los administradores globales pueden crear fácilmente un equipo público que tenga las siguientes características:
- Extrae todos los usuarios de la organización 
- Mantiene la pertenencia actualizada con Active Directory a medida que los usuarios se unen y abandonan la organización.

Solo los administradores globales pueden crear equipos para toda la organización. Actualmente, un equipo de toda la organización está limitado a organizaciones con no más de 10 000 usuarios. También hay un límite de cinco equipos de toda la organización por inquilino. Al crear un equipo, si se cumplen  estos requisitos, los administradores globales verán a toda la organización como una opción cuando seleccione Crear un equipo **desde cero.** 

![Captura de pantalla de la opción para toda la organización para crear un equipo de toda la organización](media/create-org-wide-team.png "Captura de pantalla de la opción de toda la organización para crear un equipo de toda la organización")

Cuando se crea un equipo de toda la organización, todos los administradores globales y Teams administradores de servicios se agregan como propietarios del equipo y todos los usuarios activos se agregan como miembros del equipo. Los usuarios sin licencia también se agregan al equipo. La primera vez que un usuario sin licencia inicia sesión en Teams, al usuario se le asigna una Microsoft Teams licencia exploratoria. Para obtener más información sobre la licencia exploratoria, consulte Administrar [la Microsoft Teams de Exploración.](teams-exploratory.md) 

Los siguientes tipos de cuentas no se agregarán al equipo de toda la organización:

- Las cuentas que están bloqueadas para iniciar sesión
- Usuarios invitados
- Cuentas de recursos o servicios (por ejemplo, cuentas asociadas con operadores automáticos y colas de llamadas)
- Cuentas de sala o equipamiento
- Cuentas respaldadas por un buzón compartido

A medida que el directorio de su organización se actualiza para incluir nuevos usuarios activos o para deshabilitar cuentas de usuarios que ya no trabajan en su empresa, los cambios se sincronizan automáticamente y los usuarios se agregan o quitan del equipo. Los miembros del equipo no pueden abandonar un equipo de toda la organización. Como propietario del equipo, puede añadir o eliminar usuarios manualmente si es necesario.

> [!NOTE]
> - Si no ve la  opción para toda la organización al crear un equipo y es administrador global, es posible que haya alcanzado el límite de cinco equipos de toda la organización o que su organización tenga más del límite de tamaño actual de 10 000 miembros. Buscamos aumentar este límite en el futuro. Los equipos de toda la organización aún no están disponibles para Teams educativo.
> - Los salas que no forman parte de una lista de salas, equipos y cuentas de recursos pueden agregarse o sincronizarse con el equipo de toda la organización. Los dueños de los equipos pueden eliminar fácilmente estas cuentas del equipo.
> - Todas las acciones del sistema para añadir o eliminar miembros se publican en el Canal general. El canal también será marcado como con nueva actividad en el cliente de Teams.
> - Crearemos automáticamente un equipo de toda la organización para su organización si su organización es nueva en Teams y no tiene más de 5 000 usuarios. El nombre del equipo reflejará el nombre del inquilino y tendrá un Canal general. Los administradores globales pueden editar este equipo como cualquier otro equipo.

## <a name="best-practices"></a>Procedimientos recomendados

Para sacar el máximo partido de su equipo de toda la organización, le recomendamos a los propietarios de los equipos que realicen las siguientes tareas:

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Permitir que sólo los propietarios de los equipos publiquen en el canal general

Reducir el ruido del canal haciendo que sólo los propietarios de los equipos publiquen en el canal general. 

1. Vaya al equipo, busque el canal General y, a continuación, seleccione  >   
2. En la **pestaña Configuración del** canal, haga clic en **Permisos** y, a continuación, seleccione Solo **los propietarios pueden publicar mensajes.**

### <a name="turn-off-team-and-team-name-mentions"></a>Desactivar menciones @equipo y @[nombre del equipo]

Reducir las @menciones para evitar que sobrecarguen toda la organización. 

1. Diríjase al equipo y haga clic en **˙˙˙ Más opciones** > **Administrar equipo**. 
2. En la pestaña **Configuración**, haga clic en <strong>@menciones</strong> > desactivar **Mostrar a los miembros la opción de @equipo o @[nombre del equipo]**. 

### <a name="automatically-show-important-channels"></a>Mostrar automáticamente los canales importantes

Muestre canales importantes para asegurarse de que todos los miembros de su organización participen en conversaciones específicas. Para obtener más información, consulte [Canales favoritos automáticos para todo el equipo](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6). 

### <a name="set-up-channel-moderation"></a>Configurar la moderación del canal

Considere la posibilidad de establecer la moderación del canal y dar capacidad de moderación a ciertos miembros del equipo. (Cuando se configura la moderación, los propietarios de equipos reciben automáticamente capacidades de moderador). Los moderadores pueden:

- Controlar quién puede iniciar una nueva publicación en un canal
- Agregar y quitar moderadores
- Controlar si los miembros del equipo pueden responder a mensajes de canal existentes
- Controlar si los bots y conectores pueden enviar mensajes de canal.

Parara más información, consulte[Configurar y administrar la moderación de canales en Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Eliminar las cuentas que podrían no pertenecer

Aunque los miembros no pueden abandonar un equipo de toda la organización, como propietario del equipo, puede administrar la lista de equipos quitando cuentas que no pertenecen. **Asegúrese de usar Teams para eliminar a los usuarios de su equipo de la organización**. Si usa otra forma de quitar un usuario, como el Centro de administración de Microsoft 365 o de un grupo de Outlook, es posible que el usuario se vuelva a agregar al equipo de toda la organización.

## <a name="faq"></a>Preguntas más frecuentes

### <a name="is-there-a-way-to-create-an-organization-wide-team-other-than-using-the-teams-client"></a>¿Hay alguna forma de crear un equipo para toda la organización que no sea usar el Teams cliente?

Los administradores globales solo pueden crear un equipo de toda la organización mediante el Teams usuario. Si su organización limita la creación de equipos al uso de PowerShell, la solución recomendada es agregar sus administradores globales al grupo de seguridad de usuarios que pueden crear un equipo.

Para obtener más información, vea [Administrar quién puede crear grupos.](/microsoft-365/admin/create-groups/manage-creation-of-groups)

Si esta solución alternativa no es una opción, puede usar PowerShell para crear un equipo público y agregar un administrador global como propietario del equipo. Luego, haga que el administrador global haga clic en **Más opciones** junto al nombre del equipo, haga clic en **Editar equipo**, y luego cambie la privacidad a **Toda la organización - Todos en su organización serán agregados automáticamente**. 

> [!NOTE]
> Solo los propietarios de equipos pueden acceder **a la opción** Editar equipo y solo los administradores globales pueden ver la opción para toda **la** organización.

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-organization-wide-team"></a>¿Hay alguna forma de convertir un equipo existente en un equipo de toda la organización?

Los administradores globales pueden convertir un equipo existente en un equipo de toda la organización editándolo en Teams cliente. Vaya al nombre del equipo, haga clic en **más opciones** > **Editar equipo**.

### <a name="can-i-create-an-organization-wide-team-using-a-team-template"></a>¿Puedo crear un equipo de toda la organización con una plantilla de equipo?

Las plantillas de equipo no se pueden usar para crear un equipo de toda la organización. El trabajo para esta característica está actualmente en curso. 

## <a name="see-also"></a>Vea también

Vea un vídeo sobre [cómo crear un equipo de toda la empresa en Microsoft Teams](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).
