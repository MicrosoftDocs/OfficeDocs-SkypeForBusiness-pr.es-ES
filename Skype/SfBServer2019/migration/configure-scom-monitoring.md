---
title: Configurar la supervisión SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de migrar a Microsoft Skype empresarial Server 2019, debe completar algunas tareas para configurar la 2019 de Skype empresarial Server para que funcione con System Center Operations Manager.
ms.openlocfilehash: 141154a8bd678f15fcc919b2dd70a50ca9d4dcca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284504"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="2d5cd-103">Configurar la supervisión SCOM</span><span class="sxs-lookup"><span data-stu-id="2d5cd-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="2d5cd-104">Después de migrar a Skype empresarial Server 2019, debe completar algunas tareas para configurar la 2019 de Skype empresarial Server para que funcione con System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="2d5cd-105">Aplicar actualizaciones a un servidor elegido para administrar la lógica de detección centralizada.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="2d5cd-106">Actualice la clave del registro del candidato de detección central.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="2d5cd-107">Configure el servidor de administración principal de System Center Operations Manager para que invalide el nodo de detección central candidato.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="2d5cd-108">A continuación se proporcionan instrucciones para llevar a cabo estas tareas.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="2d5cd-109">Aplicar actualizaciones a un servidor elegido para administrar la lógica de detección centralizada.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="2d5cd-110">Elija un servidor que tenga instalados los archivos del agente System Center Operations Manager y esté configurado como un nodo de detección candidato.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="2d5cd-111">Aplicar actualizaciones a este servidor.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-111">Apply updates to this server.</span></span> <span data-ttu-id="2d5cd-112">Vea el tema sobre cómo [aplicar actualizaciones](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="2d5cd-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="2d5cd-113">Actualice la clave del registro del candidato de detección central.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="2d5cd-114">En el servidor elegido para administrar la lógica de detección central, abra una ventana de comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="2d5cd-115">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="2d5cd-115">At the command line, type the following:</span></span>
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="2d5cd-116">Siempre que edite el registro, es posible que se produzca un error en el comando si la clave del registro ya existe.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="2d5cd-117">Si tiene esto, puede ignorar el error sin riesgos.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="2d5cd-118">Configure su servidor de administración principal de System Center Operations Manager para invalidar el nodo de supervisor de detección central candidato.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="2d5cd-119">En un equipo en el que se haya instalado la consola de System Center Operations Manager, expanda los **objetos del módulo de administración** y seleccione descubrimientos de **objetos**.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="2d5cd-120">Haga clic en **cambiar ámbito** .</span><span class="sxs-lookup"><span data-stu-id="2d5cd-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="2d5cd-121">En la página **objetos del módulo de administración del ámbito** , seleccione candidato de detección de **LS**.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="2d5cd-122">Invalide el **valor efectivo candidato** a la detección de LS al nombre del servidor candidato elegido en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="2d5cd-123">Para finalizar los cambios, reinicie el servicio de mantenimiento en el servidor de administración de raíz de System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="2d5cd-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

