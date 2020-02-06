---
title: Configurar la supervisión SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Después de migrar a Microsoft Skype empresarial Server 2019, debe completar algunas tareas para configurar la 2019 de Skype empresarial Server para que funcione con System Center Operations Manager.
ms.openlocfilehash: 79398336bf372fd2ca779d2ec2ff58dc5219da61
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813808"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="f1386-103">Configurar la supervisión SCOM</span><span class="sxs-lookup"><span data-stu-id="f1386-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="f1386-104">Después de migrar a Skype empresarial Server 2019, debe completar algunas tareas para configurar la 2019 de Skype empresarial Server para que funcione con System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="f1386-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="f1386-105">Aplicar actualizaciones a un servidor elegido para administrar la lógica de detección centralizada.</span><span class="sxs-lookup"><span data-stu-id="f1386-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="f1386-106">Actualice la clave del registro del candidato de detección central.</span><span class="sxs-lookup"><span data-stu-id="f1386-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="f1386-107">Configure el servidor de administración principal de System Center Operations Manager para que invalide el nodo de detección central candidato.</span><span class="sxs-lookup"><span data-stu-id="f1386-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="f1386-108">A continuación se proporcionan instrucciones para llevar a cabo estas tareas.</span><span class="sxs-lookup"><span data-stu-id="f1386-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="f1386-109">Aplicar actualizaciones a un servidor elegido para administrar la lógica de detección centralizada.</span><span class="sxs-lookup"><span data-stu-id="f1386-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="f1386-110">Elija un servidor que tenga instalados los archivos del agente System Center Operations Manager y esté configurado como un nodo de detección candidato.</span><span class="sxs-lookup"><span data-stu-id="f1386-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="f1386-111">Aplicar actualizaciones a este servidor.</span><span class="sxs-lookup"><span data-stu-id="f1386-111">Apply updates to this server.</span></span> <span data-ttu-id="f1386-112">Vea el tema sobre cómo [aplicar actualizaciones](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="f1386-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="f1386-113">Actualice la clave del registro del candidato de detección central.</span><span class="sxs-lookup"><span data-stu-id="f1386-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="f1386-114">En el servidor elegido para administrar la lógica de detección central, abra una ventana de comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1386-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="f1386-115">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="f1386-115">At the command line, type the following:</span></span>
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="f1386-116">Siempre que edite el registro, es posible que se produzca un error en el comando si la clave del registro ya existe.</span><span class="sxs-lookup"><span data-stu-id="f1386-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="f1386-117">Si tiene esto, puede ignorar el error sin riesgos.</span><span class="sxs-lookup"><span data-stu-id="f1386-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="f1386-118">Configure su servidor de administración principal de System Center Operations Manager para invalidar el nodo de supervisor de detección central candidato.</span><span class="sxs-lookup"><span data-stu-id="f1386-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="f1386-119">En un equipo en el que se haya instalado la consola de System Center Operations Manager, expanda los **objetos del módulo de administración** y seleccione **descubrimientos de objetos**.</span><span class="sxs-lookup"><span data-stu-id="f1386-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="f1386-120">Haga clic en **cambiar ámbito** .</span><span class="sxs-lookup"><span data-stu-id="f1386-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="f1386-121">En la página **objetos del módulo de administración del ámbito** , seleccione candidato de detección de **LS**.</span><span class="sxs-lookup"><span data-stu-id="f1386-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="f1386-122">Invalide el **valor efectivo candidato** a la detección de LS al nombre del servidor candidato elegido en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="f1386-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="f1386-123">Para finalizar los cambios, reinicie el servicio de mantenimiento en el servidor de administración de raíz de System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="f1386-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

