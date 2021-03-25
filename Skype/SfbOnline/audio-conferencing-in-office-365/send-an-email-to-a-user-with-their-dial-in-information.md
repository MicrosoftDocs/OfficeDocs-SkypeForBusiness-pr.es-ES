---
title: Enviar un correo electrónico a un usuario con sus audioconferencias en Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
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
description: Envíe a los usuarios un correo electrónico con su información de audioconferencia en Skype Empresarial Online.
ms.openlocfilehash: f070353069c937a62935e1cc570ebae6c0e981db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110002"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Enviar un correo electrónico a un usuario con su información de audioconferencia en Skype Empresarial Online

> [!Note]
> Para obtener información sobre cómo enviar información de audioconferencia a usuarios de Microsoft Teams, vea Enviar un correo electrónico a un usuario con su información de audioconferencia en [Microsoft Teasms.](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)

A veces, es posible que los usuarios de Skype Empresarial necesiten que les envíe su información de audioconferencia. Para ello, use el Centro de administración  de **Skype Empresarial** y haga clic en Enviar información de conferencia por correo electrónico en las propiedades de un usuario. Al enviar este correo electrónico, contendrá toda la información de audioconferencia, incluidos:
  
- El número de teléfono de la conferencia o el número de teléfono de acceso telefónico local del usuario.
    
- El id. de conferencia del usuario.
    
   
Este es un ejemplo del correo electrónico que se envía:
  
![Correo electrónico de conferencia de acceso telefónico](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar un correo electrónico con información de audioconferencia a un usuario

1. En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar.**

3. En **Audioconferencia,** haga clic **en Enviar información de conferencia por correo electrónico.**

1. Inicie sesión con su cuenta de trabajo o escuela.
    
2. Vaya al centro de administración > **Skype Empresarial** y, en el panel de navegación izquierdo, haga clic en **Audioconferencia.**
    
3. Haga **clic en** Usuarios y, a continuación, seleccione el usuario.
    
4. En el panel de acciones, haga clic en **Enviar información de conferencia por correo electrónico**.
    
> [!TIP]
> También puede enviar correo electrónico al usuario con la configuración de audioconferencia editando las propiedades del usuario y haciendo clic en **Audioconferencia** Enviar información de conferencia  >  **por correo electrónico.** 

## <a name="what-else-should-you-know-about-this-email"></a>¿Qué más debe saber sobre este correo electrónico?

- Hay varios correos electrónicos que se envían a los usuarios de su organización después de que estén habilitados para las audioconferencias:
    
  - Cuando se les asigna una licencia **de** audioconferencia.
    
  - Cuando restablezca manualmente el PIN de audioconferencia del usuario.
    
  - Al restablecer de forma manual el id. de conferencia del usuario.
    
  - Cuando se **quita una licencia de** conferencias de audio.
    
  - Cuando el proveedor de audioconferencias de un usuario se cambia de Microsoft a otro proveedor o **Ninguno.**
    
  - Cuando el proveedor de audioconferencias de un usuario se cambia a Microsoft.
    
- De forma predeterminada, el remitente de los correos electrónicos será de Microsoft 365 u Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar mediante Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios, debe:
    
  - Escriba la dirección de correo electrónico en el parámetro SendEmailFromAddress.
    
  - Establezca el parámetro SendEmailOverride en True.
    
  - Escriba el nombre para mostrar del correo electrónico en el parámetro SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Si quiere cambiar la información de la dirección de correo electrónico, asegúrese de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada configurada. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
    Para enviar un correo electrónico al usuario con su información de audioconferencia, ejecute lo siguiente:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Por qué necesita usar Microsoft 365 u Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del Centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar audioconferencias en Microsoft 365 u Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)