---
title: Cmdlets de Skype empresarial online que solo usan el ámbito global
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 210e9116152ebe071ec81d2e0d48ff31b7c20a60
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233109"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="3a4d5-102">Cmdlets de Skype empresarial online que solo usan el ámbito global</span><span class="sxs-lookup"><span data-stu-id="3a4d5-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="3a4d5-103">Una serie de opciones de configuración de Skype empresarial online solo están disponibles en el *ámbito global*.</span><span class="sxs-lookup"><span data-stu-id="3a4d5-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="3a4d5-104">Esto significa que hay una sola colección de opciones de configuración que se aplica a todos los usuarios que están asignados a ese inquilino.</span><span class="sxs-lookup"><span data-stu-id="3a4d5-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="3a4d5-105">(Cada inquilino tiene su propia recopilación exclusiva de la configuración global). Cuando se usan cmdlets que se limitan al ámbito global, el parámetro Identity es opcional.</span><span class="sxs-lookup"><span data-stu-id="3a4d5-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="3a4d5-106">Por ejemplo, para recuperar la configuración de la reunión, puede usar este comando:</span><span class="sxs-lookup"><span data-stu-id="3a4d5-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="3a4d5-107">Como alternativa, puede omitir el parámetro Identity y usar este comando más sencillo en su lugar:</span><span class="sxs-lookup"><span data-stu-id="3a4d5-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="3a4d5-108">Como solo hay una colección global de valores de configuración de reuniones, los dos comandos devuelven exactamente la misma información.</span><span class="sxs-lookup"><span data-stu-id="3a4d5-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="3a4d5-109">El parámetro Identity también se puede omitir al usar uno de los cmdlets **set-CS** .</span><span class="sxs-lookup"><span data-stu-id="3a4d5-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="3a4d5-110">Estos dos comandos son idénticos:</span><span class="sxs-lookup"><span data-stu-id="3a4d5-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="3a4d5-111">Los dos comandos son idénticos porque, de forma predeterminada, Windows PowerShell modificará la colección global si no incluye el parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="3a4d5-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="3a4d5-112">Los siguientes cmdlets solo funcionan en el ámbito global:</span><span class="sxs-lookup"><span data-stu-id="3a4d5-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="3a4d5-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4d5-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3a4d5-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4d5-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3a4d5-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4d5-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3a4d5-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4d5-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3a4d5-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4d5-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3a4d5-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4d5-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3a4d5-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4d5-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3a4d5-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4d5-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3a4d5-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4d5-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="3a4d5-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4d5-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="3a4d5-123">Tenga en cuenta que el cmdlet **Remove-CsVoicePolicy** es algo de una anomalía.</span><span class="sxs-lookup"><span data-stu-id="3a4d5-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="3a4d5-124">En primer lugar, este cmdlet requiere que incluyas el parámetro Identity:</span><span class="sxs-lookup"><span data-stu-id="3a4d5-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="3a4d5-125">En segundo lugar, el cmdlet **Remove-CsVoicePolicy** realmente no elimina la Directiva de voz global; Skype empresarial online no le permite eliminar directivas globales ni parámetros de configuración.</span><span class="sxs-lookup"><span data-stu-id="3a4d5-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="3a4d5-126">Lo que hace el cmdlet es le permite restablecer todas las propiedades de la Directiva de voz global a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="3a4d5-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="3a4d5-127">Por ejemplo, de forma predeterminada, la propiedad AllowCallForwarding se establece en false.</span><span class="sxs-lookup"><span data-stu-id="3a4d5-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="3a4d5-128">Sin embargo, es posible que se haya modificado AllowCallForwarding, con el valor ahora establecido en true.</span><span class="sxs-lookup"><span data-stu-id="3a4d5-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="3a4d5-129">Al ejecutar el cmdlet **Remove-CsVoicePolicy** , la propiedad AllowCallForwarding revertirá a su valor predeterminado: false.</span><span class="sxs-lookup"><span data-stu-id="3a4d5-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="3a4d5-130">En la tabla siguiente se resume este escenario:</span><span class="sxs-lookup"><span data-stu-id="3a4d5-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a4d5-131">Valor de AllowCallForwarding</span><span class="sxs-lookup"><span data-stu-id="3a4d5-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="3a4d5-132">Escenario</span><span class="sxs-lookup"><span data-stu-id="3a4d5-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a4d5-133">False</span><span class="sxs-lookup"><span data-stu-id="3a4d5-133">False</span></span></p></td>
<td><p><span data-ttu-id="3a4d5-134">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="3a4d5-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a4d5-135">True</span><span class="sxs-lookup"><span data-stu-id="3a4d5-135">True</span></span></p></td>
<td><p><span data-ttu-id="3a4d5-136">Una vez modificada la directiva global</span><span class="sxs-lookup"><span data-stu-id="3a4d5-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a4d5-137">False</span><span class="sxs-lookup"><span data-stu-id="3a4d5-137">False</span></span></p></td>
<td><p><span data-ttu-id="3a4d5-138">Después <strong>de ejecutar el cmdlet Remove-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="3a4d5-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="3a4d5-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a4d5-139">See Also</span></span>


[<span data-ttu-id="3a4d5-140">Identidades, ámbitos y espacios empresariales en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="3a4d5-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="3a4d5-141">[Los cmdlets de Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="3a4d5-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

