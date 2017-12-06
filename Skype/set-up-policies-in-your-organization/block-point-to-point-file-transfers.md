---
title: "Transferencia de archivos punto a punto de bloque"
ms.author: tonysmit
author: tonysmit
ms.date: 11/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
description: "En Skype empresarial Online, tiene la capacidad de controlar a las transferencias de archivos punto a punto (P2P) como parte de la configuración de la directiva de conferencia existente. Sin embargo, esto permite o bloquea las transferencias para usuarios o no son transferir archivos a un usuario que está en la misma organización o a un usuario federado de otra organización de archivos. Siguiendo los pasos a continuación, puede bloquear la transferencia de archivos P2P con organizaciones federadas o asociados."
---

# Transferencia de archivos punto a punto de bloque

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](9adf9859-de5b-461e-92ea-b6ce4dd2f7c1.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/9adf9859-de5b-461e-92ea-b6ce4dd2f7c1). 
  
En Skype empresarial Online, tiene la capacidad de controlar a las transferencias de archivos punto a punto (P2P) como parte de la configuración de la directiva de conferencia existente. Sin embargo, esto permite o bloquea las transferencias para usuarios o no son transferir archivos a un usuario que está en la misma organización o a un usuario federado de otra organización de archivos. Siguiendo los pasos a continuación, puede bloquear la transferencia de archivos P2P con organizaciones federadas o asociados.
  
Un escenario muy común es cuando desea permitir a los usuarios internos de transferencia de archivos de uso P2P pero bloque de transferencia de archivos con los socios federados. En este escenario, ¿debe hacer:
  
- Asignar una directiva de conferencia con ha habilitado la transferencia de archivos P2P ( _EnableP2PFileTransfer_ establecido en _True_) a los usuarios de su organización.
    
- Cree una directiva de comunicación de usuario externo aglobal establecer para bloquear la transferencia de archivos P2P externo (valor _EnableP2PFileTransfer_ _False_) y asignarlo a un usuario de su organización.
    
Puede encontrar más información sobre esos valores [aquí](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Si un usuario federado fuera de su organización intenta enviar un archivo a un usuario que se ha aplicado la directiva, recibirá un error de **Error de transferencia**. Y si un usuario intenta enviar un archivo, recibirá un error de **transferencia de archivos está desactivado**.
  
Para que esto funcione, el usuario debe estar usando una versión compatible de un Skype de hacer clic y ejecutar de 2016 empresarial que lo admita. Se requiere la siguiente versión mínima de Skype cliente empresas 2016 clic y ejecutar:
  
|**Tipo**|**Fecha de lanzamiento**|**Versión**|**Compilación**|
|:-----|:-----|:-----|:-----|
|First Release para Canal actual  <br/> |17/11/2016  <br/> |16.0.7571.2006  <br/> |Versión 1611 (compilación 7571.2006)  <br/> |
|Canal actual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> | Versión 1611 (compilación 7571.2072) <br/> |
|Canal diferido  <br/> |22/2/2017  <br/> |16.0.7369.2118  <br/> |Versión 1609 (compilación 7369.2118)  <br/> |
   
> [!CAUTION]
> Los usuarios que usan versiones anteriores de Skype para aplicaciones de Windows de la empresa o sus clientes de Mac aún podrán transferir archivos. 
  
## Verificar e iniciar Windows PowerShell

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
    
## Deshabilitar la transferencia de archivos P2P para su organización

De forma predeterminada,  _EnableP2PFileTransfer_ está habilitada en la directiva global de la organización. Cuando se creó, los usuarios se asignan la directiva de _BposSAllModality_.
  
> Para permitir a las transferencias de P2P para dentro de su organización pero bloquear las transferencias de archivo externo a otra organización, solo necesita cambiar a un nivel global. Para ello, ejecute:
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## Deshabilitar la transferencia de archivos P2P para un usuario

- Puede aplicar a un usuario mediante la creación de una nueva directiva y conceder a ese usuario. Para ello, ejecute:
    
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```

> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
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
  

