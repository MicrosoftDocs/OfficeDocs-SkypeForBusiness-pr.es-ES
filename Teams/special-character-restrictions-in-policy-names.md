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
description: Vea qué problemas tienen caracteres especiales en los nombres de las directivas y qué puede hacer para corregirlo.
ms.openlocfilehash: 899cffa45bc5ec7a36339e89e3cb97e35e6e4507
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814719"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="83d0b-103">¿Cuáles son las restricciones de caracteres especiales en directivas de Teams?</span><span class="sxs-lookup"><span data-stu-id="83d0b-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="83d0b-104">No puede crear o editar directivas **(para mensajería, reuniones, etc.)** que tengan un carácter especial en el nombre en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="83d0b-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="83d0b-105">Si el nombre de una directiva contiene caracteres especiales, estará limitado a la administración de estas directivas en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="83d0b-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="83d0b-106">**Por lo tanto, es muy recomendable que los nombres de directiva no incluyan caracteres especiales.**</span><span class="sxs-lookup"><span data-stu-id="83d0b-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="83d0b-107">Los nombres de directiva que se han creado con PowerShell para reuniones y mensajería en Teams pueden tener caracteres especiales como @,#,$.</span><span class="sxs-lookup"><span data-stu-id="83d0b-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="83d0b-108">Sin embargo, si quiere realizar cambios en la directiva en el Centro de administración de Microsoft Teams, no podrá hacerlo.</span><span class="sxs-lookup"><span data-stu-id="83d0b-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="83d0b-109">Si tiene una directiva con caracteres especiales, tendrá que editarla con Windows PowerShell (para siempre) o crear una directiva en el Centro de administración de Microsoft Teams con la misma configuración que la directiva anterior y asignarla al mismo grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="83d0b-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="83d0b-110">Para quitar caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="83d0b-110">To remove special characters</span></span>

<span data-ttu-id="83d0b-111">**Paso 1: realizar una conexión remota con PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="83d0b-111">**Step 1 - Make a remote connection with PowerShell.**</span></span>
> [!NOTE]
> <span data-ttu-id="83d0b-112">Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.</span><span class="sxs-lookup"><span data-stu-id="83d0b-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell Module.</span></span>
>
> <span data-ttu-id="83d0b-113">Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.</span><span class="sxs-lookup"><span data-stu-id="83d0b-113">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```PowerShell
 Import-Module -Name MicrosoftTeams
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="83d0b-114">**Paso 2: obtenga la configuración de la directiva anterior y capture el resultado.**</span><span class="sxs-lookup"><span data-stu-id="83d0b-114">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="83d0b-115">Este ejemplo es para una directiva [de](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) mensajería.</span><span class="sxs-lookup"><span data-stu-id="83d0b-115">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="83d0b-116">Los pasos serían los mismos para otros tipos de directiva, pero debe usar el cmdlet correcto.</span><span class="sxs-lookup"><span data-stu-id="83d0b-116">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="83d0b-117">**Paso 3: Crear una directiva.**</span><span class="sxs-lookup"><span data-stu-id="83d0b-117">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="83d0b-118">Puede crear la nueva directiva con la misma configuración mediante el Centro de administración de Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83d0b-118">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="83d0b-119">Si ejecuta esta opción, se creará una directiva para usted, pero deberá agregar la configuración correcta en [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) y, a continuación, ejecutarla:</span><span class="sxs-lookup"><span data-stu-id="83d0b-119">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="83d0b-120">**Paso 4: asignar la directiva.**</span><span class="sxs-lookup"><span data-stu-id="83d0b-120">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="83d0b-121">Vea [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) para obtener más información sobre este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="83d0b-121">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="83d0b-122">**Paso 5: eliminar la directiva anterior.**</span><span class="sxs-lookup"><span data-stu-id="83d0b-122">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="83d0b-123">Se eliminará la directiva anterior con los caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="83d0b-123">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="83d0b-124">Vea [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) para obtener más información sobre este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="83d0b-124">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="83d0b-125">Si este comando se realiza correctamente, ya ha terminado.</span><span class="sxs-lookup"><span data-stu-id="83d0b-125">If this command succeeds, you're done.</span></span> <span data-ttu-id="83d0b-126">Si el comando anterior devuelve un error, se debe a que la directiva anterior está asignada a los usuarios, por lo que tiene que ejecutarla para quitar todos los usuarios asignados de la directiva:</span><span class="sxs-lookup"><span data-stu-id="83d0b-126">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="83d0b-127">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="83d0b-127">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="83d0b-128">Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar.</span><span class="sxs-lookup"><span data-stu-id="83d0b-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="83d0b-129">Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas.</span><span class="sxs-lookup"><span data-stu-id="83d0b-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="83d0b-130">Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="83d0b-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="83d0b-131">¿Por qué necesita usar PowerShell de Office 365?</span><span class="sxs-lookup"><span data-stu-id="83d0b-131">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="83d0b-132">Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="83d0b-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="83d0b-133">Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="83d0b-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="83d0b-134">Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="83d0b-134">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="83d0b-135">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="83d0b-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="83d0b-136">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="83d0b-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="83d0b-137">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="83d0b-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="83d0b-138">El Windows PowerShell de administración de Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="83d0b-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="83d0b-139">Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="83d0b-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

