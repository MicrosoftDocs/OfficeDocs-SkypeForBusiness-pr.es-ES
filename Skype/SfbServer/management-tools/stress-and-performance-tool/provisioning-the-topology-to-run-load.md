---
title: Aprovisionamiento de la topología para ejecutar la carga en escenarios de esfuerzo y rendimiento
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: El aprovisionamiento o los cambios en la topología de Skype Empresarial Server 2015 permiten a los usuarios ejecutar correctamente la herramienta Stress and Performance.
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814940"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="537ff-103">Aprovisionamiento de la topología para ejecutar la carga en escenarios de esfuerzo y rendimiento</span><span class="sxs-lookup"><span data-stu-id="537ff-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="537ff-104">El aprovisionamiento o los cambios en la topología de Skype Empresarial Server 2015 permiten a los usuarios ejecutar correctamente la herramienta Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="537ff-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="537ff-105">Según la configuración y la configuración existentes para la implementación de Skype Empresarial Server 2015, es posible que deba realizar algunos cambios en su entorno.</span><span class="sxs-lookup"><span data-stu-id="537ff-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="537ff-106">A continuación se muestra una lista de los cambios:</span><span class="sxs-lookup"><span data-stu-id="537ff-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="537ff-107">Establezca la directiva Windows PowerShell ejecución en Sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="537ff-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="537ff-108">Si no está seguro de a qué está configurado actualmente, puede abrir el Shell de administración de Skype Empresarial Server y ejecutar este comando:</span><span class="sxs-lookup"><span data-stu-id="537ff-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="537ff-109">Si no se devuelve el valor Sin restricciones, tendrá que ejecutar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="537ff-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="537ff-110">Para configurar Skype Empresarial Server de forma eficaz, tendrá que:</span><span class="sxs-lookup"><span data-stu-id="537ff-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="537ff-111">Familiarícese con la topología de Skype Empresarial Server 2015 (como nombres de equipo, instancias de servicio, nombres de sitio y directivas).</span><span class="sxs-lookup"><span data-stu-id="537ff-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="537ff-112">Asigne algunos de los usuarios que se crean a grupos, como grupos de extensiones de grupo de respuesta (por ejemplo, URI de SIP).</span><span class="sxs-lookup"><span data-stu-id="537ff-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="537ff-113">Para ejecutar un script desde la línea de comandos, puede usar:</span><span class="sxs-lookup"><span data-stu-id="537ff-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="537ff-114">Normalmente, después de ejecutar un script desde este paquete, los seguimientos resultantes se almacenarán en un archivo en la misma ruta de acceso desde donde se ha ejecutado el script.</span><span class="sxs-lookup"><span data-stu-id="537ff-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="537ff-115">También hay un formato de nomenclatura, \<scriptname\> $h$m$s.txt.</span><span class="sxs-lookup"><span data-stu-id="537ff-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="537ff-116">Por lo tanto, si ejecutó la ArchivingPolicy.ps1 a las 12:15 p. m., verá un archivo de registro denominado ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="537ff-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="537ff-117">Aunque hemos proporcionado estos ejemplos para la configuración del servidor, es su función modificar la configuración y restaurarla o revertirla una vez que haya terminado de ejecutar las pruebas de carga.</span><span class="sxs-lookup"><span data-stu-id="537ff-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

