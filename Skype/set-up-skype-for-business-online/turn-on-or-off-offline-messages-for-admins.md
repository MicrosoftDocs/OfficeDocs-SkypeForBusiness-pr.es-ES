---
title: "Activar o desactivar los mensajes sin conexión para administradores"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
description: "Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell."
---

# Activar o desactivar los mensajes sin conexión para administradores

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](8967a77f-caa2-4680-aa22-8faa32c716e4.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/8967a77f-caa2-4680-aa22-8faa32c716e4). 
  
Puede enviar Skype para mensajes instantáneos de empresa a los contactos aunque no haya iniciado sesión. Esta característica permite a los contactos saber intentando acceder a ellas. No tiene que esperar hasta que alguien está en línea antes de enviarles un mensaje.
  
Información importante sobre los mensajes sin conexión:
  
- Los mensajes sin conexión no se archivan en el buzón del usuario.
    
- Se enviarán mensajes sin conexión para el buzón del usuario y se notificará al usuario cuando inicie sesión en Skype empresarial.
    
- Si el estado del destinatario del mensaje se establece en **No molestar** o **presentando**, recibirán un mensaje perdido que se envía desde Skype del destinatario empresarial Client.
    
Para obtener más información, vea [Utilizar mensajería sin conexión en Skype Empresarial](http://technet.microsoft.com/library/ffdc6a43-71a1-40ee-bfcc-640d21324a3d%28Office.14%29.aspx).
  
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
  
## Activar o desactivar la mensajería instantánea sin conexión

> [!NOTE]
> Mensajes sin conexión **solo** disponible en la versión más reciente de la Skype hacer clic y ejecutar el cliente de empresa y no están disponibles cuando se usa un anterior Skype haga clic en ejecutar para la empresa o un archivo *.msi se utilizó para instalar el Skype empresarial Client.
  
Para habilitar o deshabilitar el envío de mensajes sin conexión mensajes sin conexión para los usuarios de su organización, establezca  _EnableIMAutoArchiving_ en `True` o `False`. De forma predeterminada, esta se establece en  `True`.
  
Para desactivarlo, use el cmdlet **Set-CsClientPolicy** y ejecute:
  
```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Para habilitar o deshabilitar el envío de mensajes sin conexión mensajes sin conexión para un usuario, establezca  _EnableIMAutoArchiving_ en `True` o `False`. De forma predeterminada, esta se establece en  `True`. Puede utilizar una directiva existente o crear en el ejemplo siguiente.
  
> 
  ```
  New-CsClientPolicy -Identity OfflineIM
  ```

> 
  ```
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  ```

> 
  ```
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
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
  

