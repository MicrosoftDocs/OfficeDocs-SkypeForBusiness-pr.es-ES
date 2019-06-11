---
title: 'Lync Server 2013: Configuración de la negociación para socios federados XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02d72870e4060be6aa4ec428159af7ab19cb68b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="193b7-102">Configuración de la negociación para socios federados XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="193b7-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="193b7-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="193b7-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="193b7-104">La configuración de los tipos de negociación en la configuración de un socio XMPP tiene una amplia variedad de combinaciones posibles.</span><span class="sxs-lookup"><span data-stu-id="193b7-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="193b7-105">No todas estas combinaciones son válidas.</span><span class="sxs-lookup"><span data-stu-id="193b7-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="193b7-106">La tabla que se describe en este tema definirá la configuración válida y no válida.</span><span class="sxs-lookup"><span data-stu-id="193b7-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="193b7-107">Las configuraciones comunes se presentan en la primera tabla, en la segunda tabla, en la que se detallan todas las combinaciones posibles.</span><span class="sxs-lookup"><span data-stu-id="193b7-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="193b7-108">Tenga en cuenta que no puede tener *nivel de autenticación y seguridad simple* (SASL) **a menos que** la seguridad de la *capa de transporte* (TLS) también esté disponible.</span><span class="sxs-lookup"><span data-stu-id="193b7-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="193b7-109">SASL se envía en un formato no cifrado (legible) y nunca debe transmitirse a menos que esté protegido por otro medio, como TLS.</span><span class="sxs-lookup"><span data-stu-id="193b7-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="193b7-110">Métodos comunes de negociación de Federación de XMPP</span><span class="sxs-lookup"><span data-stu-id="193b7-110">Common XMPP Federation Negotiation Methods</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="193b7-111">Seguridad de la capa de transporte (TLS)</span><span class="sxs-lookup"><span data-stu-id="193b7-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="193b7-112">Capa de seguridad y autenticación simple (SASL)</span><span class="sxs-lookup"><span data-stu-id="193b7-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="193b7-113">Autenticación Dialback</span><span class="sxs-lookup"><span data-stu-id="193b7-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="193b7-114">Métodos de autenticación esperados</span><span class="sxs-lookup"><span data-stu-id="193b7-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="193b7-115">Notas</span><span class="sxs-lookup"><span data-stu-id="193b7-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="193b7-116">Requerido </span><span class="sxs-lookup"><span data-stu-id="193b7-116">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-117">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="193b7-117">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-118">False</span><span class="sxs-lookup"><span data-stu-id="193b7-118">False</span></span></p></td>
<td><p><span data-ttu-id="193b7-119">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="193b7-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="193b7-120">TLS y SASL requeridos ayudan a garantizar que la secuencia de mensajes SASL sea segura.</span><span class="sxs-lookup"><span data-stu-id="193b7-120">TLS and SASL required helps to ensure that the SASL message stream is secure.</span></span> <span data-ttu-id="193b7-121">Dialback no está disponible y no se puede usar para un método de reserva si el socio de XMPP federado no ha establecido TLS en requerido u opcional.</span><span class="sxs-lookup"><span data-stu-id="193b7-121">Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="193b7-122">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="193b7-122">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-123">Opcional</span><span class="sxs-lookup"><span data-stu-id="193b7-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-124">True</span><span class="sxs-lookup"><span data-stu-id="193b7-124">True</span></span></p></td>
<td><p><span data-ttu-id="193b7-125">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="193b7-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="193b7-126">Al requerir TLS, si el socio XMPP federado ha establecido SASL a la opción SASL opcional o requerida.</span><span class="sxs-lookup"><span data-stu-id="193b7-126">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used.</span></span> <span data-ttu-id="193b7-127">Si SASL no está disponible, se usará Dialback a través de TLS.</span><span class="sxs-lookup"><span data-stu-id="193b7-127">If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="193b7-128">Opcional </span><span class="sxs-lookup"><span data-stu-id="193b7-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-129">Opcional</span><span class="sxs-lookup"><span data-stu-id="193b7-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-130">True</span><span class="sxs-lookup"><span data-stu-id="193b7-130">True</span></span></p></td>
<td><p><span data-ttu-id="193b7-131">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="193b7-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="193b7-132">Aunque es muy flexible en los métodos de negociación ofrecidos, esta configuración depende de la configuración del socio de Federación de XMPP.</span><span class="sxs-lookup"><span data-stu-id="193b7-132">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings.</span></span> <span data-ttu-id="193b7-133">Si el socio tiene TLS opcional o obligatorio, pero no se admite SASL, la Dialback de TLS estará disponible.</span><span class="sxs-lookup"><span data-stu-id="193b7-133">If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available.</span></span> <span data-ttu-id="193b7-134">Si el asociado tiene TLS y SASL establecido en opcional o en obligatorio, se usa la selección óptima de TLS por SASL.</span><span class="sxs-lookup"><span data-stu-id="193b7-134">If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="193b7-135">No compatible</span><span class="sxs-lookup"><span data-stu-id="193b7-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="193b7-136">No compatible</span><span class="sxs-lookup"><span data-stu-id="193b7-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="193b7-137">True</span><span class="sxs-lookup"><span data-stu-id="193b7-137">True</span></span></p></td>
<td><p><span data-ttu-id="193b7-138">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="193b7-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="193b7-139">En muchos casos, TCP Dialback es la única solución posible.</span><span class="sxs-lookup"><span data-stu-id="193b7-139">In many cases, TCP Dialback is the only possible solution.</span></span> <span data-ttu-id="193b7-140">Menos conveniente que otras opciones, proporciona un cierto nivel de confianza.</span><span class="sxs-lookup"><span data-stu-id="193b7-140">Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="193b7-141">Matriz de métodos de negociación de Federación XMPP-completada</span><span class="sxs-lookup"><span data-stu-id="193b7-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="193b7-142">Seguridad de la capa de transporte (TLS)</span><span class="sxs-lookup"><span data-stu-id="193b7-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="193b7-143">Capa de seguridad y autenticación simple (SASL)</span><span class="sxs-lookup"><span data-stu-id="193b7-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="193b7-144">Autenticación Dialback</span><span class="sxs-lookup"><span data-stu-id="193b7-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="193b7-145">Método de autenticación esperado</span><span class="sxs-lookup"><span data-stu-id="193b7-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="193b7-146">Notas, ADVERTENCIA o error para una configuración no válida</span><span class="sxs-lookup"><span data-stu-id="193b7-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="193b7-147">Requerido </span><span class="sxs-lookup"><span data-stu-id="193b7-147">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-148">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="193b7-148">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-149">True</span><span class="sxs-lookup"><span data-stu-id="193b7-149">True</span></span></p></td>
<td><p><span data-ttu-id="193b7-150">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="193b7-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="193b7-151">Dialback no funcionará si se necesitan SASL y TLS.</span><span class="sxs-lookup"><span data-stu-id="193b7-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="193b7-152">Requerido </span><span class="sxs-lookup"><span data-stu-id="193b7-152">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-153">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="193b7-153">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-154">False</span><span class="sxs-lookup"><span data-stu-id="193b7-154">False</span></span></p></td>
<td><p><span data-ttu-id="193b7-155">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="193b7-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="193b7-156">Opcional</span><span class="sxs-lookup"><span data-stu-id="193b7-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-157">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="193b7-157">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-158">True</span><span class="sxs-lookup"><span data-stu-id="193b7-158">True</span></span></p></td>
<td><p><span data-ttu-id="193b7-159">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="193b7-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="193b7-160">SASL requiere TLS.</span><span class="sxs-lookup"><span data-stu-id="193b7-160">SASL requires TLS.</span></span> <span data-ttu-id="193b7-161">Permitir que TLS sea opcional puede provocar errores en las negociaciones de la sesión.</span><span class="sxs-lookup"><span data-stu-id="193b7-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="193b7-162">Opcional</span><span class="sxs-lookup"><span data-stu-id="193b7-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-163">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="193b7-163">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-164">False</span><span class="sxs-lookup"><span data-stu-id="193b7-164">False</span></span></p></td>
<td><p><span data-ttu-id="193b7-165">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="193b7-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="193b7-166">SASL requiere TLS.</span><span class="sxs-lookup"><span data-stu-id="193b7-166">SASL requires TLS.</span></span> <span data-ttu-id="193b7-167">Permitir que TLS sea opcional puede provocar errores en las negociaciones de la sesión.</span><span class="sxs-lookup"><span data-stu-id="193b7-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="193b7-168">No compatible</span><span class="sxs-lookup"><span data-stu-id="193b7-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="193b7-169">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="193b7-169">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-170">True</span><span class="sxs-lookup"><span data-stu-id="193b7-170">True</span></span></p></td>
<td><p><span data-ttu-id="193b7-171">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="193b7-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="193b7-172">SASL requiere TLS.</span><span class="sxs-lookup"><span data-stu-id="193b7-172">SASL requires TLS.</span></span> <span data-ttu-id="193b7-173">Permitir que TLS sea opcional puede provocar errores en las negociaciones de la sesión.</span><span class="sxs-lookup"><span data-stu-id="193b7-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="193b7-174">No compatible</span><span class="sxs-lookup"><span data-stu-id="193b7-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="193b7-175">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="193b7-175">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-176">False</span><span class="sxs-lookup"><span data-stu-id="193b7-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="193b7-177">Configuración no válida</span><span class="sxs-lookup"><span data-stu-id="193b7-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="193b7-178">Como SASL requiere TLS, y TLS no está disponible, SASL/TLS no se pueden realizar correctamente.</span><span class="sxs-lookup"><span data-stu-id="193b7-178">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed.</span></span> <span data-ttu-id="193b7-179">TCP Dialback se establece en false y no se puede usar.</span><span class="sxs-lookup"><span data-stu-id="193b7-179">TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="193b7-180">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="193b7-180">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-181">Opcional</span><span class="sxs-lookup"><span data-stu-id="193b7-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-182">True</span><span class="sxs-lookup"><span data-stu-id="193b7-182">True</span></span></p></td>
<td><p><span data-ttu-id="193b7-183">SASL sobre TLS, TLS Dialback</span><span class="sxs-lookup"><span data-stu-id="193b7-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="193b7-184">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="193b7-184">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-185">Opcional</span><span class="sxs-lookup"><span data-stu-id="193b7-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-186">False</span><span class="sxs-lookup"><span data-stu-id="193b7-186">False</span></span></p></td>
<td><p><span data-ttu-id="193b7-187">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="193b7-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="193b7-188">Opcional </span><span class="sxs-lookup"><span data-stu-id="193b7-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-189">Opcional</span><span class="sxs-lookup"><span data-stu-id="193b7-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-190">True</span><span class="sxs-lookup"><span data-stu-id="193b7-190">True</span></span></p></td>
<td><p><span data-ttu-id="193b7-191">SASL sobre TLS, TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="193b7-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="193b7-192">SASL requiere TLS.</span><span class="sxs-lookup"><span data-stu-id="193b7-192">SASL requires TLS.</span></span> <span data-ttu-id="193b7-193">Permitir que TLS sea opcional puede provocar errores en las negociaciones de la sesión.</span><span class="sxs-lookup"><span data-stu-id="193b7-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="193b7-194">Opcional </span><span class="sxs-lookup"><span data-stu-id="193b7-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-195">Opcional</span><span class="sxs-lookup"><span data-stu-id="193b7-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-196">False</span><span class="sxs-lookup"><span data-stu-id="193b7-196">False</span></span></p></td>
<td><p><span data-ttu-id="193b7-197">SASL sobre TLS</span><span class="sxs-lookup"><span data-stu-id="193b7-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="193b7-198">SASL requiere TLS.</span><span class="sxs-lookup"><span data-stu-id="193b7-198">SASL requires TLS.</span></span> <span data-ttu-id="193b7-199">Permitir que TLS sea opcional puede provocar errores en las negociaciones de la sesión.</span><span class="sxs-lookup"><span data-stu-id="193b7-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="193b7-200">No compatible</span><span class="sxs-lookup"><span data-stu-id="193b7-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="193b7-201">Opcional</span><span class="sxs-lookup"><span data-stu-id="193b7-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-202">True</span><span class="sxs-lookup"><span data-stu-id="193b7-202">True</span></span></p></td>
<td><p><span data-ttu-id="193b7-203">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="193b7-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="193b7-204">SASL requiere TLS.</span><span class="sxs-lookup"><span data-stu-id="193b7-204">SASL requires TLS.</span></span> <span data-ttu-id="193b7-205">Permitir que TLS sea opcional puede provocar errores en las negociaciones de la sesión.</span><span class="sxs-lookup"><span data-stu-id="193b7-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="193b7-206">No compatible</span><span class="sxs-lookup"><span data-stu-id="193b7-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="193b7-207">Opcional</span><span class="sxs-lookup"><span data-stu-id="193b7-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-208">False</span><span class="sxs-lookup"><span data-stu-id="193b7-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="193b7-209">Configuración no válida</span><span class="sxs-lookup"><span data-stu-id="193b7-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="193b7-210">SASL requiere TLS.</span><span class="sxs-lookup"><span data-stu-id="193b7-210">SASL requires TLS.</span></span> <span data-ttu-id="193b7-211">Permitir que TLS sea opcional puede provocar errores en las negociaciones de la sesión.</span><span class="sxs-lookup"><span data-stu-id="193b7-211">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="193b7-212">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="193b7-212">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-213">No compatible</span><span class="sxs-lookup"><span data-stu-id="193b7-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="193b7-214">True</span><span class="sxs-lookup"><span data-stu-id="193b7-214">True</span></span></p></td>
<td><p><span data-ttu-id="193b7-215">TLS Dialback</span><span class="sxs-lookup"><span data-stu-id="193b7-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="193b7-216">La configuración permite Dialback TLS.</span><span class="sxs-lookup"><span data-stu-id="193b7-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="193b7-217">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="193b7-217">Required</span></span></p></td>
<td><p><span data-ttu-id="193b7-218">No compatible</span><span class="sxs-lookup"><span data-stu-id="193b7-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="193b7-219">False</span><span class="sxs-lookup"><span data-stu-id="193b7-219">False</span></span></p></td>
<td><p><span data-ttu-id="193b7-220">Configuración no válida</span><span class="sxs-lookup"><span data-stu-id="193b7-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="193b7-221">SASL o Dialback deben estar habilitados.</span><span class="sxs-lookup"><span data-stu-id="193b7-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="193b7-222">Opcional</span><span class="sxs-lookup"><span data-stu-id="193b7-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-223">No compatible</span><span class="sxs-lookup"><span data-stu-id="193b7-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="193b7-224">True</span><span class="sxs-lookup"><span data-stu-id="193b7-224">True</span></span></p></td>
<td><p><span data-ttu-id="193b7-225">TLS Dialback, TCP Dialback</span><span class="sxs-lookup"><span data-stu-id="193b7-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="193b7-226">Según las opciones de negociación del otro punto final, se aceptarán TCP o TLS Dialback.</span><span class="sxs-lookup"><span data-stu-id="193b7-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="193b7-227">Opcional</span><span class="sxs-lookup"><span data-stu-id="193b7-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="193b7-228">No compatible</span><span class="sxs-lookup"><span data-stu-id="193b7-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="193b7-229">False</span><span class="sxs-lookup"><span data-stu-id="193b7-229">False</span></span></p></td>
<td><p><span data-ttu-id="193b7-230">Configuración no válida</span><span class="sxs-lookup"><span data-stu-id="193b7-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="193b7-231">SASL o Dialback deben estar habilitados.</span><span class="sxs-lookup"><span data-stu-id="193b7-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="193b7-232">No compatible</span><span class="sxs-lookup"><span data-stu-id="193b7-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="193b7-233">No compatible</span><span class="sxs-lookup"><span data-stu-id="193b7-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="193b7-234">True</span><span class="sxs-lookup"><span data-stu-id="193b7-234">True</span></span></p></td>
<td><p><span data-ttu-id="193b7-235">Dialback TCP</span><span class="sxs-lookup"><span data-stu-id="193b7-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="193b7-236">TCP Dialback es el único método de negociación disponible</span><span class="sxs-lookup"><span data-stu-id="193b7-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="193b7-237">No compatible</span><span class="sxs-lookup"><span data-stu-id="193b7-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="193b7-238">No compatible</span><span class="sxs-lookup"><span data-stu-id="193b7-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="193b7-239">False</span><span class="sxs-lookup"><span data-stu-id="193b7-239">False</span></span></p></td>
<td><p><span data-ttu-id="193b7-240">Configuración no válida</span><span class="sxs-lookup"><span data-stu-id="193b7-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="193b7-241">SASL o Dialback deben estar habilitados.</span><span class="sxs-lookup"><span data-stu-id="193b7-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

