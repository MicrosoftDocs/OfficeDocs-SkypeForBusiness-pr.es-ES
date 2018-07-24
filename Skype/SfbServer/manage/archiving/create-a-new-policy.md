---
title: Crear una nueva directiva de archivado en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Resumen: Obtenga información sobre cómo crear una nueva directiva de archivado para Skype para Business Server.'
ms.openlocfilehash: e900bd9ac73a6e192eba7a506d713a56a69e794d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20970361"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="90477-103">Crear una nueva directiva de archivado en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="90477-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="90477-104">**Resumen:** Obtenga información sobre cómo crear una nueva directiva de archivado para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="90477-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="90477-105">Puede crear directivas de archivado por medio del Panel de control o por medio de los cmdlets de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90477-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="90477-106">Crear una directiva de archivado con el Panel de control</span><span class="sxs-lookup"><span data-stu-id="90477-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="90477-107">Para crear una directiva de archivado con el Panel de control:</span><span class="sxs-lookup"><span data-stu-id="90477-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="90477-108">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="90477-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="90477-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="90477-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="90477-110">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="90477-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="90477-111">Haga clic en **Nuevo** y, luego, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="90477-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="90477-112">Para crear una directiva de archivado de nivel de sitio, haga clic en **Directiva de sitio**, en **Seleccionar un sitio** y, después, haga clic en el sitio al que se va a aplicar la directiva.</span><span class="sxs-lookup"><span data-stu-id="90477-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="90477-113">Para crear una directiva de archivado de usuario, haga clic en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="90477-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="90477-114">En **Directiva de archivado nueva**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90477-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="90477-115">En **Nombre**, especifique un nombre para la nueva directiva (por ejemplo, externalContoso).</span><span class="sxs-lookup"><span data-stu-id="90477-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="90477-116">En **Descripción**, proporcione información detallada sobre la función de la directiva (por ejemplo, directiva de archivado de usuarios externos para Contoso).</span><span class="sxs-lookup"><span data-stu-id="90477-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="90477-117">Para controlar el archivado de comunicaciones con usuarios internos, active o desactive la casilla **Archivar comunicaciones internas**.</span><span class="sxs-lookup"><span data-stu-id="90477-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
  - <span data-ttu-id="90477-118">Para controlar el archivado de comunicaciones externas, active o desactive la casilla **Archivar comunicaciones externas**.</span><span class="sxs-lookup"><span data-stu-id="90477-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="90477-119">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="90477-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="90477-120">La configuración de una directiva de usuario únicamente se aplica a los usuarios y grupos de usuarios específicos a los que aplica la directiva.</span><span class="sxs-lookup"><span data-stu-id="90477-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="90477-121">Para obtener información detallada, vea [aplicar una directiva de archivado para los usuarios de Skype para Business Server](apply-a-policy-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="90477-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="90477-122">Crear una directiva de archivado con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90477-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="90477-123">Puede también crear una directiva de archivado con el cmdlet de Windows PowerShell **New-CsArchivingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="90477-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="90477-124">Para obtener más información, vea el tema de ayuda para el cmdlet [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="90477-124">For more information, see the help topic for the [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="90477-125">Crear una directiva de archivado en el ámbito de sitio</span><span class="sxs-lookup"><span data-stu-id="90477-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="90477-126">Este comando crea una directiva de archivado para el sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="90477-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="90477-127">Para crear una directiva de archivado por usuario</span><span class="sxs-lookup"><span data-stu-id="90477-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="90477-128">Para crear una directiva de archivado por usuario, simplemente especifique una identidad única al crear la directiva:</span><span class="sxs-lookup"><span data-stu-id="90477-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="90477-129">Para crear una directiva de archivado que permita el archivado de sesiones de comunicaciones internas</span><span class="sxs-lookup"><span data-stu-id="90477-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="90477-130">Ya que no se especifican parámetros (excepto el parámetro obligatorio Identity) en los comandos anteriores, las nuevas directivas usarán los valores predeterminados para todas sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="90477-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="90477-131">Para crear directivas que usen otros valores de propiedades, basta con incluir el parámetro y el valor de parámetro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="90477-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="90477-132">Por ejemplo, el siguiente comando crea una directiva de archivado que permite el archivado de sesiones de mensajería instantánea internas:</span><span class="sxs-lookup"><span data-stu-id="90477-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="90477-133">Para crear una directiva de archivado que permita el archivado de sesiones de comunicaciones tanto internas como externas</span><span class="sxs-lookup"><span data-stu-id="90477-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="90477-p104">Con la inclusión de varios parámetros se pueden cambiar varios valores de propiedad. Por ejemplo, este comando configura la nueva directiva de archivado de sesiones de mensajería instantánea internas y externas:</span><span class="sxs-lookup"><span data-stu-id="90477-p104">Multiple property values can be modified by including multiple parameters. For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```