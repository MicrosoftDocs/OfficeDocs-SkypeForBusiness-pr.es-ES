---
title: Establecer directivas de cliente en su organización
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Las directivas de cliente ayudan a determinar las funciones de Skype Empresarial Online que estarán disponibles para los usuarios. Por ejemplo, puede dar a algunos usuarios permiso para transferir archivos, pero no a otros.
ms.openlocfilehash: 43b51b800b3107410c64bd2605b5a6a7622fe65a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776295"
---
# <a name="set-up-client-policies-for-your-organization"></a>Establecer directivas de cliente en su organización

[] Las directivas de cliente ayudan a determinar las funciones de Skype Empresarial Online que estarán disponibles para los usuarios. Por ejemplo, puede dar a algunos usuarios permiso para transferir archivos, pero no a otros.
  
La configuración de la Directiva de cliente se puede configurar en el momento en que se crea una directiva o puede usar el cmdlet **set-ClientPolicy** para modificar la configuración de una directiva existente.
  
## <a name="set-your-client-policies"></a>Establecer las directivas de cliente

> [!NOTE]
> Para todas las configuraciones de directiva de cliente de Skype empresarial online, debe usar Windows PowerShell y no puede **usar** el **centro de administración de Skype empresarial**. 
  
### <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar Windows PowerShell

- **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
    
    1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
        
    2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
        
    3. Si no tiene la versión 3,0 o superior, debe descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0. Reinicie el equipo cuando se le pida.
        
    4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
    Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Iniciar una sesión de Windows PowerShell**
    
    1. En el **menú Inicio** > **Windows PowerShell**.
        
    2. En la ventana de **Windows PowerShell** , conéctese a Microsoft 365 u Office 365 ejecutando:
    
        > [!NOTE]
        > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.

       ```powershell
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```
Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea [conectarse a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurar su equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Deshabilitar emoticonos y notificaciones de presencia y evitar el guardado de mensajes instantáneos

- Para crear una nueva Directiva para esta configuración, ejecute:
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  Para obtener más información, consulte el cmdlet [New-ClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .
    
- Para conceder la nueva directiva que ha creado a todos los usuarios de su organización, ejecute:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  Para obtener más información, consulta el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .
    
Si ya ha creado una directiva, puede usar el cmdlet [set-ClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar la configuración a los usuarios.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Permitir que se pueda hacer clic en las URL y los hiperenlaces en MI

- Para crear una nueva Directiva para esta configuración, ejecute:
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  Para obtener más información, consulte el cmdlet [New-ClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .
    
- Para conceder la nueva directiva que ha creado a todos los usuarios de su organización, ejecute:
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  Para obtener más información, consulta el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .
    
Si ya ha creado una directiva, puede usar el cmdlet [set-ClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar la configuración a los usuarios.
  
### <a name="prevent-showing-recent-contacts"></a>Impedir que se muestren los contactos recientes

- Para crear una nueva Directiva para esta configuración, ejecute:
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  Para obtener más información, consulte el cmdlet [New-ClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .
    
- Para conceder a la nueva directiva que ha creado a amos Marble, ejecute:
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  Para obtener más información, consulta el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .
    
  Si ya ha creado una directiva, puede usar el cmdlet [set-ClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-ClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) para aplicar la configuración a los usuarios.
  
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que es posible que desee usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Temas relacionados
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Bloquear las transferencias de archivos punto a punto](block-point-to-point-file-transfers.md)

[Configurar directivas de conferencia en su organización](set-up-conferencing-policies-for-your-organization.md)

  
 
