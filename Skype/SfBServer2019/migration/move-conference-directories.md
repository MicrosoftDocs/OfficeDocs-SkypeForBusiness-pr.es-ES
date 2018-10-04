---
title: Mover directorios de conferencia
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de retirar un grupo de servidores debe realizar el procedimiento siguiente para cada directorio de conferencia en su grupo heredado.
ms.openlocfilehash: b7526d8c3c032bf8b1f9052dce7da7e8a87b66b5
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372808"
---
# <a name="move-conference-directories"></a>Mover directorios de conferencia

Antes de retirar un grupo de servidores, debe realizar el procedimiento siguiente para cada directorio de conferencia en su grupo heredado.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Para mover un directorio de conferencia a Skype para Business Server 2019

1. Abra el Skype para Shell de administración de servidor empresarial.
    
2. Para obtener la identidad de los directorios de conferencia de la organización, ejecute el siguiente comando:
    
   ```
   Get-CsConferenceDirectory
   ```

    El comando anterior devuelve todos los directorios de conferencia en su organización. Por ese motivo, es posible que desee limitar los resultados al grupo de servidores fuera de servicio. Por ejemplo, si quita el grupo de servidores con el pool01.contoso.net de dominio completo (FQDN) del nombre, use este comando para limitar los datos devueltos a directorios de conferencia desde ese grupo de servidores:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Ese comando devuelve sólo los directorios de conferencia donde la propiedad ServiceID contiene el FQDN pool01.contoso.net.
    
3. Para mover directorios de conferencia, ejecute el siguiente comando para cada directorio de conferencia en el grupo de servidores:
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Por ejemplo, para mover el directorio de conferencia 3, use este comando, especificando un Skype para el grupo de servidores de Business Server 2019 como el TargetPool:
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Si desea mover todos los directorios de conferencia en un grupo de servidores, use un comando similar al siguiente:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Descargar [Microsoft desinstalar heredado y quitar Roles de servidor](https://go.microsoft.com/fwlink/p/?linkId=246227) para instrucciones paso a paso integrales en retirar grupos heredados.
  
Al mover directorios de conferencia, podría encontrarse con el siguiente error:
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Normalmente, este error se produce cuando el Skype para Shell de administración de Business Server requiere un conjunto actualizado de permisos de Active Directory con el fin de completar una tarea. Para resolver el problema, cierre la instancia actual de la consola de administración, a continuación, abra una nueva instancia de la consola y vuelva a ejecutar el comando para mover el directorio de conferencia.
  

