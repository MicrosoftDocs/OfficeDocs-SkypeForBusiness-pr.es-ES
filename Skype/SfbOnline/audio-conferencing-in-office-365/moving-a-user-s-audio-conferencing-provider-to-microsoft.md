---
title: Mover el proveedor de servicios de audioconferencia de un usuario a Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 3a518241-1ecc-406a-93a1-d2653eecc0f5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.PSTNConferencingEnableUsers
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Change your Skype for Business users from third-party audio conferencing providers (ACP) to a Microsoft dial-in conferencing provider. '
ms.openlocfilehash: 8df53a27f3dc0934411284c373206fc4b6dcf41a
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="moving-a-users-audio-conferencing-provider-to-microsoft"></a>Mover el proveedor de servicios de audioconferencia de un usuario a Microsoft

Para utilizar audioconferencia en Office 365 con Skype para empresas y Teams de Microsoft, los usuarios de la organización deben tener una licencia de **Conferencia de Audio** asignada a ellos y su proveedor de conferencia de audio deben establecerse a Microsoft. Vea [probar o comprar Audio conferencia en Office 365](try-or-purchase-audio-conferencing-in-office-365.md) para obtener más información sobre licencias y cuánto cuestan.
  
## <a name="to-move-a-users-audio-conferencing-provider-to-microsoft"></a>Para mover el proveedor de conferencia de audio de un usuario a Microsoft

Si una licencia de **Conferencia de Audio** se asigna a un usuario que no tiene un proveedor de conferencia de audio, proveedor del usuario se establecerá automáticamente en Microsoft y no tienes que hacer nada más. Si el usuario ya tiene un proveedor de conferencia de audio, debe cambiar el proveedor del usuario a Microsoft después de la asignación de una licencia de **Conferencia de Audio** .
  
Para configurar Microsoft como el proveedor de conferencia de audio para un usuario que tiene una licencia de **Conferencia de Audio** asignado pero está utilizando otro proveedor de conferencia de audio, para ello:
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el **Skype para el centro de administración de negocios**, vaya a las **conferencias de Audio**.
    
4. Si ve un titular le notifica que hay usuarios que tienen una **Conferencia de Audio** licencia asignada pero no tiene Microsoft establecer como su proveedor de conferencia de audio aún, haga clic en **haga clic aquí para moverlos**. Si no ve la pancarta, en el **Skype para el centro de administración de negocios** , haga clic en **usuarios**y, a continuación, seleccione el filtro de **usuarios listos para moverlos a las conferencias de Audio** .
    
5. Seleccione los usuarios que desee mover y, a continuación, en el panel Acción, haga clic en **Editar**.
    
6. Seleccione **Microsoft** en la lista **nombre de proveedor** .
    
    > [!NOTE]
    > Cuando se cambia el proveedor de conferencia de audio de un usuario a Microsoft, cambiará la información de conferencia de audio del usuario. Si necesita mantener esta información, por favor grabarlo en algún lugar antes de cambiar el proveedor de cualquiera de los usuarios. 
  
7. Haga clic en **Guardar**.
    
## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- Si selecciona el usuario en la lista, puede ver la información de conferencia de audio predeterminada del usuario, pero no podrá ver la conferencia de audio PIN. Puede restablecer el NIP de un usuario de conferencia de audio haciendo clic en **Restablecer**.
    
- Si desea cambiar la configuración de conferencia de audio de un usuario, puede seleccionar el usuario de la lista y haga clic en **Editar** y realice los cambios en la página de **Propiedades** . 
    
## <a name="related-topics"></a>See also

[Conferencias de acceso telefónico en Office 365](set-up-audio-conferencing.md)
  

