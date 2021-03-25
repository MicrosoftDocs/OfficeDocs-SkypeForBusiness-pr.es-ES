---
title: Restricciones de caracteres especiales en directivas de Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Vea qué problemas hay con caracteres especiales en los nombres de las directivas y qué puede hacer para solucionarlo.
ms.openlocfilehash: 15df8b64f423d1ee20df6e230e4a9cdbebcb56db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116988"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="bff17-103">¿Cuáles son las restricciones de caracteres especiales en directivas de Teams?</span><span class="sxs-lookup"><span data-stu-id="bff17-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="bff17-104">No puede crear ni editar directivas **(para mensajería, reuniones, etc.)** que tengan un carácter especial en el nombre en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bff17-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="bff17-105">Si un nombre de directiva contiene caracteres especiales, se le limitará la administración de estas directivas en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bff17-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="bff17-106">**Por lo tanto, recomendamos encarecidamente que los nombres de directiva no incluyan caracteres especiales.**</span><span class="sxs-lookup"><span data-stu-id="bff17-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="bff17-107">Los nombres de directiva que se han creado con PowerShell para reuniones y mensajería en Teams pueden tener caracteres especiales como @,#,$.</span><span class="sxs-lookup"><span data-stu-id="bff17-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="bff17-108">Sin embargo, si desea realizar cambios en la directiva en el Centro de administración de Microsoft Teams, no podrá hacerlo.</span><span class="sxs-lookup"><span data-stu-id="bff17-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="bff17-109">Si tiene una directiva con caracteres especiales, tendrá que editar la directiva con Windows PowerShell (para siempre) o crear una nueva directiva en el Centro de administración de Microsoft Teams con la misma configuración que la directiva anterior y asignarla al mismo grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="bff17-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="bff17-110">Para quitar caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="bff17-110">To remove special characters</span></span>

<span data-ttu-id="bff17-111">**Paso 1: realizar una conexión remota con PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="bff17-111">**Step 1 - Make a remote connection with PowerShell.**</span></span>
> [!NOTE]
> <span data-ttu-id="bff17-112">Skype Empresarial Online Connector forma parte actualmente del módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="bff17-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell Module.</span></span>
>
> <span data-ttu-id="bff17-113">Si usa la última versión pública de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="bff17-113">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


<span data-ttu-id="bff17-114">**Paso 2: obtenga la configuración de la directiva anterior y capture el resultado.**</span><span class="sxs-lookup"><span data-stu-id="bff17-114">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="bff17-115">Este ejemplo es para una [directiva de](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) mensajería.</span><span class="sxs-lookup"><span data-stu-id="bff17-115">This example is for a [Messaging](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="bff17-116">Los pasos serían los mismos para otros tipos de directiva, pero debe usar el cmdlet correcto.</span><span class="sxs-lookup"><span data-stu-id="bff17-116">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="bff17-117">**Paso 3: crear una directiva nueva.**</span><span class="sxs-lookup"><span data-stu-id="bff17-117">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="bff17-118">Puede crear la nueva directiva con la misma configuración mediante el Centro de administración de Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bff17-118">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="bff17-119">Al ejecutar esto, se creará una nueva directiva, pero tendrá que agregar la configuración correcta si ve [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) y, a continuación, ejecutó:</span><span class="sxs-lookup"><span data-stu-id="bff17-119">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="bff17-120">**Paso 4: Asignar la directiva.**</span><span class="sxs-lookup"><span data-stu-id="bff17-120">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="bff17-121">Vea [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) para obtener más información sobre este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bff17-121">See, [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="bff17-122">**Paso 5: eliminar la directiva anterior.**</span><span class="sxs-lookup"><span data-stu-id="bff17-122">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="bff17-123">Esto eliminará la directiva anterior con los caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="bff17-123">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="bff17-124">Vea [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) para obtener más información sobre este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bff17-124">See, [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="bff17-125">Si este comando se realiza correctamente, ya ha terminado.</span><span class="sxs-lookup"><span data-stu-id="bff17-125">If this command succeeds, you're done.</span></span> <span data-ttu-id="bff17-126">Si el comando anterior devuelve un error, se debe a que la directiva anterior está asignada a los usuarios, por lo que debe ejecutar para quitar todos los usuarios asignados de la directiva:</span><span class="sxs-lookup"><span data-stu-id="bff17-126">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="bff17-127">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bff17-127">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="bff17-128">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="bff17-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bff17-129">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer.</span><span class="sxs-lookup"><span data-stu-id="bff17-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="bff17-130">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="bff17-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bff17-131">¿Por qué necesita usar Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bff17-131">Why you need to use Office 365 PowerShell?</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="bff17-132">[Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="bff17-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="bff17-133">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad frente solo al uso del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="bff17-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="bff17-134">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="bff17-134">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="bff17-135">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bff17-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [<span data-ttu-id="bff17-136">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bff17-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="bff17-137">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="bff17-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="bff17-138">El Windows PowerShell de Skype Empresarial Online le permite crear una sesión remota de Windows PowerShell que se conecte a Skype Empresarial Online y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bff17-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="bff17-139">Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="bff17-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
