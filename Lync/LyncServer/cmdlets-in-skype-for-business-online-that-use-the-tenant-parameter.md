---
title: Cmdlets de Skype empresarial online que usan el parámetro tenant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd58e375bcacfcb18cbc21e6ac352b8d98b56661
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233095"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="fe5a7-102">Cmdlets de Skype empresarial online que usan el parámetro tenant</span><span class="sxs-lookup"><span data-stu-id="fe5a7-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="fe5a7-103">Al modificar la configuración de su proveedor público, siempre tiene que proporcionar una identidad de inquilino. Esto es cierto incluso si solo tienes un único inquilino.</span><span class="sxs-lookup"><span data-stu-id="fe5a7-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="fe5a7-104">Por ejemplo, este comando configura Windows Live como el único proveedor público con el que los usuarios pueden comunicarse:</span><span class="sxs-lookup"><span data-stu-id="fe5a7-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="fe5a7-105">Afortunadamente, no es necesario escribir el identificador de inquilino (por ejemplo, bf19b7db-6960-41e5-A139-2aa373474354) cada vez que se ejecuta uno de estos cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fe5a7-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="fe5a7-106">En su lugar, puede recuperar el identificador de inquilino ejecutando el cmdlet [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) , almacenando el identificador de inquilino en una variable y, a continuación, usando esa variable cuando llama a uno de los otros cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fe5a7-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="fe5a7-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fe5a7-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="fe5a7-108">Como alternativa, puede hacer esto en un solo comando al recuperar el identificador de inquilino y, a continuación, canalizar ese valor al cmdlet Set-CsTenantPublicProvider:</span><span class="sxs-lookup"><span data-stu-id="fe5a7-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="fe5a7-109">No es necesario especificar el identificador de inquilino al llamar al cmdlet **Get-CsTenant** .</span><span class="sxs-lookup"><span data-stu-id="fe5a7-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="fe5a7-110">Este comando devuelve información sobre su espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="fe5a7-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="fe5a7-111">Los siguientes cmdlets aceptan una identidad de inquilino.</span><span class="sxs-lookup"><span data-stu-id="fe5a7-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="fe5a7-112">Sin embargo, en estos casos, el parámetro es opcional y no es necesario especificarlo al llamar al cmdlet.</span><span class="sxs-lookup"><span data-stu-id="fe5a7-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="fe5a7-113">En su lugar, Windows PowerShell se encontrará eficazmente con la identidad de inquilino en función del inquilino de Skype empresarial online al que esté conectado actualmente:</span><span class="sxs-lookup"><span data-stu-id="fe5a7-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="fe5a7-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fe5a7-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fe5a7-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fe5a7-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fe5a7-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fe5a7-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fe5a7-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fe5a7-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fe5a7-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fe5a7-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="fe5a7-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fe5a7-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="fe5a7-120">Por ejemplo, se puede llamar al cmdlet **Get-CsTenantFederationConfiguration** con este comando:</span><span class="sxs-lookup"><span data-stu-id="fe5a7-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="fe5a7-121">Aunque no sea necesario, puedes incluir el parámetro tenant cuando llames a get-CsTenantFederationConfiguration:</span><span class="sxs-lookup"><span data-stu-id="fe5a7-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="fe5a7-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe5a7-122">See Also</span></span>


[<span data-ttu-id="fe5a7-123">Identidades, ámbitos y espacios empresariales en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="fe5a7-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="fe5a7-124">[Los cmdlets de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="fe5a7-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

