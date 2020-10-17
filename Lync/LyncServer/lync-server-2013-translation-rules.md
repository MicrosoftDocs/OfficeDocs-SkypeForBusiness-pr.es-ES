---
title: 'Lync Server 2013: reglas de conversión'
description: 'Lync Server 2013: reglas de conversión.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65ee21459123ea09f54eb52e65a4d9ecba61c386
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549046"
---
# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="c899f-103">Reglas de conversión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c899f-103">Translation rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c899f-104">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="c899f-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="c899f-105">Lync Server 2013 Enterprise Voice requiere que todas las cadenas de marcado se normalizan al formato E. 164 con el propósito de realizar la búsqueda inversa de números (RNL).</span><span class="sxs-lookup"><span data-stu-id="c899f-105">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="c899f-106">En Microsoft Lync Server 2010, las reglas de conversión solo se admiten para números con nombre.</span><span class="sxs-lookup"><span data-stu-id="c899f-106">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="c899f-107">New in Microsoft Lync Server 2013, también se admiten las reglas de conversión para números de llamada.</span><span class="sxs-lookup"><span data-stu-id="c899f-107">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="c899f-108">La *entidad del mismo nivel que el tronco* (esto es, la puerta de enlace asociada, la central de comunicación (PBX) o el tronco SIP) puede requerir que los números estén en un formato de marcado local.</span><span class="sxs-lookup"><span data-stu-id="c899f-108">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="c899f-109">Para convertir números del formato E.164 a un formato de marcado local, puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco.</span><span class="sxs-lookup"><span data-stu-id="c899f-109">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="c899f-110">Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.</span><span class="sxs-lookup"><span data-stu-id="c899f-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="c899f-111">Mediante la conversión de la ruta saliente del servidor, se pueden reducir los requisitos de configuración de cada entidad del mismo nivel que el tronco individual para convertir los números de teléfono en un formato de marcado local.</span><span class="sxs-lookup"><span data-stu-id="c899f-111">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="c899f-112">Al planear qué puertas de enlace y cuántas puertas de enlace, para asociar con un clúster de servidor de mediación específico, puede resultar útil agrupar los pares de tronco con requisitos de marcado local similares.</span><span class="sxs-lookup"><span data-stu-id="c899f-112">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="c899f-113">De este modo, se puede reducir el número de reglas de conversión requeridas y el tiempo necesario para escribirlas.</span><span class="sxs-lookup"><span data-stu-id="c899f-113">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c899f-114">La Asociación de una o más reglas de traducción con una configuración de tronco de Enterprise Voice debe usarse como alternativa a la configuración de reglas de conversión en el tronco del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="c899f-114">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="c899f-115">No asocie reglas de conversión a una configuración de tronco de telefonía IP empresarial si ha configurado reglas de conversión en el sistema de tronco del mismo nivel, ya que las dos reglas podrían entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="c899f-115">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="c899f-116">Reglas de conversión de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c899f-116">Example Translation Rules</span></span>

<span data-ttu-id="c899f-117">Los siguientes ejemplos de reglas de conversión muestran cómo se pueden desarrollar reglas en el servidor para convertir números del formato E.164 a un formato local para la entidad del mismo nivel que el tronco.</span><span class="sxs-lookup"><span data-stu-id="c899f-117">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="c899f-118">Para obtener más información sobre cómo implementar reglas de conversión, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="c899f-118">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c899f-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="c899f-119">Description</span></span></th>
<th><span data-ttu-id="c899f-120">Dígitos iniciales</span><span class="sxs-lookup"><span data-stu-id="c899f-120">Starting Digits</span></span></th>
<th><span data-ttu-id="c899f-121">Length</span><span class="sxs-lookup"><span data-stu-id="c899f-121">Length</span></span></th>
<th><span data-ttu-id="c899f-122">Dígitos que se van a quitar</span><span class="sxs-lookup"><span data-stu-id="c899f-122">Digits to Remove</span></span></th>
<th><span data-ttu-id="c899f-123">Dígitos que se van a agregar</span><span class="sxs-lookup"><span data-stu-id="c899f-123">Digits to Add</span></span></th>
<th><span data-ttu-id="c899f-124">Patrón de comparación</span><span class="sxs-lookup"><span data-stu-id="c899f-124">Matching Pattern</span></span></th>
<th><span data-ttu-id="c899f-125">Translation</span><span class="sxs-lookup"><span data-stu-id="c899f-125">Translation</span></span></th>
<th><span data-ttu-id="c899f-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c899f-126">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c899f-127">Marcado convencional de larga distancia en EE.UU.</span><span class="sxs-lookup"><span data-stu-id="c899f-127">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="c899f-128">(quite el "+")</span><span class="sxs-lookup"><span data-stu-id="c899f-128">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="c899f-129">+ 1</span><span class="sxs-lookup"><span data-stu-id="c899f-129">+1</span></span></p></td>
<td><p><span data-ttu-id="c899f-130">Exactamente 12</span><span class="sxs-lookup"><span data-stu-id="c899f-130">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="c899f-131">1</span><span class="sxs-lookup"><span data-stu-id="c899f-131">1</span></span></p></td>
<td><p><span data-ttu-id="c899f-132">comprendi</span><span class="sxs-lookup"><span data-stu-id="c899f-132">0</span></span></p></td>
<td><p><span data-ttu-id="c899f-133">^\+(1 \ d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="c899f-133">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="c899f-134">$1</span><span class="sxs-lookup"><span data-stu-id="c899f-134">$1</span></span></p></td>
<td><p><span data-ttu-id="c899f-135">+14255551010 se convierte en 14255551010</span><span class="sxs-lookup"><span data-stu-id="c899f-135">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c899f-136">Marcado internacional de larga distancia de EE.UU.</span><span class="sxs-lookup"><span data-stu-id="c899f-136">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="c899f-137">(quite el "+" y agregue 011)</span><span class="sxs-lookup"><span data-stu-id="c899f-137">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="c899f-138">11 como mínimo</span><span class="sxs-lookup"><span data-stu-id="c899f-138">At least 11</span></span></p></td>
<td><p><span data-ttu-id="c899f-139">1</span><span class="sxs-lookup"><span data-stu-id="c899f-139">1</span></span></p></td>
<td><p><span data-ttu-id="c899f-140">011</span><span class="sxs-lookup"><span data-stu-id="c899f-140">011</span></span></p></td>
<td><p><span data-ttu-id="c899f-141">^\+(\d {9} \d +) $</span><span class="sxs-lookup"><span data-stu-id="c899f-141">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="c899f-142">011 $1</span><span class="sxs-lookup"><span data-stu-id="c899f-142">011$1</span></span></p></td>
<td><p><span data-ttu-id="c899f-143">+441235551010 se convierte en 011441235551010</span><span class="sxs-lookup"><span data-stu-id="c899f-143">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

