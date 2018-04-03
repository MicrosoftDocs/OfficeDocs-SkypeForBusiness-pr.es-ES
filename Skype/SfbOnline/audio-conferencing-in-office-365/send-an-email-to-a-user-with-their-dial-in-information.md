---
title: Enviar un correo electrónico a un usuario con su información de acceso telefónico
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Enviar un correo electrónico con su información de conferencia de audio de los usuarios.
ms.openlocfilehash: f1e4ddd06011d7eb85253e06d6b7de775a207683
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a>Enviar un correo electrónico a un usuario con su información de conferencias de Audio

A veces quizá tenga Skype para usuarios de negocios o Teams de Microsoft le envíe su información de conferencia de Audio. Puede hacerlo utilizando el **Skype para el centro de administración de negocios** y hacer clic en **Enviar información de conferencia a través de correo electrónico** en las propiedades de un usuario. Al enviar este correo electrónico, contendrá toda la información de conferencia de audio, incluyendo:
  
- El número de teléfono de la conferencia o el número de teléfono de acceso telefónico local del usuario.
    
- El id. de conferencia del usuario.
    
    > [!NOTE]
    > Identificadores estáticos se utilizan cuando las personas de la organización no desean recordar un número aleatorio; Puede seleccionar un determinado número o utilizar uno que sea fácil de recordar. Cuando se utilizan identificadores de conferencia dinámico, cada reunión programaciones de un usuario obtener asignará un identificador único conferencia. Si desea asignar el dinámico en lugar de conferencia estática IDs, [vaya aquí](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
Aquí es un ejemplo del correo electrónico que se envía:
  
![Correo electrónico de conferencia de acceso telefónico](../images/audio-conferencing-info.png)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar un correo electrónico con información de conferencia de audio a un usuario

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Ir al **Centro de administración de Office 365** > **Skype para el negocio**y la exploración de la izquierda, haga clic en **conferencias de Audio**.
    
3. Haga clic en **usuarios**y, a continuación, seleccione el usuario.
    
4. En el panel de acciones, haga clic en **Enviar información de conferencia por correo electrónico**.
    
> [!TIP]
> También puede enviar correo electrónico al usuario con la configuración de conferencia de audio editando las propiedades del usuario y, a continuación, haga clic en **conferencias de Audio** > **Enviar información de conferencia a través de correo electrónico**. 
  
## <a name="what-else-should-you-know-about-this-email"></a>¿Qué más debe saber sobre este correo electrónico?

- Hay varios correos electrónicos que se envían a los usuarios de la organización después de que se hayan habilitado para conferencias de audio:
    
  - Cuando se asigna una licencia de **Conferencia de Audio** a ellos.
    
  - Cuando restablece manualmente conferencias de audio PIN del usuario.
    
  - Al restablecer de forma manual el id. de conferencia del usuario.
    
  - Cuando se quita una licencia de **Conferencia de Audio** de ellos.
    
  - Cuando se cambia el proveedor de conferencia de audio para un usuario de Microsoft a otro proveedor, o **Ninguno**.
    
  - Cuando se cambia el proveedor de conferencia de audio de un usuario a Microsoft.
    
- De forma predeterminada, será el remitente de los mensajes de correo electrónico de Office 365, pero puede cambiar la dirección de correo electrónico y nombre para mostrar mediante el uso de Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) . Para realizar cambios en la dirección de correo electrónico que está enviando el correo electrónico a los usuarios, debe:
    
  - Escriba la dirección de correo electrónico en el parámetro SendEmailFromAddress.
    
  - Establezca el parámetro SendEmailOverride en True.
    
  - Escriba el nombre de pantalla de correo electrónico en el parámetro SendEmailFromDisplayName.
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > Si quiere cambiar la información de la dirección de correo electrónico, asegúrese de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada configurada. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
    Para enviar un correo electrónico al usuario con su información de conferencia de audio, ejecute lo siguiente:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
