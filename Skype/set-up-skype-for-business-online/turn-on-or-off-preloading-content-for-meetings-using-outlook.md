---
title: "Activar o desactivar la precarga de contenido con Outlook en las reuniones"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
description: "See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. "
---

# Activar o desactivar la precarga de contenido con Outlook en las reuniones

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Los usuarios pueden cargar contenido, archivos o datos adjuntos que se han adjuntado a una invitación de reunión de Outlook a un Skype empresarial Online reunión, pero se puede activar o desactivar. Está activada de forma predeterminada para todas las organizaciones que usan Skype empresarial Online. Vea cómo [Precargar datos adjuntos para una reunión de Skype Empresarial.](http://technet.microsoft.com/library/fd3d9f9d-b448-4754-b813-02e49393f251%28Office.14%29.aspx).
  
> [!NOTE]
> En este momento no hay ningún cmdlets disponibles en Skype empresarial Online para configuración o ver los valores en línea para  _MaxContentStorageMB_ y _MaxUploadFileMB_. Solo están disponibles para las implementaciones locales. Es importante saber que el contenido no se cargarán en una reunión si el contenido adjunto supera el  _MaxUploadFileSizeMB_ o si se ha alcanzado el límite de _MaxContentStorageMB_.
  
## Para empezar

### 

 **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
  
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
### 

 **Iniciar una sesión de Windows PowerShell**
  
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
  
## Activación o desactivación

Posibilidad de cargar contenido adjuntado a una invitación de reunión de Outlook para Skype para reuniones en línea de negocio está activada de forma predeterminada, pero necesita impedir que los usuarios de su organización desde precargar contenido en sus reuniones.
  
> [!IMPORTANT]
> Esta configuración se puede sólo activar o desactivar para toda la organización; no puede activar o desactivar para un solo usuario. 
  
 **Para desactivarla, abra Windows PowerShell y haga lo siguiente:**
  
```
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **Si desea volver a activarla, abra Windows PowerShell y haga lo siguiente:**
  
```
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

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
  

