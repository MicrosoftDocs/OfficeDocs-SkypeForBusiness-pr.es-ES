---
title: Administrar la configuración de Audioconferencia para los usuarios
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Un administrador de Microsoft 365 o Office 365 puede editar la configuración de Audioconferencia de Teams, incluido el proveedor, el número de pago o gratuito predeterminado, el id. de conferencia o el PIN de un usuario.
ms.openlocfilehash: 9b68ea4452928ce739ec8429ed9b71bfaca91cf4
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641911"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-microsoft-teams"></a>Administrar la configuración de Audioconferencia para un usuario en Microsoft Teams

Como administrador de Microsoft 365 o Office 365, puede editar la configuración de Audioconferencia (como el proveedor, el número de pago o gratuito predeterminado, el id. de conferencia o el PIN) para un usuario individual de su organización. Si desea editar la configuración de su organización, consulte [Administrar la configuración de Audioconferencia para su organización](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, haga clic en **Usuarios** y, a continuación, seleccione el usuario en la lista de usuarios disponibles.

2. Haga clic en **Editar**.

3. En **Audioconferencia**, modifique cualquiera de las siguientes opciones:

|**Setting**|**Descripción**|
|:-----|:-----|
|**Audioconferencia**|Para activar o desactivar la audioconferencia para el usuario, haga clic en **Editar** junto a **Audioconferencia** y, a continuación, en el panel **Audioconferencia** , active o desactive **Audioconferencia** .|
|**Enviar información de conferencia por correo electrónico**  |Haga clic en este vínculo solo si desea enviar inmediatamente un correo electrónico al usuario con su número de teléfono e Id. de conferencia. (Este correo electrónico no incluye el PIN). Vea [Enviar un correo electrónico a un usuario con su información de Audioconferencia](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).  |
|**Id. de conferencia**  |Haga clic en **Restablecer id** . de conferencia si necesita restablecer el id. de conferencia para el usuario. Para obtener más información, consulte [Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md).  |
|**Anclar** |Haga clic en **Restablecer PIN** si necesita restablecer el PIN del usuario. Para obtener más información, vea [Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md). |
|**Número de teléfono de pago de conferencia predeterminado** (obligatorio) |Los números establecidos en el puente de audioconferencia. Aplique formato a los números como desee que aparezcan en las convocatorias de reunión de Teams. Para cambiar el número de pago predeterminado, haga clic en **Editar** junto a **Audioconferencia** y, en el panel **Audioconferencia** , seleccione un número en **Número** de pago. También puede establecer números de teléfono agregándolos a TeamsAudioConferencingPolicy y asignando la directiva a los usuarios. Los números de teléfono agregados a la directiva tienen prioridad sobre los números de teléfono establecidos con el **número de teléfono de pago para conferencias predeterminadas**. Si no se agregan números de teléfono a TeamsAudioConferencingPolicy, el número de teléfono establecido mediante **el número de teléfono de pago de conferencias predeterminadas** se mostrará en las convocatorias de reunión de Microsoft Teams. |
|**Las invitaciones de este usuario pueden incluir un número gratuito**|Esta configuración solo se puede cambiar con TeamsAudioconferecningPolicy. |
|**Los usuarios no autenticados pueden ser la primera persona de la reunión**|Para cambiar esta configuración, active o desactive la casilla **Los usuarios no autenticados pueden ser la primera persona de la reunión** .
|**Permisos de acceso telefónico local**|Para cambiar esta configuración, haga clic en **Editar** junto a **Audioconferencia** y, en el panel **Audioconferencia** , elija una opción en **Salida de reuniones**.|

![Muestra la configuración de Audioconferencia para un usuario.](media/teams-manage-audio-conferencing-settings-for-a-user-image1.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Temas relacionados

[Administrar la configuración de Audioconferencia para su organización](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

[Preguntas frecuentes sobre Audioconferencia](audio-conferencing-common-questions.md)
