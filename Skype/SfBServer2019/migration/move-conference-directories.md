---
title: Mover directorios de conferencia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de dar de baja un grupo, debe realizar el siguiente procedimiento para cada directorio de conferencia de su grupo heredado.
ms.openlocfilehash: c3bee8160e7387102f6d45fc39fa821d2f0df161
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298144"
---
# <a name="move-conference-directories"></a>Mover directorios de conferencia

Antes de dar de baja un grupo, debe realizar el siguiente procedimiento para cada directorio de conferencia de su grupo heredado.
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Para mover un directorio de conferencia a Skype empresarial Server 2019

1. Abra el shell de administración de Skype empresarial Server.
    
2. Para obtener la identidad de los directorios de conferencia de su organización, ejecute el siguiente comando:
    
   ```
   Get-CsConferenceDirectory
   ```

    El comando anterior devuelve todos los directorios de conferencia de su organización. Por eso, es posible que desee limitar los resultados al grupo que se va a retirar. Por ejemplo, si va a retirar el grupo con el nombre de dominio completo (FQDN) pool01.contoso.net, use este comando para limitar los datos devueltos a los directorios de conferencia de ese grupo:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    Ese comando devuelve solo los directorios de la Conferencia en los que la propiedad ServiceID contiene el FQDN pool01.contoso.net.
    
3. Para mover los directorios de la Conferencia, ejecute el comando siguiente para cada directorio de conferencia del Grupo:
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    Por ejemplo, para mover el directorio de conferencia 3, use este comando, especificando un grupo de servidores de Skype empresarial 2019 como TargetPool:
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    Si quiere mover todos los directorios de conferencia de un grupo, use un comando similar al siguiente:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

Descargue [desinstalando Microsoft Legacy y quitando roles de servidor](https://go.microsoft.com/fwlink/p/?linkId=246227) para obtener instrucciones detalladas paso a paso sobre la retirada de grupos heredados.
  
Al mover los directorios de la Conferencia, es posible que se produzca el siguiente error:
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

Este error suele ocurrir cuando el shell de administración de Skype empresarial Server requiere un conjunto actualizado de permisos de Active Directory para poder completar una tarea. Para resolver el problema, cierre la instancia actual del shell de administración, abra una nueva instancia de la Shell y vuelva a ejecutar el comando para mover el directorio de la Conferencia.
  

