---
title: Aprovisionamiento de la topología para ejecutar la carga en escenarios de estrés y rendimiento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: El cambio o el aprovisionamiento de la topología de Skype empresarial Server 2015 permite a los usuarios ejecutar correctamente la herramienta de estrés y rendimiento.
ms.openlocfilehash: c7cdc10b3667ac99376904c81309df739e49844a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299705"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="7e6ac-103">Aprovisionamiento de la topología para ejecutar la carga en escenarios de estrés y rendimiento</span><span class="sxs-lookup"><span data-stu-id="7e6ac-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="7e6ac-104">El cambio o el aprovisionamiento de la topología de Skype empresarial Server 2015 permite a los usuarios ejecutar correctamente la herramienta de estrés y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7e6ac-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="7e6ac-105">En función de la configuración y la configuración actuales de su implementación de Skype empresarial Server 2015, es posible que tenga que realizar algunos cambios en su entorno.</span><span class="sxs-lookup"><span data-stu-id="7e6ac-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="7e6ac-106">A continuación se muestra una lista de esos cambios:</span><span class="sxs-lookup"><span data-stu-id="7e6ac-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="7e6ac-107">Establezca la Directiva de ejecución de Windows PowerShell en no restringido.</span><span class="sxs-lookup"><span data-stu-id="7e6ac-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="7e6ac-108">Si no está seguro de lo que está configurado en este momento, puede abrir el shell de administración de Skype empresarial Server y ejecutar este comando:</span><span class="sxs-lookup"><span data-stu-id="7e6ac-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="7e6ac-109">Si no se devuelve el valor Unrestricted, tendrá que ejecutar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7e6ac-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="7e6ac-110">Para configurar de forma eficaz Skype empresarial Server, necesitará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7e6ac-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="7e6ac-111">Familiarícese con su topología de 2015 de Skype empresarial Server (como nombres de equipos, instancias de servicios, nombres de sitios y directivas).</span><span class="sxs-lookup"><span data-stu-id="7e6ac-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="7e6ac-112">Asigne algunos de los usuarios que se crean a grupos, por ejemplo, grupos de captura de grupo de respuesta (por ejemplo, URI de SIP).</span><span class="sxs-lookup"><span data-stu-id="7e6ac-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="7e6ac-113">Para ejecutar un script desde la línea de comandos, puede usar:</span><span class="sxs-lookup"><span data-stu-id="7e6ac-113">To run a script from command line, you can use:</span></span>
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="7e6ac-114">Normalmente, después de ejecutar un script desde este paquete, la traza resultante se almacenará en un archivo en la misma ruta desde la que se ejecutó el script.</span><span class="sxs-lookup"><span data-stu-id="7e6ac-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="7e6ac-115">También hay un formato de nombre, \<scriptName\>$h $ m $ s. txt.</span><span class="sxs-lookup"><span data-stu-id="7e6ac-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="7e6ac-116">Por tanto, si ejecutaste el ArchivingPolicy. PS1 en 12:15 PM, recibirás un archivo de registro denominado ArchivingPolicy121500. txt.</span><span class="sxs-lookup"><span data-stu-id="7e6ac-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="7e6ac-117">Aunque proporcionamos estos ejemplos para la configuración del servidor, usted puede modificar la configuración y restaurarla o revertirla una vez que haya terminado de ejecutar las pruebas de carga.</span><span class="sxs-lookup"><span data-stu-id="7e6ac-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

