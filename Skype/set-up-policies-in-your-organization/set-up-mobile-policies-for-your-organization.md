---
title: "Configurar directivas de dispositivos móviles para su organización"
ms.author: tonysmit
author: tonysmit
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
description: "Puede configurar cómo los usuarios conectarán a Skype empresarial Online mediante la Skype empresarial en dispositivos móviles como, por ejemplo, una característica que permite a los usuarios realizar y recibir llamadas de teléfono en su teléfono móvil mediante su número de teléfono del trabajo en lugar de su nu teléfono móvil Nú. Las directivas de movilidad también pueden utilizarse para requerir Wi-Fi conexiones al realizar o recibir llamadas."
---

# Configurar directivas de dispositivos móviles para su organización

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](beea47b2-7b9a-4b28-92d0-af65d80cd00f.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/beea47b2-7b9a-4b28-92d0-af65d80cd00f). 
  
Puede configurar cómo los usuarios conectarán a Skype empresarial Online mediante la Skype empresarial en dispositivos móviles como, por ejemplo, una característica que permite a los usuarios realizar y recibir llamadas de teléfono en su teléfono móvil mediante su número de teléfono del trabajo en lugar de su nu teléfono móvil Nú. Las directivas de movilidad también pueden utilizarse para requerir Wi-Fi conexiones al realizar o recibir llamadas.
  
Configuración de directivas de dispositivos móviles puede configurarse en el momento en que se crea una directiva, o puede usar el cmdlet **Set-CsMobilityPolicy** para modificar la configuración de una directiva existente.
  
## Establecer las directivas móviles

> [!NOTE]
> Para todas las configuraciones de directivas de dispositivos móviles en Skype Empresarial Online, debe usar Windows PowerShell y **no se puede usar** la **Skype centro de administración de la empresa**. 
  
### Verificar e iniciar Windows PowerShell

- **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
    
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
    Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Iniciar una sesión de Windows PowerShell**
    
1. En el **menú Inicio** > **Windows PowerShell**.
    
2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:
    
    > [!NOTE]
    > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

    Si desea obtener más información sobre cómo iniciar Windows PowerShell, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) o[Conectarse a Skype Empresarial Online con Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
    
### Requerir que un usuario disponga de conexión WiFi para usar el vídeo

- Para crear una nueva directiva de esta configuración, ejecute:
    
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```

    Más información sobre el cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx).
    
- Para conceder a la nueva directiva creado a todos los usuarios de su organización, ejecute:
    
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```

    Más información sobre el cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx).
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) para realizar cambios en la directiva existente y, a continuación, use el cmdlet de[Conceder CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) para aplicar la configuración a los usuarios.
  
### Impedir que un usuario use la aplicación Skype Empresarial

- Para crear una nueva directiva de esta configuración, ejecute:
    
> 
  ```
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```

    Más información sobre el cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx).
    
- Para conceder a la nueva directiva que creó Amos mármol, ejecute:
    
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```

    Más información sobre el cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx).
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) para realizar cambios en la directiva existente y, a continuación, use el cmdlet de[Conceder CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) para aplicar la configuración a los usuarios.
  
### Impedir que un usuario haga llamadas de voz sobre IP con un dispositivo móvil

- Para crear una nueva directiva de esta configuración, ejecute:
    
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```

    Más información sobre el cmdlet [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx).
    
- Para conceder a la nueva directiva creado a todos los usuarios de su organización, ejecute:
    
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

    Más información sobre el cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx).
    
Si ya ha creado una directiva, puede usar el cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) para realizar cambios en la directiva existente y, a continuación, use el cmdlet de[Conceder CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) para aplicar la configuración a los usuarios.
  
## ¿Quiere saber más sobre Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

