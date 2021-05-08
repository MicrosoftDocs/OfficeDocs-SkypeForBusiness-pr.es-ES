---
title: Administrar la configuración de conferencias de audio para un usuario en Skype Empresarial Online
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
description: 'Como administrador de Microsoft 365 o Office 365, puede editar la configuración de audioconferencia en línea de Skype Empresarial (como el proveedor, número de pago o gratuito predeterminado, id. de conferencia o PIN) para un usuario individual de su organización. '
ms.openlocfilehash: f31648c9b2d50f595dc113b65318f9c6f9204e24
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237306"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Administrar la configuración de conferencias de audio para un usuario en Skype Empresarial Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Si desea administrar la configuración de usuario en Microsoft Teams, vea Administrar la configuración de audioconferencia para un usuario [en Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams).

Como administrador de Microsoft 365 o Office 365, puede editar la configuración de audioconferencia (como el proveedor, número de pago o gratuito predeterminado, id. de conferencia o PIN) para un usuario individual de su organización. Si desea editar la configuración de su organización, vea Administrar la [configuración de audioconferencia de mi organización.](manage-the-audio-conferencing-settings-for-my-organization.md)

 
1. Inicie sesión con su cuenta de trabajo o escuela.
    
2. Seleccione **Centros de administración** > **Skype Empresarial**.
    
3. En el Skype Empresarial de administración, elija **Usuarios.**
    
4. Seleccione el usuario para el que desea administrar la configuración y, a continuación, en el panel Acción, haga clic en **Editar**![Muestra el icono Editar](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Elija **Audioconferencia** en el panel de navegación izquierdo y, a continuación, en la página **Propiedades** para el usuario, modifique cualquiera de las siguientes opciones:
    
|**Setting**|**Descripción**|
|:-----|:-----|
|**Nombre del proveedor** <br/> |Elija su proveedor de la lista.  <br/><br/> **Nota:** Los demás valores de configuración de esta tabla se aplican solo si selecciona Microsoft como el proveedor de audioconferencia.           |
|**Número de teléfono de pago predeterminado** (obligatorio) <br/> |Para los proveedores externos, estos números de teléfono son los que le proporcionó el proveedor de audioconferencia. Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia. Aplicar formato a los números como desee que aparezcan en Skype Empresarial y Microsoft Teams de reunión.  <br/> |
|**Número gratuito predeterminado** <br/> |Para los proveedores externos, estos números de teléfono son los que le proporcionó el proveedor de audioconferencia. Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia. Aplicar formato a los números como desee que aparezcan en Skype Empresarial y Microsoft Teams de reunión.  <br/> |
|**Permitir el uso de los números gratuitos en el puente de Microsoft de su organización para unirse a las reuniones de este usuario** <br/> |Seleccione esta opción si desea permitir el uso de números gratuitos para unirse a reuniones.  <br/> |
|**Enviar información de conferencia por correo electrónico** <br/> |Haga clic en este vínculo solo si desea enviar inmediatamente un correo electrónico al usuario con su número de teléfono e Id. de conferencia. (Este correo electrónico no incluye el PIN). Vea [Enviar un correo electrónico a un usuario con su información de Audioconferencia](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
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
