---
title: Administrar la configuración de Audioconferencia de un usuario en Skype for Business Online
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Como un administrador de Office 365, puede editar la configuración de Audioconferencia de Skype for Business Online, como por ejemplo el proveedor, el número gratuito o de pago predeterminado, el identificador de conferencia o el PIN, de un usuario individual en la organización. '
ms.openlocfilehash: 11ab14b3ebba54e1af8125c2d2f6c2acbd0730b7
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779059"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Administrar la configuración de Audioconferencia de un usuario en Skype for Business Online

> [!Note]
> Si desea administrar la configuración de usuario en Microsoft Teams, consulte [Administrar la configuración de Audioconferencia de un usuario en Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams).

Como un administrador de Office 365, puede editar la configuración de Audioconferencia, como por ejemplo el proveedor, el número gratuito o de pago predeterminado, el identificador de conferencia o el PIN, de un usuario individual en la organización. Si desea editar la configuración de la organización, vea [Administrar la configuración de Audioconferencia de mi organización](manage-the-audio-conferencing-settings-for-my-organization.md).

 
1. Inicie sesión en Office 365 con su cuenta de trabajo o escuela.
    
2. Seleccione **Centros de administración** > **Skype for Business**.
    
3. En el Centro de administración de Skype for Business, seleccione **Usuarios**.
    
4. Seleccione el usuario para el que desea administrar la configuración y, a continuación, en el panel Acción, haga clic en **Editar**![Muestra el icono Editar](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Elija **Audioconferencia** en el panel de navegación izquierdo y, a continuación, en la página **Propiedades** para el usuario, modifique cualquiera de las siguientes opciones:
    
|**Valor**|**Descripción**|
|:-----|:-----|
|**Nombre del proveedor** <br/> |Elija su proveedor de la lista.  <br/><br/> **Nota:** Los demás valores de configuración de esta tabla se aplican solo si selecciona Microsoft como el proveedor de audioconferencia.           |
|**Número de teléfono de pago predeterminado** (obligatorio) <br/> |Para los proveedores externos, estos números de teléfono son los que le proporcionó el proveedor de audioconferencia. Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia. Asigne a los números el formato con el que quiere que aparezcan en las convocatorias de reunión de Skype for Business y Microsoft Teams.  <br/> |
|**Número de teléfono gratuito predeterminado** <br/> |Para los proveedores externos, estos números de teléfono son los que le proporcionó el proveedor de audioconferencia. Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia. Asigne a los números el formato con el que quiere que aparezcan en las convocatorias de reunión de Skype for Business y Microsoft Teams.  <br/> |
|**Permitir el uso de los números gratuitos en el puente de Microsoft de su organización para unirse a las reuniones de este usuario** <br/> |Seleccione esta opción si desea permitir el uso de números gratuitos para unirse a reuniones.  <br/> |
|**Enviar información de conferencia mediante correo electrónico** <br/> |Haga clic en este vínculo solo si desea enviar inmediatamente un correo electrónico al usuario con su número de teléfono e Id. de conferencia. (Este correo electrónico no incluye el PIN). Vea [Enviar un correo electrónico a un usuario con su información de Audioconferencia](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**Id. de conferencia** <br/> |Seleccione **Restablecer** si desea restablecer el Id. de conferencia para el usuario. Para obtener más información, consulte [Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md).  <br/> |
|**PIN** <br/> |Seleccione **Restablecer** si desea restablecer el PIN para el usuario. Para obtener más información, vea [Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin.md).  <br/> |
|**Permitir que los autores de llamadas sin autenticar sean las primeras personas en una reunión** <br/> |Seleccione esta opción para permitir que los autores de llamadas sin autenticar sean los primeros en unirse a las reuniones.  <br/> |
|**Restricciones al marcado de salida desde reuniones de este usuario** <br/> |Si desea restringir el marcado de salida solo a llamadas nacionales, o si desea impedir completamente el marcado de salida de las reuniones, seleccione una opción de la lista.  <br/> |
  
![Muestra la página de propiedades de Audioconferencia de un usuario](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Temas relacionados

[Administrar la configuración de Audioconferencia para mi organización](manage-the-audio-conferencing-settings-for-my-organization.md)

[Preguntas comunes sobre Audioconferencia](/MicrosoftTeams/audio-conferencing-common-questions)
