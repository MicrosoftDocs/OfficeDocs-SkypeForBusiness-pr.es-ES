---
title: Administrar la configuración de audioconferencia para un usuario de Skype empresarial online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Como un administrador de Office 365, puede editar la configuración de Audioconferencia de Skype for Business Online, como por ejemplo el proveedor, el número gratuito o de pago predeterminado, el identificador de conferencia o el PIN, de un usuario individual en la organización. '
ms.openlocfilehash: fe6814bee547e80d6bcb6fc367d055dce13d513d
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777995"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Administrar la configuración de audioconferencia para un usuario de Skype empresarial online

> [!Note]
> Si quiere administrar la configuración de usuario en Microsoft Teams, vea [administrar la configuración de audioconferencias para un usuario en Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams).

As an Office 365 admin, you can edit the Audio Conferencing settings—such as the provider, default toll or toll-free number, conference ID, or PIN—for an individual user in your organization. If you want to edit settings for your organization, see [Manage the Audio Conferencing settings for my organization](manage-the-audio-conferencing-settings-for-my-organization.md).

 
1. Inicie sesión con su cuenta profesional o educativa.
    
2. Seleccione **Centros de administración** > **Skype Empresarial**.
    
3. En el centro de administración de Skype empresarial, elija **usuarios**.
    
4. Seleccione el usuario para el que desea administrar la configuración y, a continuación, en el panel Acción, haga clic en **Editar**![Muestra el icono Editar](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Elija **Audioconferencia** en el panel de navegación izquierdo y, a continuación, en la página **Propiedades** para el usuario, modifique cualquiera de las siguientes opciones:
    
|**Setting**|**Descripción**|
|:-----|:-----|
|**Nombre del proveedor** <br/> |Elija su proveedor de la lista.  <br/><br/> **Nota:** Los demás valores de configuración de esta tabla se aplican solo si selecciona Microsoft como el proveedor de audioconferencia.           |
|**Número de teléfono de pago predeterminado** (obligatorio) <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Número de teléfono gratuito predeterminado** <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Permitir el uso de los números gratuitos en el puente de Microsoft de su organización para unirse a las reuniones de este usuario** <br/> |Seleccione esta opción si desea permitir el uso de números gratuitos para unirse a reuniones.  <br/> |
|**Enviar información de conferencia por correo electrónico** <br/> |Click this link only if you want to immediately send an email to the user with his or her conference ID and phone number. (This email does not include the PIN.) See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**Id. de conferencia** <br/> |Select **Reset** if you need to reset the conference ID for the user. For more information, see [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).  <br/> |
|**PULSO** <br/> |Select **Reset** if you need to reset the PIN for the user. For more information, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).  <br/> |
|**Permitir que los autores de llamadas sin autenticar sean las primeras personas en una reunión** <br/> |Seleccione esta opción para permitir que los autores de llamadas sin autenticar sean los primeros en unirse a las reuniones.  <br/> |
|**Restricciones al marcado de salida desde reuniones de este usuario** <br/> |Si desea restringir el marcado de salida solo a llamadas nacionales, o si desea impedir completamente el marcado de salida de las reuniones, seleccione una opción de la lista.  <br/> |
  
![Muestra la página de propiedades de Audioconferencia de un usuario](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Temas relacionados

[Administrar la configuración de Audioconferencia para mi organización](manage-the-audio-conferencing-settings-for-my-organization.md)

[Preguntas comunes sobre Audioconferencia](/MicrosoftTeams/audio-conferencing-common-questions)
