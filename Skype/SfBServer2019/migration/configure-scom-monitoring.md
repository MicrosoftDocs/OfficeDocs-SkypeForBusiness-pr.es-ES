---
title: Configurar la supervisión SCOM
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
description: Después de migrar a Microsoft Skype empresarial Server 2019, debe realizar algunas tareas para configurar Skype empresarial Server 2019 para que funcione con System Center Operations Manager.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754050"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="18e4b-103">Configurar la supervisión SCOM</span><span class="sxs-lookup"><span data-stu-id="18e4b-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="18e4b-104">Después de migrar a Skype empresarial Server 2019, debe realizar algunas tareas para configurar Skype empresarial Server 2019 para que funcione con System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="18e4b-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="18e4b-105">Aplicar actualizaciones a un servidor elegido para administrar la lógica de detección central.</span><span class="sxs-lookup"><span data-stu-id="18e4b-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="18e4b-106">Actualice la clave de registro del servidor candidato de detección central.</span><span class="sxs-lookup"><span data-stu-id="18e4b-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="18e4b-107">Configure el servidor de administración principal de System Center Operations Manager para invalidar el nodo de detección central candidato.</span><span class="sxs-lookup"><span data-stu-id="18e4b-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="18e4b-108">A continuación se proporcionan instrucciones para realizar cada una de estas tareas.</span><span class="sxs-lookup"><span data-stu-id="18e4b-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="18e4b-109">Aplicar actualizaciones a un servidor elegido para administrar la lógica de detección central.</span><span class="sxs-lookup"><span data-stu-id="18e4b-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="18e4b-110">Elija un servidor que tenga los archivos del agente System Center Operations Manager instalados y esté configurado como un nodo de detección candidato.</span><span class="sxs-lookup"><span data-stu-id="18e4b-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="18e4b-111">Aplicar actualizaciones a este servidor.</span><span class="sxs-lookup"><span data-stu-id="18e4b-111">Apply updates to this server.</span></span> <span data-ttu-id="18e4b-112">Vea el tema [Apply updates](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="18e4b-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="18e4b-113">Actualice la clave de registro del servidor candidato de detección central.</span><span class="sxs-lookup"><span data-stu-id="18e4b-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="18e4b-114">En el servidor decidió administrar la lógica de detección central, abra una ventana de comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18e4b-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="18e4b-115">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="18e4b-115">At the command line, type the following:</span></span>
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="18e4b-p102">Al cambiar el registro, puede recibir un error que indica que el comando ha fallado si la clave de registro ya existe. Si le pasa esto, puede ignorar el error de forma segura.</span><span class="sxs-lookup"><span data-stu-id="18e4b-p102">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="18e4b-118">Configure el servidor de administración principal de System Center Operations Manager para invalidar el nodo de monitor de detección central candidato.</span><span class="sxs-lookup"><span data-stu-id="18e4b-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="18e4b-119">En un PC donde se haya instalado la consola de System Center Operations Manager, expanda **Objetos del módulo de administración** y luego seleccione **Detecciones de objetos**.</span><span class="sxs-lookup"><span data-stu-id="18e4b-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="18e4b-120">Haga clic en **cambiar ámbito**</span><span class="sxs-lookup"><span data-stu-id="18e4b-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="18e4b-121">En la página **Objetos de módulo de administración de ámbito**, seleccione **Candidato de detección de LS**.</span><span class="sxs-lookup"><span data-stu-id="18e4b-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="18e4b-122">Reemplace el **Valor efectivo de Candidato de detección de LS** con el nombre del servidor candidato elegido en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="18e4b-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="18e4b-123">Para finalizar los cambios, reinicie el servicio de mantenimiento en el servidor de administración raíz de System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="18e4b-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

