---
title: Configurar la supervisión de SCOM
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de migrar a Microsoft Skype para Business Server 2019, debe completar algunas tareas para configurar Skype para Business Server 2019 trabajar con System Center Operations Manager.
ms.openlocfilehash: c0d15d14e158c33cda5e623ea978a0bc4f0bb920
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028939"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="b5d30-103">Configurar la supervisión de SCOM</span><span class="sxs-lookup"><span data-stu-id="b5d30-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="b5d30-104">Después de migrar a Skype para Business Server 2019, debe completar algunas tareas para configurar Skype para Business Server 2019 trabajar con System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="b5d30-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="b5d30-105">Aplique las actualizaciones a un servidor elegido para administrar la lógica de detección central.</span><span class="sxs-lookup"><span data-stu-id="b5d30-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="b5d30-106">Actualizar la clave del registro de detección central candidato server.</span><span class="sxs-lookup"><span data-stu-id="b5d30-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="b5d30-107">Configure el servidor de administración de System Center Operations Manager principal para invalidar el nodo de detección central candidato.</span><span class="sxs-lookup"><span data-stu-id="b5d30-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="b5d30-108">A continuación se proporcionan instrucciones para llevar a cabo cada una de estas tareas.</span><span class="sxs-lookup"><span data-stu-id="b5d30-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="b5d30-109">Aplique las actualizaciones a un servidor elegido para administrar la lógica de detección central.</span><span class="sxs-lookup"><span data-stu-id="b5d30-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="b5d30-110">Elija a un servidor que tiene System Center Operations Manager archivos del agente se instala y se configura como un nodo de detección candidato.</span><span class="sxs-lookup"><span data-stu-id="b5d30-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="b5d30-111">Aplicar actualizaciones a este servidor.</span><span class="sxs-lookup"><span data-stu-id="b5d30-111">Apply updates to this server.</span></span> <span data-ttu-id="b5d30-112">Vea el tema [aplicar actualizaciones](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="b5d30-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="b5d30-113">Actualizar la clave del registro de detección central candidato server.</span><span class="sxs-lookup"><span data-stu-id="b5d30-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="b5d30-114">En el servidor elegido para administrar la lógica de detección central, abra una ventana de comandos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5d30-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="b5d30-115">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="b5d30-115">At the command line, type the following:</span></span>
    
  ```
  New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
  ```

  ```
  New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
  ```

    > [!NOTE]
    > <span data-ttu-id="b5d30-116">Cada vez que edite el registro, puede experimentar un error que el comando no se pudo si ya existe la clave del registro.</span><span class="sxs-lookup"><span data-stu-id="b5d30-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="b5d30-117">Si sucede esto, puede ignorar el error.</span><span class="sxs-lookup"><span data-stu-id="b5d30-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="b5d30-118">Configurar el servidor principal de administración de System Center Operations Manager para invalidar el nodo de Monitor de detección central candidato.</span><span class="sxs-lookup"><span data-stu-id="b5d30-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="b5d30-119">En un equipo donde se ha instalado la consola de System Center Operations Manager, expanda **Objetos del módulo de administración** y, a continuación, seleccione **Detecciones de objetos**.</span><span class="sxs-lookup"><span data-stu-id="b5d30-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="b5d30-120">Haga clic en **Cambiar ámbito**</span><span class="sxs-lookup"><span data-stu-id="b5d30-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="b5d30-121">En la página **Objetos del módulo de administración de ámbito** , seleccione **Candidato de detección de LS**.</span><span class="sxs-lookup"><span data-stu-id="b5d30-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="b5d30-122">Reemplazar el **Valor efectivo de candidato de detección de LS** en el nombre de servidor candidato elegido en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="b5d30-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="b5d30-123">Para finalizar los cambios, reinicie el servicio de mantenimiento en el servidor de administración de System Center Operations Manager raíz.</span><span class="sxs-lookup"><span data-stu-id="b5d30-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

