---
title: Asignar directivas de conferencia en Skype Empresarial Server
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
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Resumen: obtenga información sobre cómo asignar directivas de conferencia en Skype Empresarial Server.'
ms.openlocfilehash: 61082a9189b085c852e7593207fc86dcc6509139
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099166"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="e3489-103">Asignar directivas de conferencia en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e3489-103">Assign conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="e3489-104">**Resumen:** Obtenga información sobre cómo asignar directivas de conferencia en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e3489-104">**Summary:** Learn how to assign conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="e3489-105">Puede asignar directivas de conferencia a los usuarios mediante el Shell de administración de Skype Empresarial Server y el cmdlet **Grant-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="e3489-105">You can assign conferencing policies to users by using Skype for Business Server Management Shell and the **Grant-CsConferencingPolicy** cmdlet.</span></span>
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e3489-106">Asignar directivas de conferencia mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e3489-106">Assign conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="e3489-107">En el siguiente ejemplo, la directiva SalesConferencingPolicy se asigna al usuario con la identidad "Ken Myer":</span><span class="sxs-lookup"><span data-stu-id="e3489-107">In the following example, the policy SalesConferencingPolicy is assigned to the user with the Identity "Ken Myer":</span></span>
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

<span data-ttu-id="e3489-108">En el siguiente ejemplo, la directiva de conferencia FinanceConferencingPolicy se asigna a todos los usuarios que tienen cuentas en la unidad organizativa Finanzas.</span><span class="sxs-lookup"><span data-stu-id="e3489-108">In the next example, the conferencing policy FinanceConferencingPolicy is assigned to all the users who have accounts in the Finance organizational unit.</span></span> <span data-ttu-id="e3489-109">A fin de asignar la misma directiva a todos los usuarios en determinada unidad organizativa (OU), se usa el cmdlet Get-CsUser para recuperar todas las cuentas en esa OU.</span><span class="sxs-lookup"><span data-stu-id="e3489-109">To assign the same policy to all the users in a given organizational unit (OU), the Get-CsUser cmdlet is used to retrieve all the accounts in that OU.</span></span> <span data-ttu-id="e3489-110">Una vez recuperadas las cuentas de usuario, esa información se canalizará al cmdlet Grant-CsConferencingPolicy, que asigna la directiva FinanceConferencingPolicy a cada usuario de la colección:</span><span class="sxs-lookup"><span data-stu-id="e3489-110">After the user accounts have been retrieved, that information is then piped to the Grant-CsConferencingPolicy cmdlet, which assigns the FinanceConferencingPolicy policy to each user in the collection:</span></span>
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

<span data-ttu-id="e3489-111">Para obtener más información, incluida la sintaxis completa y una lista de parámetros, [vea Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e3489-111">For more information, including complete syntax and a list of parameters, see [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).</span></span>
