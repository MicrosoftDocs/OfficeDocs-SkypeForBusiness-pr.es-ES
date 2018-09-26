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
ms.openlocfilehash: 18cbada5833a5160fc1eb81560c56bc9fcff3e2a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028015"
---
# <a name="move-conference-directories"></a><span data-ttu-id="7019d-103">Mover directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="7019d-103">Move Conference Directories</span></span>

<span data-ttu-id="7019d-104">Antes de retirar un grupo de servidores, debe realizar el procedimiento siguiente para cada directorio de conferencia en su grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="7019d-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="7019d-105">Para mover un directorio de conferencia a Skype para Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="7019d-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="7019d-106">Abra el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="7019d-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="7019d-107">Para obtener la identidad de los directorios de conferencia de la organización, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7019d-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
  ```
  Get-CsConferenceDirectory
  ```

    <span data-ttu-id="7019d-108">El comando anterior devuelve todos los directorios de conferencia en su organización.</span><span class="sxs-lookup"><span data-stu-id="7019d-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="7019d-109">Por ese motivo, es posible que desee limitar los resultados al grupo de servidores fuera de servicio.</span><span class="sxs-lookup"><span data-stu-id="7019d-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="7019d-110">Por ejemplo, si quita el grupo de servidores con el pool01.contoso.net de dominio completo (FQDN) del nombre, use este comando para limitar los datos devueltos a directorios de conferencia desde ese grupo de servidores:</span><span class="sxs-lookup"><span data-stu-id="7019d-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
  ```
  Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
  ```

    <span data-ttu-id="7019d-111">Ese comando devuelve sólo los directorios de conferencia donde la propiedad ServiceID contiene el FQDN pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="7019d-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="7019d-112">Para mover directorios de conferencia, ejecute el siguiente comando para cada directorio de conferencia en el grupo de servidores:</span><span class="sxs-lookup"><span data-stu-id="7019d-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
  ```
  Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
  ```

    <span data-ttu-id="7019d-113">Por ejemplo, para mover el directorio de conferencia 3, use este comando, especificando un Skype para el grupo de servidores de Business Server 2019 como el TargetPool:</span><span class="sxs-lookup"><span data-stu-id="7019d-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
  ```
  Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
  ```

    <span data-ttu-id="7019d-114">Si desea mover todos los directorios de conferencia en un grupo de servidores, use un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="7019d-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
  ```
  Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
  ```

<span data-ttu-id="7019d-115">Descargar [Microsoft desinstalar heredado y quitar Roles de servidor](https://go.microsoft.com/fwlink/p/?linkId=246227) para instrucciones paso a paso integrales en retirar grupos heredados.</span><span class="sxs-lookup"><span data-stu-id="7019d-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="7019d-116">Al mover directorios de conferencia, podría encontrarse con el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="7019d-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="7019d-117">Normalmente, este error se produce cuando el Skype para Shell de administración de Business Server requiere un conjunto actualizado de permisos de Active Directory con el fin de completar una tarea.</span><span class="sxs-lookup"><span data-stu-id="7019d-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="7019d-118">Para resolver el problema, cierre la instancia actual de la consola de administración, a continuación, abra una nueva instancia de la consola y vuelva a ejecutar el comando para mover el directorio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7019d-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

