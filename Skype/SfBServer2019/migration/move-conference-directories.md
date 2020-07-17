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
# <a name="move-conference-directories"></a><span data-ttu-id="dcec4-103">Mover directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="dcec4-103">Move Conference Directories</span></span>

<span data-ttu-id="dcec4-104">Antes de retirar un grupo de servidores, debe realizar el siguiente procedimiento para cada directorio de conferencia del grupo de servidores heredado.</span><span class="sxs-lookup"><span data-stu-id="dcec4-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="dcec4-105">Para mover un directorio de conferencia a Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="dcec4-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="dcec4-106">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="dcec4-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="dcec4-107">Para obtener la identidad de los directorios de conferencia de su organización, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="dcec4-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="dcec4-108">El comando anterior devuelve todos los directorios de conferencia de la organización.</span><span class="sxs-lookup"><span data-stu-id="dcec4-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="dcec4-109">Por ello, es posible que desee limitar los resultados al grupo de servidores que se está retirando.</span><span class="sxs-lookup"><span data-stu-id="dcec4-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="dcec4-110">Por ejemplo, si va a retirar el grupo de servidores con el nombre de dominio completo (FQDN) pool01.contoso.net, use este comando para limitar los datos devueltos a los directorios de conferencia de ese grupo:</span><span class="sxs-lookup"><span data-stu-id="dcec4-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="dcec4-111">Este comando devuelve sólo los directorios de conferencia en los que la propiedad ServiceID contiene el FQDN pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="dcec4-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="dcec4-112">Para mover los directorios de conferencia, ejecute el siguiente comando para cada directorio de conferencia del Grupo:</span><span class="sxs-lookup"><span data-stu-id="dcec4-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="dcec4-113">Por ejemplo, para mover el directorio de conferencia 3, use este comando, especificando un grupo de servidores de Skype empresarial Server 2019 como TargetPool:</span><span class="sxs-lookup"><span data-stu-id="dcec4-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="dcec4-114">Si desea mover todos los directorios de conferencia en un grupo de servidores, use un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="dcec4-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="dcec4-115">Descargue la desinstalación de la versión [heredada de Microsoft y la eliminación de roles de servidor](https://go.microsoft.com/fwlink/p/?linkId=246227) para obtener instrucciones detalladas paso a paso sobre la retirada de grupos de servidores heredados.</span><span class="sxs-lookup"><span data-stu-id="dcec4-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="dcec4-116">Al mover los directorios de conferencia, es posible que se produzca el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="dcec4-116">When moving conference directories, you might encounter the following error:</span></span>
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="dcec4-117">Este error suele producirse cuando el shell de administración de Skype empresarial Server requiere un conjunto actualizado de permisos de Active Directory para poder completar una tarea.</span><span class="sxs-lookup"><span data-stu-id="dcec4-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="dcec4-118">Para solucionar el problema, cierre la instancia actual del shell de administración, abra una nueva instancia del shell y vuelva a ejecutar el comando para mover el directorio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="dcec4-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

