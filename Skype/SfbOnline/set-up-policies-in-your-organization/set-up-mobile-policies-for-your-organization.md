---
title: Configurar directivas de dispositivos móviles para su organización
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Puede configurar cómo los usuarios se conectan a Skype para los negocios en línea usando el Skype para la aplicación de negocio en dispositivos móviles, por ejemplo, una característica que permite a los usuarios realizar y recibir llamadas en su teléfono móvil mediante su número de teléfono de trabajo en lugar de su teléfono móvil de nu Nú. Las directivas de movilidad también se pueden usar para requerir conexiones WiFi para hacer o recibir llamadas.
ms.openlocfilehash: cbd981285f6c4dfacf09597b2bd8e687ba124ad8
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Configurar directivas de dispositivos móviles para su organización

Puede configurar cómo los usuarios se conectan a Skype para los negocios en línea usando el Skype para la aplicación de negocio en dispositivos móviles, por ejemplo, una característica que permite a los usuarios realizar y recibir llamadas en su teléfono móvil mediante su número de teléfono de trabajo en lugar de su teléfono móvil de nu Nú. Las directivas de movilidad también se pueden usar para requerir conexiones WiFi para hacer o recibir llamadas.
  
Configuración de directivas de dispositivos móviles puede configurarse en el momento en que se crea una directiva o puede utilizar el cmdlet **Set-CsMobilityPolicy** para modificar la configuración de una directiva existente.
  
## <a name="set-your-mobile-policies"></a>Establecer las directivas móviles

> [!NOTE]
> Para todas las configuraciones de directivas de dispositivos móviles en Skype para los negocios en línea, debe utilizar Windows PowerShell y **no se puede utilizar** el **Skype para el centro de administración de negocios**. 
  
### <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar Windows PowerShell

- **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
    
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
    Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Iniciar una sesión de Windows PowerShell**
    
1. En el **menú Inicio** > **Windows PowerShell**.
    
2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:
    
    > [!NOTE]
    > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar con todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [conectarse a Skype para los negocios en línea mediante el uso de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Requerir que un usuario disponga de conexión WiFi para usar el vídeo

- Para crear una nueva directiva para estas configuraciones, ejecute:
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```
  Obtenga más información sobre el cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .
    
- Para conceder a la nueva directiva creada para todos los usuarios de la organización, ejecute:
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```
  Obtenga más información acerca del cmdlet [Grant CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .
    
  Si ya ha creado una directiva, puede utilizar el cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) para realizar cambios a la directiva existente y, a continuación, use el cmdlet de[Concesión CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) para aplicar la configuración a los usuarios.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Impedir que un usuario use la aplicación Skype Empresarial

- Para crear una nueva directiva para estas configuraciones, ejecute:
```
New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
```
  Obtenga más información sobre el cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .
    
- Para conceder a la nueva directiva que ha creado al Mármol Amos, ejecute:  
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```
  Obtenga más información acerca del cmdlet [Grant CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .
    
  Si ya ha creado una directiva, puede utilizar el cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) para realizar cambios a la directiva existente y, a continuación, use el cmdlet de [Concesión CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) para aplicar la configuración a los usuarios.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Impedir que un usuario haga llamadas de voz sobre IP con un dispositivo móvil

- Para crear una nueva directiva para estas configuraciones, ejecute:
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```
  Obtenga más información sobre el cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .
    
- Para conceder a la nueva directiva creada para todos los usuarios de la organización, ejecute:
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

  Obtenga más información acerca del cmdlet [Grant CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .
    
Si ya ha creado una directiva, puede utilizar el cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) para realizar cambios a la directiva existente y, a continuación, use el cmdlet de[Concesión CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) para aplicar la configuración a los usuarios.
  
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Transferencias de archivos punto a punto de bloque](block-point-to-point-file-transfers.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar directivas de la conferencia de la organización](set-up-conferencing-policies-for-your-organization.md)

  
 