---
title: Crear directivas personalizadas de acceso externo
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: "Skype para los negocios en línea le permite crear directivas de acceso externo adicional. A diferencia de las directivas de cliente o conferencias, donde es posible tener varias combinaciones, hay tres directivas predefinidas de acceso externo que pueden cubrir la mayoría de los escenarios."
ms.openlocfilehash: 7a5e347f3f9629f603544ad9ab06e11d4b649868
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="create-custom-external-access-policies"></a>Crear directivas personalizadas de acceso externo

Skype para los negocios en línea le permite crear directivas de acceso externo adicional. A diferencia de las directivas de cliente o conferencias, donde es posible tener varias combinaciones, hay tres directivas predefinidas de acceso externo que pueden cubrir la mayoría de los escenarios. Estos son:
  
- No federado o consumidor de Skype Access (_Etiqueta: NoFederationAndPIC_ )
    
- Sólo acceso federado (_Etiqueta: FederationOnly_ )
    
- Federados y consumidor accede (_FederationAndPICDefault_)
    
Directivas externas personalizadas le permiten crear más políticas que no estén cubiertos por los valores anteriores. Cuando se creó la directiva, se necesitaría para establecer todos los parámetros necesarios y se no se puede modificar más adelante. Creación de nuevas directivas personalizadas permiten a las características de control como el acceso de los consumidores Skype o una directiva para deshabilitar pública de nube audio o vídeo, lo cual es algo que no estaba cubierto con una configuración predefinida. Las directivas de acceso externo personalizado siguen la misma sintaxis que las directivas de cliente, movilidad y conferencias. Puede encontrar más información acerca de las opciones [aquí](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Para que esto funcione, el usuario debe utilizar una versión compatible de 2016 Skype hacer clic para ejecutar para el negocio de la aplicación que lo admite. Se requiere la siguiente versión mínima de Skype para cliente de negocios 2016 clic y ejecutar:
  
|**Tipo**|**Fecha de lanzamiento**|**Versión**|**Versión**|
|:-----|:-----|:-----|:-----|
|Primera versión para el canal actual  <br/> |17/11/2016  <br/> |16.0.7571.2006  <br/> |Versión 1611 (compilación 7571.2006)  <br/> |
|Canal actual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versión 1611 (compilación 7571.2072)  <br/> |
|Canal diferido  <br/> |22/2/2017  <br/> |16.0.7369.2118  <br/> |Versión 1609 (compilación 7369.2118)  <br/> |
   
> [!CAUTION]
> Usuarios que utilizan versiones anteriores de Skype para clientes de Mac o Windows Business apps podrán transferir archivos. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar Windows PowerShell

- **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
    
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
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
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Crear una directiva personalizada de acceso externo para un usuario

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

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[Transferencias de archivos punto a punto de bloque](block-point-to-point-file-transfers.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar directivas de la conferencia de la organización](set-up-conferencing-policies-for-your-organization.md)
