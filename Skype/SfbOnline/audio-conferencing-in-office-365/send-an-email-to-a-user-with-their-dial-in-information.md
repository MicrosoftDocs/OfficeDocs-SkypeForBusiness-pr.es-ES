---
title: Enviar un correo electrónico a un usuario con su Conferencia de audio en Skype empresarial online
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
description: Envíe un correo electrónico a los usuarios con la información de las conferencias de audio en Skype empresarial online.
ms.openlocfilehash: 78ce937bd9aa3bcdab8c860ce261c419af7cc768
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680407"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Enviar un correo electrónico a un usuario con su información de audioconferencia en Skype empresarial online

> [!Note]
> Para obtener información sobre cómo enviar información de audioconferencia a los usuarios en Microsoft Teams, consulte [Enviar un correo electrónico a un usuario con su información de audioconferencia en Microsoft Teasms](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).

A veces, es posible que los usuarios de Skype empresarial le envíen su información de audioconferencia. Puede hacerlo con el **centro de administración de Skype empresarial** y haciendo clic en **enviar información de conferencia por correo electrónico** , en las propiedades de un usuario. Cuando envíe este mensaje de correo electrónico, contendrá toda la información de la audioconferencia, que incluye:
  
- El número de teléfono de la conferencia o el número de teléfono de acceso telefónico local del usuario.
    
- El id. de conferencia del usuario.
    
   
Este es un ejemplo del correo electrónico que se envía:
  
![Correo electrónico de conferencia de acceso telefónico](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar un correo electrónico con información sobre las conferencias de audio a un usuario

1. En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Conferencia de audio**, haga clic en **enviar información de conferencia por correo electrónico**.

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al centro de administración > **Skype empresarial**y, a continuación, en la barra de navegación izquierda, haga clic en **audioconferencia**.
    
3. Haga clic en **usuarios**y, a continuación, seleccione el usuario.
    
4. En el panel de acciones, haga clic en **Enviar información de conferencia por correo electrónico**.
    
> [!TIP]
> También puede enviar correos electrónicos al usuario con la configuración de audioconferencia modificando las propiedades del usuario y, a continuación, haciendo clic en **audioconferencia** > **enviar información de conferencia por correo electrónico**. 

## <a name="what-else-should-you-know-about-this-email"></a>¿Qué más debe saber sobre este correo electrónico?

- Se envían varios correos electrónicos a los usuarios de su organización después de que estén habilitados para las conferencias de audio:
    
  - Cuando se les asigna una licencia de **conferencias de audio** .
    
  - Cuando restablece manualmente el PIN de conferencia de audio del usuario.
    
  - Al restablecer de forma manual el id. de conferencia del usuario.
    
  - Cuando se quita una licencia de **conferencias de audio** de ellos.
    
  - Cuando el proveedor de servicios de audioconferencia de un usuario cambia de Microsoft a otro proveedor o a **ninguno**.
    
  - Cuando se cambia el proveedor de servicios de audioconferencia de un usuario a Microsoft.
    
- De forma predeterminada, el remitente de los mensajes de correo electrónico será de Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell y el cmdlet [set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) . Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios, debe hacer lo siguiente:
    
  - Escriba la dirección de correo electrónico en el parámetro SendEmailFromAddress.
    
  - Establezca el parámetro SendEmailOverride en True.
    
  - Escriba el nombre para mostrar del correo electrónico en el parámetro SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Si quiere cambiar la información de la dirección de correo electrónico, asegúrese de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada configurada. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Para enviar un correo electrónico al usuario con la información de la audioconferencia, ejecute lo siguiente:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, por ejemplo, cuando está realizando cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
