---
title: Aprovisionamiento de la topología para ejecutar la carga en situaciones de estrés y rendimiento
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype para cambios de topología de servidor de negocios 2015 o provisioning para permitir a los usuarios ejecutar correctamente la herramienta de carga y rendimiento.
ms.openlocfilehash: 825dd56a7f2cb343eddd8cbed7e811cdc5154b9c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="7e5f7-103">Aprovisionamiento de la topología para ejecutar la carga en situaciones de estrés y rendimiento</span><span class="sxs-lookup"><span data-stu-id="7e5f7-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="7e5f7-104">Skype para cambios de topología de servidor de negocios 2015 o provisioning para permitir a los usuarios ejecutar correctamente la herramienta de carga y rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="7e5f7-105">Dependiendo de la configuración existente y la configuración de la implementación de Skype para Business Server 2015, puede que necesite realizar algunos cambios en su entorno.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="7e5f7-106">La siguiente es una lista de los cambios:</span><span class="sxs-lookup"><span data-stu-id="7e5f7-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="7e5f7-107">Establecer la directiva de ejecución de Windows PowerShell en Irrestricto.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="7e5f7-108">Si no estás seguro de lo que es establecido en la actualidad, puede abrir el Skype para el Shell de administración de servidor de Business y ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="7e5f7-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
  ```
  Get-ExecutionPolicy
  ```

  <span data-ttu-id="7e5f7-109">Si no se devuelve el valor Unrestricted, necesitará ejecutar este a continuación:</span><span class="sxs-lookup"><span data-stu-id="7e5f7-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
  ```
  Set-ExecutionPolicy -Unrestricted
  ```

2. <span data-ttu-id="7e5f7-110">Para configurar eficazmente Skype para Business Server, necesitará:</span><span class="sxs-lookup"><span data-stu-id="7e5f7-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="7e5f7-111">Estar familiarizado con su Skype para Business Server 2015 topología (por ejemplo, nombres de equipo, las instancias de servicio, los nombres de sitio y directivas).</span><span class="sxs-lookup"><span data-stu-id="7e5f7-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="7e5f7-112">Asignar algunos de los usuarios que se crean a grupos, como grupo de respuesta de captura de grupos (por ejemplo, URI de SIP).</span><span class="sxs-lookup"><span data-stu-id="7e5f7-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="7e5f7-113">Para ejecutar un script desde la línea de comandos, puede utilizar:</span><span class="sxs-lookup"><span data-stu-id="7e5f7-113">To run a script from command line, you can use:</span></span>
    
  ```
  PowerShell.exe -file <path to the file>
  ```

4. <span data-ttu-id="7e5f7-114">Normalmente, una vez ejecutado un script de este paquete, los seguimientos resultantes se guardará en un archivo en la misma ruta de acceso desde donde se ejecutó la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="7e5f7-115">Hay también un formato de nombre \<scriptname\>$h$m$s.txt.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="7e5f7-116">Así que si ejecutó el ArchivingPolicy.ps1 a las 12:15 P.M., obtendrá un archivo de registro denominado ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="7e5f7-117">Mientras que la configuración del servidor le hemos proporcionado en estos ejemplos, incumbe a usted para modificar su configuración y restaurar o hacerla girar después de que haya terminado de ejecutar las pruebas de carga.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

