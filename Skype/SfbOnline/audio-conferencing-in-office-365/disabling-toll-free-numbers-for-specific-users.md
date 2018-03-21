---
title: "Desactivación de números de teléfono gratuitos para usuarios específicos"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 02/23/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Los administradores pueden controlar cómo los organizadores pueden usar números de teléfono gratuitos para sus reuniones."
ms.openlocfilehash: fb4b0f8725608928e686307845871b4f5c1976d9
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a>Desactivación de números de teléfono gratuitos para usuarios específicos

Si su organización tiene números gratuitos en su Microsoft Audio Conferencing Bridge, puede permitir o impedir su uso en las reuniones de organizadores específicos.  

De forma predeterminada, todos los usuarios de su organización están habilitados para el uso de números de teléfono gratuitos, lo que significa que esos números, si está disponible, pueden utilizarse por los participantes para unirse a sus reuniones. Si no es el comportamiento deseado de algunos usuarios de su organización, puede evitar que usuarios específicos utilizando esos números en sus reuniones a través de un control de habilitación número gratuito. 

Cuando los números gratuitos están deshabilitados para el organizador de una determinada: 
 - Ya no se incluirán un número gratuito en su o invita su reunión. 
 - Ya no se mostrarán en la página "Buscar un número local" que se hace referencia en su números gratuitos o invita su reunión. 
 - Los participantes no pueden participar en la reunión del organizador determinado si marcar cualquier número gratuito de la organización. 
 - Se programará automáticamente todas las reuniones del organizador y se quitará el número gratuito de ellos.  

    > [!IMPORTANT]
    > Esto volverá a enviar todas las invitaciones de correo electrónico del organizador a todos los participantes de las reuniones. 

 - Los participantes pueden continuar unirse a reuniones del organizador con números de teléfono. 

## <a name="disabling-toll-free-numbers-for-specific-users-using-the-skype-for-business-admin-center"></a>Desactivación de números de teléfono gratuitos para usuarios específicos mediante el Skype para el centro de administración de negocios 
 1. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**. 
 2. En el Skype para el centro de administración de negocios, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles. 
 3. En el panel de acciones, haga clic en **Editar**. 
 4. Active o desactive **Permitir mediante números de teléfono gratuitos para unirse a las reuniones de este usuario**. 
 5. Haga clic en **Guardar**. 
 
## <a name="disabling-toll-free-numbers-for-specific-users-using-powershell"></a>Desactivación de números de teléfono gratuitos para usuarios específicos mediante PowerShell  

Puede utilizar el parámetro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser para habilitar o deshabilitar este control. Por ejemplo: 

 - Conjunto CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
