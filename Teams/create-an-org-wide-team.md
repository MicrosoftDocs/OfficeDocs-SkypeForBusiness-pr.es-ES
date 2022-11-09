---
title: Usar equipos de toda la organización en Microsoft Teams para ayudar a todos a colaborar
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo crear y administrar un equipo de toda la organización en Teams para proporcionar una forma para que todos los usuarios de una organización pequeña o mediana puedan colaborar.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- EngageScoreOct2022
- ContentEnagagementFY23
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee17d482c311a4bdd92ebad55e29058104a89b98
ms.sourcegitcommit: e5f5a1a164576b317e89340e233c9b67f082d19c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2022
ms.locfileid: "68890059"
---
# <a name="use-organization-wide-teams-in-microsoft-teams-to-help-everyone-collaborate"></a>Usar equipos de toda la organización en Microsoft Teams para ayudar a todos a colaborar

Los administradores globales pueden crear equipos para toda la organización que proporcionan a todos los miembros de una organización de tamaño pequeño a mediano una forma de formar parte de un único equipo y de colaboración. Los equipos de toda la organización incluyen automáticamente todos los usuarios de la organización y mantienen la pertenencia actualizada a medida que los usuarios se unen y abandonan la organización.

Si su organización es nueva en Teams y no tiene más de 5000 usuarios, se creará automáticamente un equipo de toda la organización. Los equipos de toda la organización están limitados a organizaciones que no tienen más de 10 000 usuarios. Puede tener hasta cinco equipos de toda la organización. 

## <a name="create-an-organization-wide-team"></a>Crear un equipo para toda la organización

Hay dos formas de crear un equipo para toda la organización:

- Convertir un equipo existente en un equipo de toda la organización. Vaya al nombre del equipo y haga clic en **Más opciones** > **Editar equipo**.

- [Cree un nuevo equipo desde cero](https://support.microsoft.com/office/174adf5f-846b-4780-b765-de1a0a737e2b) y elija la opción **para toda** la organización.

    ![Captura de pantalla de la opción de toda la organización para crear un equipo de toda la organización.](media/create-org-wide-team.png "Captura de pantalla de la opción De toda la organización para crear un equipo de toda la organización")

## <a name="types-of-users-in-an-organization-wide-team"></a>Tipos de usuarios de un equipo de toda la organización

Cuando se crea un equipo para toda la organización, todos los administradores globales y administradores de Teams se agregan como propietarios del equipo y todos los usuarios activos se agregan como miembros del equipo. Los miembros del equipo no pueden abandonar un equipo de toda la organización, pero los propietarios del equipo pueden agregar o quitar usuarios manualmente si es necesario. Cuando Teams agrega o quita a alguien automáticamente, se envía una notificación al canal General.

Los usuarios sin licencia también se agregan al equipo. La primera vez que un usuario sin licencia inicia sesión en Teams, se le asigna una licencia exploratoria de Microsoft Teams. Para obtener más información sobre la licencia exploratoria, consulte [Administrar la licencia exploratoria de Microsoft Teams](teams-exploratory.md).

Los siguientes tipos de cuentas no se agregarán al equipo de toda la organización:

- Cuentas que están bloqueadas para el inicio de sesión
- Invitados
- Cuentas de recursos o servicios (por ejemplo, cuentas asociadas con operadores automáticos y colas de llamadas)
- Cuentas de sala o equipamiento
- Cuentas respaldadas por un buzón compartido

> [!NOTE]
> Los salones que no forman parte de una lista de salas, equipos y cuentas de recursos pueden agregarse o sincronizarse con el equipo de toda la organización. Los dueños de los equipos pueden eliminar fácilmente estas cuentas del equipo.

## <a name="options-to-get-the-most-out-of-an-organization-wide-team"></a>Opciones para sacar el máximo partido a un equipo de toda la organización

Para sacar el máximo partido a su equipo de toda la organización, le recomendamos que los propietarios del equipo realicen las siguientes tareas:

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Permitir que sólo los propietarios de los equipos publiquen en el canal general

Reducir el ruido del canal haciendo que sólo los propietarios de los equipos publiquen en el canal general.

1. Vaya al equipo, busque el canal General y, a continuación, seleccione **... Más opciones** > **Administrar canal**.
2. En la pestaña **Configuración de canal** , haga clic en **Permisos** y, a continuación, seleccione **Solo los propietarios pueden publicar mensajes**.

### <a name="turn-off-team-and-team-name-mentions"></a>Desactivar menciones @equipo y @[nombre del equipo]

Reducir las @menciones para evitar que sobrecarguen toda la organización.

1. Vaya al equipo y haga clic en **... Más opciones** \> **Administrar equipo**.
2. En la pestaña **Configuración** , haga clic **en @mentions** \> desactive **Mostrar a los miembros la opción de @team o @[nombre del equipo]**.

### <a name="automatically-show-important-channels"></a>Mostrar automáticamente los canales importantes

Muestre canales importantes para asegurarse de que todos los miembros de su organización participen en conversaciones específicas. Para obtener más información, consulte [Canales favoritos automáticos para todo el equipo](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).

### <a name="set-up-channel-moderation"></a>Configurar la moderación del canal

Considere la posibilidad de establecer la moderación del canal y dar capacidad de moderación a ciertos miembros del equipo. (Cuando se configura la moderación, a los propietarios de equipos se les conceden automáticamente las capacidades de moderador). Los moderadores pueden:

- Controlar quién puede iniciar una nueva publicación en un canal
- Agregar y quitar moderadores
- Controlar si los miembros del equipo pueden responder a los mensajes del canal existentes
- Controlar si los bots y conectores pueden enviar mensajes de canal.

Parara más información, consulte[Configurar y administrar la moderación de canales en Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Eliminar las cuentas que podrían no pertenecer

Aunque los miembros no pueden abandonar un equipo de toda la organización, como propietario del equipo, puede administrar la lista de equipos quitando las cuentas que no pertenecen. **Asegúrese de usar Teams para eliminar a los usuarios de su equipo de la organización**. Si usa otra forma de quitar un usuario, como el Centro de administración de Microsoft 365 o de un grupo en Outlook, es posible que el usuario se agregue de nuevo al equipo de toda la organización.

## <a name="related-topics"></a>Temas relacionados

Vea un vídeo sobre [Cómo crear un equipo de toda la organización en Microsoft Teams](https://www.youtube.com/watch?v=x3qGlwwCz_w).
