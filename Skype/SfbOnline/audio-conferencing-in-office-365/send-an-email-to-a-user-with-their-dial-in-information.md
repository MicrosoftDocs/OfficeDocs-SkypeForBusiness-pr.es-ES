---
title: Enviar un correo electrónico a un usuario con sus conferencias de Audio en Skype para profesionales en línea
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Enviar un correo electrónico con su información de conferencia de audio de los usuarios en Skype para profesionales en línea.
ms.openlocfilehash: 80cfbd88b8c933e2b1e66d6348deff111a45f8e3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229325"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>Enviar un correo electrónico a un usuario con su información de conferencia de Audio en Skype para profesionales en línea

> [!Note]
> Para obtener información acerca de cómo enviar información de conferencia de Audio para los usuarios de Microsoft Teams, vea [Enviar un correo electrónico a un usuario con su información de conferencia de Audio en Microsoft Teasms](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).

En ocasiones, Skype para usuarios profesionales necesite enviarles su información de conferencia de Audio. Puede hacer esto utilizando el **Skype para el centro de administración de negocio** y haciendo clic en **Enviar información de conferencia a través de correo electrónico** en las propiedades de un usuario. Al enviar este correo electrónico, contendrá toda la información de conferencia de audio, incluidos:
  
- El número de teléfono de la conferencia o el número de teléfono de acceso telefónico local del usuario.
    
- El id. de conferencia del usuario.
    
   
Este es un ejemplo del correo electrónico que se envía:
  
![Correo electrónico de conferencia de acceso telefónico](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar un correo electrónico con información de conferencia de audio a un usuario

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Conferencias de Audio**, haga clic en **Enviar información de conferencia en el correo electrónico**.

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al **Centro de administración de Office 365** > **Skype para la empresa**y en el panel de navegación izquierdo, haga clic en **conferencias de Audio**.
    
3. Haga clic en **usuarios**y, a continuación, seleccione el usuario.
    
4. En el panel de acciones, haga clic en **Enviar información de conferencia por correo electrónico**.
    
> [!TIP]
> También puede enviar correo electrónico al usuario con la configuración de conferencias de audio mediante la edición de las propiedades del usuario y, a continuación, haciendo clic en **conferencias de Audio** > **Enviar información de conferencia a través de correo electrónico**. 

## <a name="what-else-should-you-know-about-this-email"></a>¿Qué más debe saber sobre este correo electrónico?

- Hay varios correos electrónicos que se envían a los usuarios de su organización después de que están habilitados para conferencias de audio:
    
  - Cuando se asigna una licencia de **Conferencias de Audio** a ellos.
    
  - Al restablecer manualmente PIN de conferencia de audio del usuario.
    
  - Al restablecer de forma manual el id. de conferencia del usuario.
    
  - Cuando se quita una licencia de **Conferencias de Audio** de ellas.
    
  - Cuando se cambia el proveedor de conferencia de audio para un usuario de Microsoft a otro proveedor o **Ninguno**.
    
  - Cuando se cambia el proveedor de conferencia de audio para un usuario a Microsoft.
    
- De forma predeterminada, será el remitente de los mensajes de correo electrónico de Office 365, pero puede cambiar la dirección de correo electrónico y nombre para mostrar mediante el uso de Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) . Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios, debe:
    
  - Escriba la dirección de correo electrónico en el parámetro SendEmailFromAddress.
    
  - Establezca el parámetro SendEmailOverride en True.
    
  - Escriba el nombre para mostrar de correo electrónico en el parámetro SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Si quiere cambiar la información de la dirección de correo electrónico, asegúrese de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada configurada. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Para enviar un correo electrónico al usuario con su información de conferencia de audio, ejecute lo siguiente:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
