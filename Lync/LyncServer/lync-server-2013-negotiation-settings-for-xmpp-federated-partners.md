---
title: 'Lync Server 2013: configuración de la negociación para socios federados XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c190e4a45a70bd527aa8fc6323a671d481f04872
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="32d5d-102">Configuración de la negociación para socios federados XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32d5d-102">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32d5d-103">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="32d5d-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="32d5d-104">Las opciones de configuración de los tipos de negociación en la configuración de un socio XMPP se pueden combinar de una infinidad de formas.</span><span class="sxs-lookup"><span data-stu-id="32d5d-104">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="32d5d-105">Aunque no todas las combinaciones son válidas.</span><span class="sxs-lookup"><span data-stu-id="32d5d-105">Not all of these combinations are valid.</span></span> <span data-ttu-id="32d5d-106">En la tabla incluida en este tema se define cuáles son válidas y cuáles no.</span><span class="sxs-lookup"><span data-stu-id="32d5d-106">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="32d5d-107">En la primera tabla se presentan las configuraciones comunes y en la segunda, todas las combinaciones posibles.</span><span class="sxs-lookup"><span data-stu-id="32d5d-107">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="32d5d-108">Tenga en cuenta que no puede tener una *capa de seguridad y autenticación simple* (SASL) **a menos que** la seguridad de la *capa de transporte* (TLS) también esté disponible.</span><span class="sxs-lookup"><span data-stu-id="32d5d-108">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="32d5d-109">La SASL se envía en formato no cifrado (legible) y no debe enviarse a menos que se proteja por otro medio, como puede ser TLS.</span><span class="sxs-lookup"><span data-stu-id="32d5d-109">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="32d5d-110">Métodos de negociación de federación de XMPP</span><span class="sxs-lookup"><span data-stu-id="32d5d-110">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="32d5d-111">Seguridad de capa de transporte (TLS)</span><span class="sxs-lookup"><span data-stu-id="32d5d-111">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="32d5d-112">Capa de autenticación y seguridad simple (SASL)</span><span class="sxs-lookup"><span data-stu-id="32d5d-112">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="32d5d-113">Autenticación por devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="32d5d-113">Dialback Authentication</span></span></th>
<th><span data-ttu-id="32d5d-114">Método(s) de autenticación esperado(s)</span><span class="sxs-lookup"><span data-stu-id="32d5d-114">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="32d5d-115">Notas</span><span class="sxs-lookup"><span data-stu-id="32d5d-115">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32d5d-116">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-116">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-117">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-117">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-118">False</span><span class="sxs-lookup"><span data-stu-id="32d5d-118">False</span></span></p></td>
<td><p><span data-ttu-id="32d5d-119">SASL por TLS</span><span class="sxs-lookup"><span data-stu-id="32d5d-119">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="32d5d-p102">Se requiere el uso de TLS y SASL para garantizar que la transmisión de mensajes SASL es segura. La devolución de llamadas no se encuentra disponible y no se puede utilizar como método de conmutación por recuperación si el socio federado de XMPP no ha definido el uso de TLS como obligatorio u opcional.</span><span class="sxs-lookup"><span data-stu-id="32d5d-p102">TLS and SASL required helps to ensure that the SASL message stream is secure. Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32d5d-122">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-122">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-123">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-124">True</span><span class="sxs-lookup"><span data-stu-id="32d5d-124">True</span></span></p></td>
<td><p><span data-ttu-id="32d5d-125">SASL por TLS, Devolución de llamada TLS, Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="32d5d-125">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="32d5d-p103">Al requerir el uso de TLS, si el socio federado de XMPP ha definido el uso de SASL como opcional u obligatorio, se utilizará. Si la SASL no se encuentra disponible, se utilizará la Devolución de llamada TLS.</span><span class="sxs-lookup"><span data-stu-id="32d5d-p103">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used. If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32d5d-128">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-128">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-129">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-130">True</span><span class="sxs-lookup"><span data-stu-id="32d5d-130">True</span></span></p></td>
<td><p><span data-ttu-id="32d5d-131">SASL por TLS, Devolución de llamada TLS, Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="32d5d-131">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="32d5d-p104">A pesar de ser muy flexibles en cuanto a los métodos de negociación ofrecidos, estas opciones dependen de la configuración del socio de federación XMPP. Si el socio tiene el uso de TLS como opcional u obligatorio, pero no es compatible con la SASL, se tendrá disponible la Devolución de llamada TLS. Si el socio ha definido TLS y SASL como opcionales u obligatorio, se usará la opción óptima, es decir, TLS por SASL.</span><span class="sxs-lookup"><span data-stu-id="32d5d-p104">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings. If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available. If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32d5d-135">No se admite</span><span class="sxs-lookup"><span data-stu-id="32d5d-135">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="32d5d-136">No compatible</span><span class="sxs-lookup"><span data-stu-id="32d5d-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="32d5d-137">True</span><span class="sxs-lookup"><span data-stu-id="32d5d-137">True</span></span></p></td>
<td><p><span data-ttu-id="32d5d-138">Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="32d5d-138">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="32d5d-p105">En muchos casos, la Devolución de llamada TCP es la única solución posible. Aunque es menos recomendable que otras opciones, ofrece cierto nivel de confianza.</span><span class="sxs-lookup"><span data-stu-id="32d5d-p105">In many cases, TCP Dialback is the only possible solution. Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="32d5d-141">Matriz de métodos de negociación de federación XMPP completa</span><span class="sxs-lookup"><span data-stu-id="32d5d-141">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="32d5d-142">Seguridad de capa de transporte (TLS)</span><span class="sxs-lookup"><span data-stu-id="32d5d-142">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="32d5d-143">Capa de autenticación y seguridad simple (SASL)</span><span class="sxs-lookup"><span data-stu-id="32d5d-143">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="32d5d-144">Autenticación por devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="32d5d-144">Dialback Authentication</span></span></th>
<th><span data-ttu-id="32d5d-145">Método de autenticación esperado</span><span class="sxs-lookup"><span data-stu-id="32d5d-145">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="32d5d-146">Notas, advertencias o errores en caso de configuraciones no válidas</span><span class="sxs-lookup"><span data-stu-id="32d5d-146">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32d5d-147">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-147">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-148">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-148">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-149">True</span><span class="sxs-lookup"><span data-stu-id="32d5d-149">True</span></span></p></td>
<td><p><span data-ttu-id="32d5d-150">SASL por TLS</span><span class="sxs-lookup"><span data-stu-id="32d5d-150">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="32d5d-151">La devolución de llamada no funcionará si SASL y TLS son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="32d5d-151">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32d5d-152">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-152">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-153">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-153">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-154">False</span><span class="sxs-lookup"><span data-stu-id="32d5d-154">False</span></span></p></td>
<td><p><span data-ttu-id="32d5d-155">SASL por TLS</span><span class="sxs-lookup"><span data-stu-id="32d5d-155">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32d5d-156">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-156">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-157">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-157">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-158">True</span><span class="sxs-lookup"><span data-stu-id="32d5d-158">True</span></span></p></td>
<td><p><span data-ttu-id="32d5d-159">SASL por TLS, Devolución de llamada TLS, Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="32d5d-159">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="32d5d-160">SASL requiere TLS.</span><span class="sxs-lookup"><span data-stu-id="32d5d-160">SASL requires TLS.</span></span> <span data-ttu-id="32d5d-161">Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.</span><span class="sxs-lookup"><span data-stu-id="32d5d-161">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32d5d-162">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-162">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-163">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-163">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-164">False</span><span class="sxs-lookup"><span data-stu-id="32d5d-164">False</span></span></p></td>
<td><p><span data-ttu-id="32d5d-165">SASL por TLS</span><span class="sxs-lookup"><span data-stu-id="32d5d-165">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="32d5d-166">SASL requiere TLS.</span><span class="sxs-lookup"><span data-stu-id="32d5d-166">SASL requires TLS.</span></span> <span data-ttu-id="32d5d-167">Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.</span><span class="sxs-lookup"><span data-stu-id="32d5d-167">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32d5d-168">No compatible</span><span class="sxs-lookup"><span data-stu-id="32d5d-168">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="32d5d-169">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-169">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-170">True</span><span class="sxs-lookup"><span data-stu-id="32d5d-170">True</span></span></p></td>
<td><p><span data-ttu-id="32d5d-171">Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="32d5d-171">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="32d5d-172">SASL requiere TLS.</span><span class="sxs-lookup"><span data-stu-id="32d5d-172">SASL requires TLS.</span></span> <span data-ttu-id="32d5d-173">Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.</span><span class="sxs-lookup"><span data-stu-id="32d5d-173">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32d5d-174">No compatible</span><span class="sxs-lookup"><span data-stu-id="32d5d-174">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="32d5d-175">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-175">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-176">False</span><span class="sxs-lookup"><span data-stu-id="32d5d-176">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="32d5d-177">La configuración no es válida</span><span class="sxs-lookup"><span data-stu-id="32d5d-177">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="32d5d-p109">Como SASL requiere TLS y TLS no está disponible, la combinación SASL/TLS no es viable. La Devolución de llamada TCP se ha definido en False y, por tanto, no se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="32d5d-p109">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed. TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32d5d-180">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-180">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-181">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-181">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-182">True</span><span class="sxs-lookup"><span data-stu-id="32d5d-182">True</span></span></p></td>
<td><p><span data-ttu-id="32d5d-183">SASL por TLS, Devolución de llamada TLS</span><span class="sxs-lookup"><span data-stu-id="32d5d-183">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32d5d-184">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-184">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-185">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-185">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-186">False</span><span class="sxs-lookup"><span data-stu-id="32d5d-186">False</span></span></p></td>
<td><p><span data-ttu-id="32d5d-187">SASL por TLS</span><span class="sxs-lookup"><span data-stu-id="32d5d-187">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32d5d-188">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-188">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-189">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-190">True</span><span class="sxs-lookup"><span data-stu-id="32d5d-190">True</span></span></p></td>
<td><p><span data-ttu-id="32d5d-191">SASL por TLS, Devolución de llamada TLS, Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="32d5d-191">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="32d5d-192">SASL requiere TLS.</span><span class="sxs-lookup"><span data-stu-id="32d5d-192">SASL requires TLS.</span></span> <span data-ttu-id="32d5d-193">Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.</span><span class="sxs-lookup"><span data-stu-id="32d5d-193">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32d5d-194">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-194">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-195">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-196">False</span><span class="sxs-lookup"><span data-stu-id="32d5d-196">False</span></span></p></td>
<td><p><span data-ttu-id="32d5d-197">SASL por TLS</span><span class="sxs-lookup"><span data-stu-id="32d5d-197">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="32d5d-198">SASL requiere TLS.</span><span class="sxs-lookup"><span data-stu-id="32d5d-198">SASL requires TLS.</span></span> <span data-ttu-id="32d5d-199">Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.</span><span class="sxs-lookup"><span data-stu-id="32d5d-199">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32d5d-200">No compatible</span><span class="sxs-lookup"><span data-stu-id="32d5d-200">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="32d5d-201">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-201">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-202">True</span><span class="sxs-lookup"><span data-stu-id="32d5d-202">True</span></span></p></td>
<td><p><span data-ttu-id="32d5d-203">Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="32d5d-203">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="32d5d-204">SASL requiere TLS.</span><span class="sxs-lookup"><span data-stu-id="32d5d-204">SASL requires TLS.</span></span> <span data-ttu-id="32d5d-205">Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.</span><span class="sxs-lookup"><span data-stu-id="32d5d-205">Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32d5d-206">No compatible</span><span class="sxs-lookup"><span data-stu-id="32d5d-206">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="32d5d-207">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-207">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-208">False</span><span class="sxs-lookup"><span data-stu-id="32d5d-208">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="32d5d-209">La configuración no es válida</span><span class="sxs-lookup"><span data-stu-id="32d5d-209">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="32d5d-p113">SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.</span><span class="sxs-lookup"><span data-stu-id="32d5d-p113">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32d5d-212">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-212">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-213">No compatible</span><span class="sxs-lookup"><span data-stu-id="32d5d-213">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="32d5d-214">True</span><span class="sxs-lookup"><span data-stu-id="32d5d-214">True</span></span></p></td>
<td><p><span data-ttu-id="32d5d-215">Devolución de llamada TLS</span><span class="sxs-lookup"><span data-stu-id="32d5d-215">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="32d5d-216">La configuración permite la Devolución de llamada TLS.</span><span class="sxs-lookup"><span data-stu-id="32d5d-216">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32d5d-217">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="32d5d-217">Required</span></span></p></td>
<td><p><span data-ttu-id="32d5d-218">No se admite</span><span class="sxs-lookup"><span data-stu-id="32d5d-218">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="32d5d-219">False</span><span class="sxs-lookup"><span data-stu-id="32d5d-219">False</span></span></p></td>
<td><p><span data-ttu-id="32d5d-220">La configuración no es válida</span><span class="sxs-lookup"><span data-stu-id="32d5d-220">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="32d5d-221">Es necesario activar SASL o la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="32d5d-221">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32d5d-222">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-222">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-223">No compatible</span><span class="sxs-lookup"><span data-stu-id="32d5d-223">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="32d5d-224">True</span><span class="sxs-lookup"><span data-stu-id="32d5d-224">True</span></span></p></td>
<td><p><span data-ttu-id="32d5d-225">Devolución de llamada TLS, Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="32d5d-225">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="32d5d-226">La Devolución de llamada TCP o TLS se aceptarán o no en función de las opciones de negociación del otro extremo.</span><span class="sxs-lookup"><span data-stu-id="32d5d-226">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32d5d-227">Opcional</span><span class="sxs-lookup"><span data-stu-id="32d5d-227">Optional</span></span></p></td>
<td><p><span data-ttu-id="32d5d-228">No se admite</span><span class="sxs-lookup"><span data-stu-id="32d5d-228">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="32d5d-229">False</span><span class="sxs-lookup"><span data-stu-id="32d5d-229">False</span></span></p></td>
<td><p><span data-ttu-id="32d5d-230">La configuración no es válida</span><span class="sxs-lookup"><span data-stu-id="32d5d-230">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="32d5d-231">Es necesario activar SASL o la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="32d5d-231">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32d5d-232">No compatible</span><span class="sxs-lookup"><span data-stu-id="32d5d-232">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="32d5d-233">No compatible</span><span class="sxs-lookup"><span data-stu-id="32d5d-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="32d5d-234">True</span><span class="sxs-lookup"><span data-stu-id="32d5d-234">True</span></span></p></td>
<td><p><span data-ttu-id="32d5d-235">Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="32d5d-235">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="32d5d-236">La Devolución de llamada TCP es el único método de negociación disponible</span><span class="sxs-lookup"><span data-stu-id="32d5d-236">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32d5d-237">No se admite</span><span class="sxs-lookup"><span data-stu-id="32d5d-237">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="32d5d-238">No se admite</span><span class="sxs-lookup"><span data-stu-id="32d5d-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="32d5d-239">False</span><span class="sxs-lookup"><span data-stu-id="32d5d-239">False</span></span></p></td>
<td><p><span data-ttu-id="32d5d-240">La configuración no es válida</span><span class="sxs-lookup"><span data-stu-id="32d5d-240">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="32d5d-241">Es necesario activar SASL o la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="32d5d-241">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

