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
# <a name="move-conference-directories"></a><span data-ttu-id="87fd6-103">Mover directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="87fd6-103">Move Conference Directories</span></span>

<span data-ttu-id="87fd6-104">Antes de dar de baja un grupo, debe realizar el siguiente procedimiento para cada directorio de conferencia de su grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="87fd6-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="87fd6-105">Para mover un directorio de conferencia a Skype empresarial Server 2019</span><span class="sxs-lookup"><span data-stu-id="87fd6-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="87fd6-106">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="87fd6-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="87fd6-107">Para obtener la identidad de los directorios de conferencia de su organización, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="87fd6-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="87fd6-108">El comando anterior devuelve todos los directorios de conferencia de su organización.</span><span class="sxs-lookup"><span data-stu-id="87fd6-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="87fd6-109">Por eso, es posible que desee limitar los resultados al grupo que se va a retirar.</span><span class="sxs-lookup"><span data-stu-id="87fd6-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="87fd6-110">Por ejemplo, si va a retirar el grupo con el nombre de dominio completo (FQDN) pool01.contoso.net, use este comando para limitar los datos devueltos a los directorios de conferencia de ese grupo:</span><span class="sxs-lookup"><span data-stu-id="87fd6-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="87fd6-111">Ese comando devuelve solo los directorios de la Conferencia en los que la propiedad ServiceID contiene el FQDN pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="87fd6-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="87fd6-112">Para mover los directorios de la Conferencia, ejecute el comando siguiente para cada directorio de conferencia del Grupo:</span><span class="sxs-lookup"><span data-stu-id="87fd6-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="87fd6-113">Por ejemplo, para mover el directorio de conferencia 3, use este comando, especificando un grupo de servidores de Skype empresarial 2019 como TargetPool:</span><span class="sxs-lookup"><span data-stu-id="87fd6-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="87fd6-114">Si quiere mover todos los directorios de conferencia de un grupo, use un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="87fd6-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="87fd6-115">Descargue [desinstalando Microsoft Legacy y quitando roles de servidor](https://go.microsoft.com/fwlink/p/?linkId=246227) para obtener instrucciones detalladas paso a paso sobre la retirada de grupos heredados.</span><span class="sxs-lookup"><span data-stu-id="87fd6-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="87fd6-116">Al mover los directorios de la Conferencia, es posible que se produzca el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="87fd6-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="87fd6-117">Este error suele ocurrir cuando el shell de administración de Skype empresarial Server requiere un conjunto actualizado de permisos de Active Directory para poder completar una tarea.</span><span class="sxs-lookup"><span data-stu-id="87fd6-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="87fd6-118">Para resolver el problema, cierre la instancia actual del shell de administración, abra una nueva instancia de la Shell y vuelva a ejecutar el comando para mover el directorio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="87fd6-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  

