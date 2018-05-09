---
title: Administrar la configuración de conferencia de Audio para un usuario
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Como un administrador de Office 365, puede editar la configuración de conferencias de Audio, como el proveedor, pago predeterminado o número de teléfono gratuito, identificador de conferencia o PIN: para un usuario individual en la organización. Si desea editar la configuración de la organización, vea Administrar la conferencia de Audio configuración para mi organización.'
ms.openlocfilehash: 141ede21a99ff251786c7dfc63f4c55358b61c72
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
---
# <a name="manage-the-audio-conferencing-settings-for-a-user"></a>Administrar la configuración de conferencia de Audio para un usuario

Como un administrador de Office 365, puede editar la configuración de conferencias de Audio, como el proveedor, pago predeterminado o número de teléfono gratuito, identificador de conferencia o PIN: para un usuario individual en la organización. Si desea editar la configuración de la organización, vea [Administrar la configuración de conferencia de Audio de mi organización](manage-the-audio-conferencing-settings-for-my-organization.md).

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En las **Conferencias de Audio**, modifique cualquiera de las siguientes opciones:

|**Configuración**|**Descripción**|
|:-----|:-----|
|**Audioconferencias**|Para activar la conferencia de audio o desactivada para el usuario, haga clic en **Editar** junto a **Conferencias de Audio**y, a continuación, en el panel de **Conferencia de Audio** , activar o desactivar el **conferencias de Audio** .|
|**Enviar información de conferencia en el correo electrónico**  |Haga clic en este vínculo sólo si desea enviar un correo electrónico inmediatamente al usuario con su número de identificador y el teléfono de conferencia. (Este correo electrónico no incluye el PIN). Vea [Enviar un correo electrónico a un usuario con su información de conferencia de Audio](send-an-email-to-a-user-with-their-dial-in-information.md).  |
|**Id. de conferencia**  |Haga clic en **Restablecer el identificador de conferencia** si necesita restablecer el identificador de conferencia para el usuario. Para obtener más información, consulte [Restablecer un identificador de conferencia para un usuario](reset-a-conference-id-for-a-user.md).  |
|**PIN** |Haga clic en **Restablecer PIN** si necesita restablecer el PIN para el usuario. Para obtener más información, vea [Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin.md). |
|**Valor predeterminado de número de teléfono de pago de conferencia** (obligatorio) |Se trata de números que se establecen en el puente de conferencia de audio. Dar formato a los números tal como desea que aparezca en Skype para las convocatorias de reunión de Microsoft Teams y profesionales. Para cambiar el número de teléfono de pago predeterminado, haga clic en **Editar** junto a la **conferencia de Audio** y, en el el panel de **Conferencia de Audio** , seleccione un número en **número de teléfono de pago**. |
|**Invitaciones de este usuario pueden incluir el número de teléfono gratuito**|Para cambiar esta configuración, haga clic en **Editar** junto a **Conferencias de Audio** y en el panel de **Conferencia de Audio** , activar o desactivar el **incluir los números gratuitos en convocatorias de reunión de este usuario** . |
|**Permisos de acceso telefónico de salida**|Para cambiar esta configuración, haga clic en **Editar** junto a **Conferencias de Audio** y en el panel de **Conferencia de Audio** , elija una opción bajo el **permiso de acceso telefónico de salida de las reuniones**.|

![Muestra la configuración de conferencia de Audio para un usuario](../images/sfbaudioconf-usersettings.png)
 
![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**
 
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Seleccione **Centros de administración** > **Skype Empresarial**.
    
3. En Skype para el centro de administración de negocio, elija **los usuarios**.
    
4. Seleccione el usuario para el que desea administrar la configuración y, a continuación, en el panel de acciones, haga clic en **Editar**![muestra el icono de edición](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Elija **conferencias de Audio** en el panel de navegación izquierdo y, a continuación, en la página de **Propiedades** para el usuario, modificar cualquiera de las siguientes opciones:
    
|**Configuración**|**Descripción**|
|:-----|:-----|
|**Nombre del proveedor** <br/> |Elija su proveedor de la lista.  <br/><br/> **Nota:** El resto de la configuración de esta tabla se aplica sólo si selecciona Microsoft como el proveedor de conferencia de audio.           |
|**Número de teléfono de pago predeterminado** (obligatorio) <br/> |Para los proveedores de un tercero, estos números de teléfono son los que le proporcionó el proveedor de conferencia de audio. Si el usuario está utilizando Microsoft como proveedor de conferencias de audio, éstos serán los números que se establecen en el puente de conferencia de audio. Dar formato a los números tal como desea que aparezca en Skype para las convocatorias de reunión de Microsoft Teams y profesionales.  <br/> |
|**Número de teléfono gratuito de forma predeterminada** <br/> |Para los proveedores de un tercero, estos números de teléfono son los que le proporcionó el proveedor de conferencia de audio. Si el usuario está utilizando Microsoft como proveedor de conferencias de audio, éstos serán los números que se establecen en el puente de conferencia de audio. Dar formato a los números tal como desea que aparezca en Skype para las convocatorias de reunión de Microsoft Teams y profesionales.  <br/> |
|**Permitir el uso de los números gratuitos en el puente de Microsoft de su organización para unirse a las reuniones de este usuario** <br/> |Seleccione esta opción si desea permitir que al usuario de los números gratuitos para unirse a una conferencia.  <br/> |
|**Enviar información de conferencia a través de correo electrónico** <br/> |Haga clic en este vínculo sólo si desea enviar un correo electrónico inmediatamente al usuario con su número de identificador y el teléfono de conferencia. (Este correo electrónico no incluye el PIN). Vea [Enviar un correo electrónico a un usuario con su información de conferencia de Audio](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**Id. de conferencia** <br/> |Seleccione **Restablecer** si desea restablecer el identificador de conferencia para el usuario. Para obtener más información, consulte [Restablecer un identificador de conferencia para un usuario](reset-a-conference-id-for-a-user.md).  <br/> |
|**PIN** <br/> |Seleccione **Restablecer** si desea restablecer el PIN para el usuario. Para obtener más información, vea [Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin.md).  <br/> |
|**Permitir que los autores de llamadas sin autenticar a ser el primer personas en una reunión** <br/> |Seleccione esta opción para permitir que los autores de llamadas sin autenticar se unirse a reuniones en primer lugar.  <br/> |
|**Restricciones al marcado-outs de reuniones de este usuario** <br/> |Si desea restringir el marcado-outs a sólo nacionales, o si desea impedir que todos los marcado-outs de reuniones, seleccione una opción de la lista.  <br/> |
  
![Muestra la página de propiedades de conferencia de Audio para un usuario](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>See also

[Administrar la configuración de Audioconferencia para mi organización](manage-the-audio-conferencing-settings-for-my-organization.md)

[Preguntas comunes sobre Audioconferencia](audio-conferencing-common-questions.md)
