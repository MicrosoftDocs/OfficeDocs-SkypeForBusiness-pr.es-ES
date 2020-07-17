---
title: Cmdlets de Skype empresarial online que solo usan el ámbito global
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b97f3c8d9ca7dda0b96db211192350184cbf27b1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755102"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="45bbb-102">Cmdlets de Skype empresarial online que solo usan el ámbito global</span><span class="sxs-lookup"><span data-stu-id="45bbb-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="45bbb-103">Una cantidad de opciones de configuración de Skype empresarial online solo está disponible en el *ámbito global*.</span><span class="sxs-lookup"><span data-stu-id="45bbb-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="45bbb-104">Esto significa que hay una sola colección de opciones de configuración que se aplican a todos los usuarios que están asignados a ese inquilino.</span><span class="sxs-lookup"><span data-stu-id="45bbb-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="45bbb-105">(Cada inquilino tiene su propia colección única de configuración global). Cuando se usan cmdlets que están limitados al ámbito global, el parámetro Identity es opcional.</span><span class="sxs-lookup"><span data-stu-id="45bbb-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="45bbb-106">Por ejemplo, para recuperar las opciones de configuración de reunión, puede usar este comando:</span><span class="sxs-lookup"><span data-stu-id="45bbb-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="45bbb-107">Como alternativa, puede omitir el parámetro Identity y usar este comando más sencillo en su lugar:</span><span class="sxs-lookup"><span data-stu-id="45bbb-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="45bbb-108">Como solo hay una colección global de opciones de configuración de reuniones, los dos comandos devuelven exactamente la misma información.</span><span class="sxs-lookup"><span data-stu-id="45bbb-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="45bbb-109">El parámetro Identity también puede omitirse cuando se usa uno de los cmdlets **set-CS** .</span><span class="sxs-lookup"><span data-stu-id="45bbb-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="45bbb-110">Estos dos comandos son idénticos:</span><span class="sxs-lookup"><span data-stu-id="45bbb-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="45bbb-111">Los dos comandos son idénticos porque, de manera predeterminada, Windows PowerShell modificará la colección global si no se incluye el parámetro Identity.</span><span class="sxs-lookup"><span data-stu-id="45bbb-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="45bbb-112">Los cmdlets siguientes solo funcionan en el ámbito global:</span><span class="sxs-lookup"><span data-stu-id="45bbb-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="45bbb-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="45bbb-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="45bbb-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="45bbb-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="45bbb-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="45bbb-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="45bbb-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="45bbb-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="45bbb-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="45bbb-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="45bbb-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="45bbb-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="45bbb-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="45bbb-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="45bbb-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="45bbb-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="45bbb-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="45bbb-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="45bbb-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="45bbb-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="45bbb-123">Tenga en cuenta que el cmdlet **Remove-CsVoicePolicy** es algo de una anomalía.</span><span class="sxs-lookup"><span data-stu-id="45bbb-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="45bbb-124">En primer lugar, este cmdlet requiere que incluya el parámetro Identity:</span><span class="sxs-lookup"><span data-stu-id="45bbb-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="45bbb-125">En segundo lugar, el cmdlet **Remove-CsVoicePolicy** no elimina realmente la Directiva de voz global; Skype empresarial online no permite eliminar directivas globales ni opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="45bbb-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="45bbb-126">Lo que hace el cmdlet le permite restablecer todas las propiedades de la Directiva de voz global a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="45bbb-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="45bbb-127">Por ejemplo, de forma predeterminada, la propiedad AllowCallForwarding se establece en false.</span><span class="sxs-lookup"><span data-stu-id="45bbb-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="45bbb-128">Sin embargo, es posible que AllowCallForwarding se haya modificado, con el valor ahora establecido en true.</span><span class="sxs-lookup"><span data-stu-id="45bbb-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="45bbb-129">Cuando se ejecuta el cmdlet **Remove-CsVoicePolicy** , la propiedad AllowCallForwarding se revertirá a su valor predeterminado: false.</span><span class="sxs-lookup"><span data-stu-id="45bbb-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="45bbb-130">En la tabla siguiente se resume este escenario:</span><span class="sxs-lookup"><span data-stu-id="45bbb-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45bbb-131">Valor AllowCallForwarding</span><span class="sxs-lookup"><span data-stu-id="45bbb-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="45bbb-132">Escenario</span><span class="sxs-lookup"><span data-stu-id="45bbb-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45bbb-133">Falso</span><span class="sxs-lookup"><span data-stu-id="45bbb-133">False</span></span></p></td>
<td><p><span data-ttu-id="45bbb-134">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="45bbb-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45bbb-135">True</span><span class="sxs-lookup"><span data-stu-id="45bbb-135">True</span></span></p></td>
<td><p><span data-ttu-id="45bbb-136">Una vez modificada la directiva global</span><span class="sxs-lookup"><span data-stu-id="45bbb-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45bbb-137">Falso</span><span class="sxs-lookup"><span data-stu-id="45bbb-137">False</span></span></p></td>
<td><p><span data-ttu-id="45bbb-138">Después <strong>de ejecutar el cmdlet Remove-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="45bbb-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="45bbb-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="45bbb-139">See Also</span></span>


[<span data-ttu-id="45bbb-140">Identidades, ámbitos e inquilinos en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="45bbb-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="45bbb-141">[Los cmdlets de Skype empresarial online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="45bbb-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

