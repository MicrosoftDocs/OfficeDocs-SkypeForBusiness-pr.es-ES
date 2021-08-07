---
title: Bloquear las transferencias de archivos punto a punto
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: En Skype Empresarial Online, puede controlar las transferencias de archivos punto a punto (P2P) como parte de la configuración de directiva de conferencia existente. Sin embargo, esto permite o bloquea las transferencias de archivos para los usuarios, independientemente de si están transfiriendo o no archivos a un usuario de la misma organización o a un usuario federado de otra organización. Siguiendo los pasos siguientes, puede bloquear las transferencias de archivos P2P con organizaciones o partners federados.
ms.openlocfilehash: f09f67793303d393b24cb40077fd3dd3b16d38f278460a2f4d747ef67b97aa96
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306203"
---
# <a name="block-point-to-point-file-transfers"></a>Bloquear las transferencias de archivos punto a punto

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

En Skype Empresarial Online, puede controlar las transferencias de archivos punto a punto (P2P) como parte de la configuración de directiva de conferencia existente. Sin embargo, esto permite o bloquea las transferencias de archivos para los usuarios, independientemente de si están transfiriendo o no archivos a un usuario de la misma organización o a un usuario federado de otra organización. Siguiendo los pasos siguientes, puede bloquear las transferencias de archivos P2P con organizaciones o partners federados.
  
 Un escenario muy común es cuando desea permitir que los usuarios internos usen la transferencia de archivos P2P, pero bloqueen la transferencia de archivos con partners federados. Para este escenario, tendría que hacer lo siguiente:
  
- Asigne una directiva de conferencia con la transferencia de archivos P2P habilitada _(EnableP2PFileTransfer_ establecido en _True)_ a los usuarios de su organización.
    
- Cree un conjunto global de directivas de comunicación de usuarios externos para bloquear las transferencias de archivos P2P externos _(EnableP2PFileTransfer_ establecido en _False)_ y asígnelo a un usuario de su organización. 
    
Puede obtener más información sobre esa configuración [aquí.](/previous-versions//mt228132(v=technet.10))
  
Si un usuario federado fuera de su organización intenta enviar un archivo a un usuario donde se ha aplicado la directiva, recibirá un **error** Error de transferencia. Y si un usuario intenta enviar un archivo, recibirá un error de transferencia de **archivos** desactivado.
  
Para que esto funcione, el usuario debe usar una versión compatible de una aplicación de hacer clic y ejecutar de 2016 Skype Empresarial que la admita. Se requiere la siguiente versión mínima Skype Empresarial cliente hacer clic y ejecutar de 2016:
  
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
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Deshabilitar las transferencias de archivos P2P para su organización

De forma predeterminada, _EnableP2PFileTransfer_ está habilitado en la directiva global de la organización. Cuando se creó, a los usuarios se les asignó la _directiva BposSAllModality._
  
Para permitir las transferencias P2P dentro de su organización pero bloquear las transferencias de archivos externos a otra organización, solo tiene que cambiarla a nivel global. Para ello, ejecute:
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Deshabilitar las transferencias de archivos P2P para un usuario

Puede aplicar esto a un usuario creando una nueva directiva y concedéndola a ese usuario. Para ello, ejecute: 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario, cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [¿Por qué necesita usar Microsoft 365 o Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tiene muchas ventajas en la velocidad, la simplicidad y la productividad en lugar de usar solo el Centro de administración de Microsoft 365 como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Temas relacionados
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar directivas de conferencia en su organización](set-up-conferencing-policies-for-your-organization.md)

  
