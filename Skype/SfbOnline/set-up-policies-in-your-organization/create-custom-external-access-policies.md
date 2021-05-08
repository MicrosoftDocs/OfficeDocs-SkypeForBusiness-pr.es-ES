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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Skype Empresarial Online le permite crear directivas de acceso externo adicionales. A diferencia de las directivas de cliente o conferencia, donde puede tener varias combinaciones, hay tres directivas de acceso externo predefinidas que pueden abarcar la mayoría de los escenarios.
ms.openlocfilehash: f9d99789bdb400cee9b7597bfcdc4079c1d3612d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240149"
---
# <a name="create-custom-external-access-policies"></a>Crear directivas personalizadas de acceso externo

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Skype Empresarial Online le permite crear directivas de acceso externo adicionales. A diferencia de las directivas de cliente o conferencia, donde puede tener varias combinaciones, hay tres directivas de acceso externo predefinidas que pueden abarcar la mayoría de los escenarios. Estos son:
  
- Sin acceso al consumidor Skype federado o Skype (_Tag:NoFederationAndPIC_ )
    
- Solo acceso federado (_tag:FederationOnly_ )
    
- Acceso federado y de consumidor (_FederationAndPICDefault_)
    
Las directivas externas personalizadas le permiten crear policías adicionales que no están cubiertas por la configuración anterior. Cuando se creó la directiva, se le obligaría a establecer todos los parámetros necesarios y no pudo modificarlos más adelante. La creación de nuevas directivas personalizadas le permite controlar características como el acceso de consumidor Skype o una directiva para deshabilitar el audio/vídeo en la nube pública, que es algo que no se ha cubierto con la configuración predefinida. Las directivas de acceso externo personalizadas siguen la misma sintaxis que las directivas de cliente, movilidad y conferencia. Puede obtener más información sobre esa configuración [aquí.](/previous-versions//mt228132(v=technet.10))
  
Para que esto funcione, el usuario debe usar una versión compatible de la aplicación Hacer clic y ejecutar de 2016 Skype Empresarial que la admita. Se requiere la siguiente versión mínima Skype Empresarial cliente hacer clic y ejecutar de 2016:
  
|**Tipo**|**Fecha de lanzamiento**|**Versión**|**Versión**|
|:-----|:-----|:-----|:-----|
|First Release para el Canal actual  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Versión 1611 (compilación 7571.2006)  <br/> |
|Canal actual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versión 1611 (compilación 7571.2072)  <br/> |
|Canal diferido  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versión 1609 (compilación 7369.2118)  <br/> |
   
> [!CAUTION]
> Los usuarios que usan versiones anteriores de Skype Empresarial Windows aplicaciones o clientes Mac seguirán siendo capaces de transferir archivos. 
  
## <a name="start-windows-powershell"></a>Iniciar Windows PowerShell

> [!NOTE]
> El conector en línea del cliente de Skype® Empresarial actualmente forma parte del módulo más reciente de Windows PowerShell de Teams. Si usa la versión pública más reciente de Teams PowerShell, no es necesario que instale el conector en línea de cliente de Skype® Empresarial.
1. Instale el [Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Abra un Windows PowerShell de comandos y ejecute los siguientes comandos: 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea Conectar todos los servicios de Microsoft 365 o Office 365 en una única ventana de [Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) o Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Crear una directiva de acceso externo personalizada para un usuario

Para ello, ejecute:
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [¿Por qué necesita usar Microsoft 365 o Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Temas relacionados
[Bloquear las transferencias de archivos punto a punto](block-point-to-point-file-transfers.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar directivas de conferencia en su organización](set-up-conferencing-policies-for-your-organization.md)

  
