---
title: Establecer directivas móviles en su organización
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: Puede configurar la forma en que los usuarios se conectan a Skype empresarial online con la aplicación de Skype empresarial en dispositivos móviles, como una característica que permite a los usuarios realizar y recibir llamadas telefónicas en su teléfono móvil usando su número de teléfono del trabajo en lugar de su teléfono móvil nu mber. Las directivas de movilidad también se pueden usar para requerir conexiones Wi-Fi al realizar o recibir llamadas.
ms.openlocfilehash: 2d608356e08ae989d0be79bd61f14a4d6ba3b9f0
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887859"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Establecer directivas móviles en su organización

Puede configurar la forma en que los usuarios se conectan a Skype empresarial online con la aplicación de Skype empresarial en dispositivos móviles, como una característica que permite a los usuarios realizar y recibir llamadas telefónicas en su teléfono móvil usando su número de teléfono del trabajo en lugar de su teléfono móvil nu mber. Las directivas de movilidad también se pueden usar para requerir conexiones Wi-Fi al realizar o recibir llamadas.
  
La configuración de la Directiva móvil se puede configurar en el momento en que se crea una directiva o puede usar el cmdlet **set-CsMobilityPolicy** para modificar la configuración de una directiva existente.
  
## <a name="set-your-mobile-policies"></a>Establecer las directivas móviles

> [!NOTE]
> Para todas las configuraciones de directiva móvil de Skype empresarial online, debe usar Windows PowerShell y **no puede usar** el centro de **Administración de Skype empresarial**. 
  
### <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar Windows PowerShell

- **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
    
    1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
        
    2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
        
    3. Si no tiene la versión 3,0 o superior, debe descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0. Reinicie el equipo cuando se le pida.
        
    4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
    Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Iniciar una sesión de Windows PowerShell**
    
    1. En el **menú Inicio** > **Windows PowerShell**.
        
    2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:
        
        > [!NOTE]
        > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea [conectarse a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o [configurar su equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Requerir que un usuario disponga de conexión WiFi para usar el vídeo

- Para crear una nueva Directiva para esta configuración, ejecute:
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   Para obtener más información, consulte el cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Para conceder la nueva directiva que ha creado a todos los usuarios de su organización, ejecute:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   Para obtener más información, consulta el cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
  Si ya ha creado una directiva, puede usar el cmdlet [set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar la configuración a los usuarios.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Impedir que un usuario use la aplicación Skype Empresarial

- Para crear una nueva Directiva para esta configuración, ejecute:
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  Para obtener más información, consulte el cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Para conceder a la nueva directiva que ha creado a amos Marble, ejecute:  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   Para obtener más información, consulta el cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
  Si ya ha creado una directiva, puede usar el cmdlet [set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar la configuración a los usuarios.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Impedir que un usuario haga llamadas de voz sobre IP con un dispositivo móvil

- Para crear una nueva Directiva para esta configuración, ejecute:
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   Para obtener más información, consulte el cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Para conceder la nueva directiva que ha creado a todos los usuarios de su organización, ejecute:
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  Para obtener más información, consulta el cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
Si ya ha creado una directiva, puede usar el cmdlet [set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) para realizar cambios en la directiva existente y, después, usar el cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) para aplicar la configuración a los usuarios.
  
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

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar directivas de conferencia en su organización](set-up-conferencing-policies-for-your-organization.md)

  
 
