---
title: Crear directivas personalizadas de acceso externo
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Skype empresarial online le permite crear directivas de acceso externo adicionales. A diferencia de las directivas de conferencia o del cliente, donde puede tener varias combinaciones, hay tres directivas de acceso externo predefinidas que pueden cubrir la mayoría de los escenarios.
ms.openlocfilehash: 978bad4e87e3e7dbe2a9bac5565aa7a6a45ca2df
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962508"
---
# <a name="create-custom-external-access-policies"></a>Crear directivas personalizadas de acceso externo

Skype empresarial online le permite crear directivas de acceso externo adicionales. A diferencia de las directivas de conferencia o del cliente, donde puede tener varias combinaciones, hay tres directivas de acceso externo predefinidas que pueden cubrir la mayoría de los escenarios. Estas son las siguientes:
  
- Sin acceso de usuarios federados o de Skype (_etiqueta: NoFederationAndPIC_ )
    
- Solo acceso federado (_etiqueta: FederationOnly_ )
    
- Acceso federado y de consumidor (_FederationAndPICDefault_)
    
Las directivas externas personalizadas le permiten crear directivas adicionales que no están cubiertas por la configuración anterior. Cuando se creó la Directiva, se le pedirá que configure todos los parámetros necesarios y no podrá modificarlos más adelante. La creación de nuevas directivas personalizadas le permite controlar características como el acceso a los consumidores de Skype o una directiva para deshabilitar el audio/vídeo de la nube pública, que es algo que no se ha cubierto con la configuración predefinida. Las directivas de acceso externo personalizadas siguen la misma sintaxis que las directivas de cliente, movilidad y Conferencia. Puede obtener más información sobre esa configuración [aquí](https://technet.microsoft.com/library/mt228132.aspx).
  
Para que esto funcione, el usuario debe usar una versión compatible de 2016 aplicación de Skype empresarial hacer clic y ejecutar que la admita. Se necesita la siguiente versión mínima de Skype empresarial 2016 cliente de hacer clic y ejecutar:
  
|**Tipo**|**Fecha de lanzamiento**|**Versión**|**Versión**|
|:-----|:-----|:-----|:-----|
|First Release para el canal actual  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Versión 1611 (compilación 7571,2006)  <br/> |
|Canal actual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versión 1611 (compilación 7571,2072)  <br/> |
|Canal diferido  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versión 1609 (compilación 7369,2118)  <br/> |
   
> [!CAUTION]
> Los usuarios que usen versiones anteriores de aplicaciones para Windows de Skype empresarial o clientes de Mac seguirán pudiendo transferir archivos. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar Windows PowerShell

- **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
    
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba  _Get-Host_ en la ventana **Windows PowerShell**.
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4,0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) para descargar y actualizar Windows PowerShell a la versión 4,0. Reinicie el equipo cuando se le solicite.
    
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
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Crear una directiva de acceso externo personalizada para un usuario

Para ello, ejecute:
  
> 
>   ```PowerShell
>   New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
>   ```
> 
> 
>   ```PowerShell
>   Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, como cuando se hacen los cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Temas relacionados
[Bloquear las transferencias de archivos punto a punto](block-point-to-point-file-transfers.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar directivas de conferencia en su organización](set-up-conferencing-policies-for-your-organization.md)

  
 
