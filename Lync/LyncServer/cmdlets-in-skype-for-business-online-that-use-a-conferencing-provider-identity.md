---
title: Cmdlets de Skype empresarial online que usan una identidad de proveedor de conferencias
description: Cmdlets de Skype empresarial online que usan una identidad de proveedor de conferencias.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a conferencing provider identity
ms:assetid: be5621b6-ec11-4b12-83ec-075af269ca6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362841(v=OCS.15)
ms:contentKeyID: 56558858
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61ab4fb410878ca73314b73737948d9961462c87
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545736"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity"></a><span data-ttu-id="74495-103">Cmdlets de Skype empresarial online que usan una identidad de proveedor de conferencias</span><span class="sxs-lookup"><span data-stu-id="74495-103">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>

 


<span data-ttu-id="74495-104">Para devolver información acerca de todos los proveedores de audioconferencia con los que la organización ha contratado, simplemente puede llamar al cmdlet [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) sin ningún parámetro:</span><span class="sxs-lookup"><span data-stu-id="74495-104">To return information about all of the audio conferencing providers that your organization has contracted with, you can simply call the [Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\)) cmdlet without any parameters:</span></span>

    Get-CsAudioConferencingProvider

<span data-ttu-id="74495-105">Si desea limitar los datos devueltos a un solo proveedor (en este ejemplo, el proveedor contoso audio Services), use el parámetro Identity:</span><span class="sxs-lookup"><span data-stu-id="74495-105">If you want to limit the returned data to a single provider (in this example, the provider Contoso Audio Services), then use the Identity parameter:</span></span>

    Get-CsAudioConferencingProvider -Identity "Contoso Audio Services"

<span data-ttu-id="74495-106">Solo hay un cmdlet de Skype empresarial online que acepta un identificador de proveedor de servicios de audioconferencia:</span><span class="sxs-lookup"><span data-stu-id="74495-106">There is only one Skype for Business Online cmdlet that accepts an audio conferencing provider ID:</span></span>

  - <span data-ttu-id="74495-107">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74495-107">[Get-CsAudioConferencingProvider](https://technet.microsoft.com/library/jj994030\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="74495-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74495-108">See Also</span></span>


[<span data-ttu-id="74495-109">Identidades, ámbitos e inquilinos en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="74495-109">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="74495-110">[Los cmdlets de Skype empresarial online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74495-110">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

