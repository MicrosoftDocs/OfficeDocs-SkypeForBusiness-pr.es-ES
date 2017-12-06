---
title: "Crear directivas de acceso externo personalizado"
ms.author: tonysmit
author: tonysmit
ms.date: 11/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
description: "Skype empresarial Online le permite crear directivas de acceso externo adicionales. A diferencia de las directivas de cliente o conferencias, donde puede tener varias combinaciones, hay tres directivas de acceso externo predefinidos que pueden cubrir la mayoría de los casos. Estos son:"
---

# Crear directivas de acceso externo personalizado

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](89cbd278-5480-473c-8cd9-04e07e5f9e0b.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/89cbd278-5480-473c-8cd9-04e07e5f9e0b). 
  
Skype empresarial Online le permite crear directivas de acceso externo adicionales. A diferencia de las directivas de cliente o conferencias, donde puede tener varias combinaciones, hay tres directivas de acceso externo predefinidos que pueden cubrir la mayoría de los casos. Estos son:
  
- No federado o acceso de los consumidores de Skype ( _Tag:NoFederationAndPIC_ )
    
- Sólo acceso federado ( _Tag:FederationOnly_ )
    
- Federado y consumidores acceder ( _FederationAndPICDefault_)
    
Directivas externas personalizadas le permiten crear adicionales directivas que no están cubiertos por la configuración anterior. Cuando se creó la directiva, sería necesario para establecer todos los parámetros requeridos y no se puede modificar más adelante. Creación de nuevas directivas personalizadas le permiten a las características de control, como el acceso de consumidores de Skype o una directiva para deshabilitar pública de nube audio y vídeo, que es algo que no se ha cubierto con valores predefinidos. Las directivas de acceso externo personalizado siguen la misma sintaxis que las directivas de cliente, movilidad y conferencias. Puede encontrar más información sobre esos valores [aquí](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Para que esto funcione, el usuario debe estar usando una versión compatible de 2016 hacer clic y ejecutar de Skype empresarial que lo admita. Se requiere la siguiente versión mínima de Skype cliente empresas 2016 clic y ejecutar:
  
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
    
## Crear una directiva de acceso externo personalizado para un usuario

Para ello, ejecute:
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True 
-EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
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
  

