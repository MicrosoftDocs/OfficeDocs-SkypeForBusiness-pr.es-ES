---
title: Mover directorios de conferencia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Antes de retirar un grupo de servidores, debe realizar el siguiente procedimiento para cada directorio de conferencia del grupo de servidores heredado.
ms.openlocfilehash: 8a25b955ae769a712750ff08325b3fa29538be8a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752502"
---
# <a name="move-conference-directories"></a>Mover directorios de conferencia

Antes de retirar un grupo de servidores, debe realizar el siguiente procedimiento para cada directorio de conferencia del grupo de servidores heredado.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Para mover un directorio de conferencia a Skype empresarial Server 2019

1. Abra el shell de administración de Skype empresarial Server.
    
2. Para obtener la identidad de los directorios de conferencia de su organización, ejecute el siguiente comando:
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    El comando anterior devuelve todos los directorios de conferencia de la organización. Por ello, es posible que desee limitar los resultados al grupo de servidores que se está retirando. Por ejemplo, si va a retirar el grupo de servidores con el nombre de dominio completo (FQDN) pool01.contoso.net, use este comando para limitar los datos devueltos a los directorios de conferencia de ese grupo:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Este comando devuelve sólo los directorios de conferencia en los que la propiedad ServiceID contiene el FQDN pool01.contoso.net.
    
3. Para mover los directorios de conferencia, ejecute el siguiente comando para cada directorio de conferencia del Grupo:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Por ejemplo, para mover el directorio de conferencia 3, use este comando, especificando un grupo de servidores de Skype empresarial Server 2019 como TargetPool:
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Si desea mover todos los directorios de conferencia en un grupo de servidores, use un comando similar al siguiente:
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Descargue la desinstalación de la versión [heredada de Microsoft y la eliminación de roles de servidor](https://go.microsoft.com/fwlink/p/?linkId=246227) para obtener instrucciones detalladas paso a paso sobre la retirada de grupos de servidores heredados.
  
Al mover los directorios de conferencia, es posible que se produzca el siguiente error:
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Este error suele producirse cuando el shell de administración de Skype empresarial Server requiere un conjunto actualizado de permisos de Active Directory para poder completar una tarea. Para solucionar el problema, cierre la instancia actual del shell de administración, abra una nueva instancia del shell y vuelva a ejecutar el comando para mover el directorio de conferencia.
  

