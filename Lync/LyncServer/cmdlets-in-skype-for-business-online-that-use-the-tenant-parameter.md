---
title: Cmdlets en Skype empresarial online que usan el parámetro tenant
description: Cmdlets de Skype empresarial online que usan el parámetro tenant.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff2b8053dd855a854fa26699770d3dafaa0dcbd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546806"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="1ac8a-103">Cmdlets en Skype empresarial online que usan el parámetro tenant</span><span class="sxs-lookup"><span data-stu-id="1ac8a-103">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="1ac8a-104">Al modificar la configuración de un proveedor público, siempre debe proporcionar una identidad de espacio empresarial; Esto es así incluso si solo tiene un único inquilino.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-104">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="1ac8a-105">Por ejemplo, este comando configura Windows Live como el único proveedor público con el que los usuarios pueden comunicarse:</span><span class="sxs-lookup"><span data-stu-id="1ac8a-105">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="1ac8a-106">Afortunadamente, no es necesario escribir el identificador de inquilino (por ejemplo, bf19b7db-6960-41e5-A139-2aa373474354) cada vez que se ejecuta uno de estos cmdlets.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-106">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="1ac8a-107">En su lugar, puede recuperar el identificador de inquilino ejecutando el cmdlet [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) , almacenando el identificador de inquilino en una variable y, a continuación, usando esa variable cuando se llama a uno de los otros cmdlets.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-107">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="1ac8a-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1ac8a-108">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="1ac8a-109">Como alternativa, puede hacer esto en un solo comando al recuperar el identificador de inquilino y, a continuación, canalizar ese valor al cmdlet Set-CsTenantPublicProvider:</span><span class="sxs-lookup"><span data-stu-id="1ac8a-109">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="1ac8a-110">No es necesario especificar el identificador de inquilino al llamar al cmdlet **Get-CsTenant** .</span><span class="sxs-lookup"><span data-stu-id="1ac8a-110">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="1ac8a-111">Este comando devuelve información sobre el espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="1ac8a-111">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="1ac8a-112">Los siguientes cmdlets aceptan una identidad de inquilino.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-112">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="1ac8a-113">Sin embargo, en estos casos, el parámetro es opcional y no es necesario especificarlo al llamar al cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1ac8a-113">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="1ac8a-114">En su lugar, Windows PowerShell introducirá la identidad del espacio empresarial de forma efectiva en el inquilino de Skype empresarial online al que esté conectado actualmente:</span><span class="sxs-lookup"><span data-stu-id="1ac8a-114">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="1ac8a-115">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1ac8a-115">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1ac8a-116">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1ac8a-116">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1ac8a-117">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1ac8a-117">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1ac8a-118">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1ac8a-118">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1ac8a-119">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1ac8a-119">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1ac8a-120">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1ac8a-120">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="1ac8a-121">Por ejemplo, se puede llamar al cmdlet **Get-CsTenantFederationConfiguration** con este comando:</span><span class="sxs-lookup"><span data-stu-id="1ac8a-121">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="1ac8a-122">Aunque no es necesario, puede incluir el parámetro tenant al llamar a Get-CsTenantFederationConfiguration:</span><span class="sxs-lookup"><span data-stu-id="1ac8a-122">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="1ac8a-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ac8a-123">See Also</span></span>


[<span data-ttu-id="1ac8a-124">Identidades, ámbitos e inquilinos en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="1ac8a-124">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="1ac8a-125">[Los cmdlets de Skype empresarial online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1ac8a-125">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

