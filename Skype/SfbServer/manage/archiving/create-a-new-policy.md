---
title: Crear una nueva directiva de archivado en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Resumen: obtenga información sobre cómo crear una nueva directiva de archivado para Skype Empresarial Server.'
ms.openlocfilehash: fe3a80708d3810a085f1814e6d16ff3cd4c6057c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095424"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="aeff4-103">Crear una nueva directiva de archivado en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="aeff4-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="aeff4-104">**Resumen:** Obtenga información sobre cómo crear una nueva directiva de archivado para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="aeff4-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="aeff4-105">Puede crear nuevas directivas de archivado mediante el Panel de control o mediante Windows PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="aeff4-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="aeff4-106">Crear una nueva directiva de archivado mediante el Panel de control</span><span class="sxs-lookup"><span data-stu-id="aeff4-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="aeff4-107">Para crear una nueva directiva de archivado mediante el Panel de control:</span><span class="sxs-lookup"><span data-stu-id="aeff4-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="aeff4-108">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="aeff4-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="aeff4-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="aeff4-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="aeff4-110">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="aeff4-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="aeff4-111">Haga clic en **Nuevo** y luego siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="aeff4-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="aeff4-112">Para crear una directiva de archivado de nivel de sitio, haga clic en Directiva de sitio y, a continuación, en Seleccionar un sitio, haga clic en el sitio al que se va **a** aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="aeff4-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="aeff4-113">Para crear una directiva de archivado de nivel de usuario, haga clic en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="aeff4-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="aeff4-114">En **Directiva de archivado nueva**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aeff4-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="aeff4-115">En **Nombre**, especifique un nombre para la nueva directiva (por ejemplo, externalContoso).</span><span class="sxs-lookup"><span data-stu-id="aeff4-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="aeff4-116">En **Descripción**, proporcione información detallada sobre la función de la directiva (por ejemplo, directiva de archivado de usuarios externos para Contoso).</span><span class="sxs-lookup"><span data-stu-id="aeff4-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="aeff4-117">Para controlar el archivado de comunicaciones con usuarios internos, active o desactive la casilla **Archivar comunicaciones internas**.</span><span class="sxs-lookup"><span data-stu-id="aeff4-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="aeff4-118">Para controlar el archivado de comunicaciones externas, active o desactive la casilla **Archivar comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="aeff4-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="aeff4-119">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="aeff4-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="aeff4-120">La configuración de una directiva de usuario únicamente se aplica a los usuarios y grupos de usuarios específicos a los que aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="aeff4-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="aeff4-121">Para obtener más información, [vea Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="aeff4-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="aeff4-122">Crear una nueva directiva de archivado mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aeff4-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="aeff4-123">También puede crear nuevas directivas de archivado mediante el Windows PowerShell **cmdlet New-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="aeff4-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="aeff4-124">Para obtener más información, vea el tema de ayuda del cmdlet [New-CsArchivingPolicy.](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="aeff4-124">For more information, see the help topic for the [New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="aeff4-125">Para crear una nueva directiva de archivado en el nivel de sitio</span><span class="sxs-lookup"><span data-stu-id="aeff4-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="aeff4-126">Este comando crea una nueva directiva de archivado para el sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="aeff4-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="aeff4-127">Para crear una nueva directiva de archivado en el nivel por usuario</span><span class="sxs-lookup"><span data-stu-id="aeff4-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="aeff4-128">Para crear una nueva directiva de archivado en el nivel por usuario, simplemente especifique una identidad única al crear la directiva:</span><span class="sxs-lookup"><span data-stu-id="aeff4-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="aeff4-129">Para crear una nueva directiva de archivado que permita el archivado de sesiones de comunicación interna</span><span class="sxs-lookup"><span data-stu-id="aeff4-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="aeff4-130">Ya que no se especifican parámetros (excepto el parámetro obligatorio de identidad) en los comandos anteriores, las nuevas directivas usarán los valores predeterminados para todas sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="aeff4-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="aeff4-131">Para crear directivas que usen otros valores de propiedades, basta con incluir el parámetro y el valor de parámetro.</span><span class="sxs-lookup"><span data-stu-id="aeff4-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="aeff4-132">Por ejemplo, el siguiente comando crea una directiva de archivado que permite el archivado de sesiones internas de mensajería instantánea:</span><span class="sxs-lookup"><span data-stu-id="aeff4-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="aeff4-133">Para crear una nueva directiva de archivado que permita el archivado de sesiones de comunicación internas y externas</span><span class="sxs-lookup"><span data-stu-id="aeff4-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="aeff4-134">Puede cambiar varios valores de propiedad incluyendo varios parámetros.</span><span class="sxs-lookup"><span data-stu-id="aeff4-134">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="aeff4-135">Por ejemplo, este comando configura la nueva directiva para archivar sesiones de mensajería instantánea internas y externas:</span><span class="sxs-lookup"><span data-stu-id="aeff4-135">For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```