---
title: 'Lync Server 2013: configuración de la negociación para socios federados XMPP'
description: 'Lync Server 2013: configuración de la negociación para socios federados XMPP.'
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
ms.openlocfilehash: 6ac3d9c69d407dc750a1afb35f0a448869a88f09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578646"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a><span data-ttu-id="d648d-103">Configuración de la negociación para socios federados XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d648d-103">Negotiation settings for XMPP federated partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d648d-104">_**Última modificación del tema:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="d648d-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="d648d-105">Las opciones de configuración de los tipos de negociación en la configuración de un socio XMPP se pueden combinar de una infinidad de formas.</span><span class="sxs-lookup"><span data-stu-id="d648d-105">The settings for the negotiation types in the configuration of an XMPP Partner have a wide variety of possible combinations.</span></span> <span data-ttu-id="d648d-106">Aunque no todas las combinaciones son válidas.</span><span class="sxs-lookup"><span data-stu-id="d648d-106">Not all of these combinations are valid.</span></span> <span data-ttu-id="d648d-107">En la tabla incluida en este tema se define cuáles son válidas y cuáles no.</span><span class="sxs-lookup"><span data-stu-id="d648d-107">The table detailed in this topic will define the valid and not valid settings.</span></span> <span data-ttu-id="d648d-108">En la primera tabla se presentan las configuraciones comunes y en la segunda, todas las combinaciones posibles.</span><span class="sxs-lookup"><span data-stu-id="d648d-108">Common configurations are presented in the first table, the second table detailing all possible combinations.</span></span> <span data-ttu-id="d648d-109">Tenga en cuenta que no puede tener una *capa de seguridad y autenticación simple* (SASL) **a menos que** la seguridad de la *capa de transporte* (TLS) también esté disponible.</span><span class="sxs-lookup"><span data-stu-id="d648d-109">Note that you cannot have *Simple Authentication and Security Layer* (SASL) **unless** *Transport Layer Security* (TLS) is also available.</span></span> <span data-ttu-id="d648d-110">La SASL se envía en formato no cifrado (legible) y no debe enviarse a menos que se proteja por otro medio, como puede ser TLS.</span><span class="sxs-lookup"><span data-stu-id="d648d-110">SASL is sent in an unencrypted (readable) format and should never be transmitted unless protected by another means, such as TLS.</span></span>

### <a name="common-xmpp-federation-negotiation-methods"></a><span data-ttu-id="d648d-111">Métodos de negociación de federación de XMPP</span><span class="sxs-lookup"><span data-stu-id="d648d-111">Common XMPP Federation Negotiation Methods</span></span>

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
<th><span data-ttu-id="d648d-112">Seguridad de capa de transporte (TLS)</span><span class="sxs-lookup"><span data-stu-id="d648d-112">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="d648d-113">Capa de autenticación y seguridad simple (SASL)</span><span class="sxs-lookup"><span data-stu-id="d648d-113">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="d648d-114">Autenticación por devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="d648d-114">Dialback Authentication</span></span></th>
<th><span data-ttu-id="d648d-115">Método(s) de autenticación esperado(s)</span><span class="sxs-lookup"><span data-stu-id="d648d-115">Expected Authentication Method(s)</span></span></th>
<th><span data-ttu-id="d648d-116">Notas</span><span class="sxs-lookup"><span data-stu-id="d648d-116">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d648d-117">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="d648d-117">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-118">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="d648d-118">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-119">False</span><span class="sxs-lookup"><span data-stu-id="d648d-119">False</span></span></p></td>
<td><p><span data-ttu-id="d648d-120">SASL por TLS</span><span class="sxs-lookup"><span data-stu-id="d648d-120">SASL over TLS</span></span></p></td>
<td><p><span data-ttu-id="d648d-p102">Se requiere el uso de TLS y SASL para garantizar que la transmisión de mensajes SASL es segura. La devolución de llamadas no se encuentra disponible y no se puede utilizar como método de conmutación por recuperación si el socio federado de XMPP no ha definido el uso de TLS como obligatorio u opcional.</span><span class="sxs-lookup"><span data-stu-id="d648d-p102">TLS and SASL required helps to ensure that the SASL message stream is secure. Dialback is not available and cannot be used for a fallback method if the XMPP federated partner has not set TLS to required or optional.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d648d-123">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="d648d-123">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-124">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-125">Verdadero</span><span class="sxs-lookup"><span data-stu-id="d648d-125">True</span></span></p></td>
<td><p><span data-ttu-id="d648d-126">SASL por TLS, Devolución de llamada TLS, Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="d648d-126">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d648d-p103">Al requerir el uso de TLS, si el socio federado de XMPP ha definido el uso de SASL como opcional u obligatorio, se utilizará. Si la SASL no se encuentra disponible, se utilizará la Devolución de llamada TLS.</span><span class="sxs-lookup"><span data-stu-id="d648d-p103">By requiring TLS, if the XMPP federated partner has set SASL to optional or required SASL is used. If SASL is not available, Dialback over TLS will be used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d648d-129">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-130">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-130">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-131">Verdadero</span><span class="sxs-lookup"><span data-stu-id="d648d-131">True</span></span></p></td>
<td><p><span data-ttu-id="d648d-132">SASL por TLS, Devolución de llamada TLS, Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="d648d-132">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d648d-p104">A pesar de ser muy flexibles en cuanto a los métodos de negociación ofrecidos, estas opciones dependen de la configuración del socio de federación XMPP. Si el socio tiene el uso de TLS como opcional u obligatorio, pero no es compatible con la SASL, se tendrá disponible la Devolución de llamada TLS. Si el socio ha definido TLS y SASL como opcionales u obligatorio, se usará la opción óptima, es decir, TLS por SASL.</span><span class="sxs-lookup"><span data-stu-id="d648d-p104">While very flexible in the negotiation methods offered, these settings rely on the XMPP federation partner’s settings. If the partner has TLS optional or required but SASL is not supported, TLS Dialback will be available. If the partner has TLS and SASL set to optional or required, the optimal selection of TLS over SASL is used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d648d-136">No se admite</span><span class="sxs-lookup"><span data-stu-id="d648d-136">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d648d-137">No se admite</span><span class="sxs-lookup"><span data-stu-id="d648d-137">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d648d-138">Verdadero</span><span class="sxs-lookup"><span data-stu-id="d648d-138">True</span></span></p></td>
<td><p><span data-ttu-id="d648d-139">Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="d648d-139">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d648d-p105">En muchos casos, la Devolución de llamada TCP es la única solución posible. Aunque es menos recomendable que otras opciones, ofrece cierto nivel de confianza.</span><span class="sxs-lookup"><span data-stu-id="d648d-p105">In many cases, TCP Dialback is the only possible solution. Less desirable than other options, it does provide some level of trust.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a><span data-ttu-id="d648d-142">Matriz de métodos de negociación de federación XMPP completa</span><span class="sxs-lookup"><span data-stu-id="d648d-142">XMPP Federation Negotiation Methods Matrix - Complete</span></span>

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
<th><span data-ttu-id="d648d-143">Seguridad de capa de transporte (TLS)</span><span class="sxs-lookup"><span data-stu-id="d648d-143">Transport Layer Security (TLS)</span></span></th>
<th><span data-ttu-id="d648d-144">Capa de autenticación y seguridad simple (SASL)</span><span class="sxs-lookup"><span data-stu-id="d648d-144">Simple Authentication and Security Layer (SASL)</span></span></th>
<th><span data-ttu-id="d648d-145">Autenticación por devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="d648d-145">Dialback Authentication</span></span></th>
<th><span data-ttu-id="d648d-146">Método de autenticación esperado</span><span class="sxs-lookup"><span data-stu-id="d648d-146">Expected Authentication Method</span></span></th>
<th><span data-ttu-id="d648d-147">Notas, advertencias o errores en caso de configuraciones no válidas</span><span class="sxs-lookup"><span data-stu-id="d648d-147">Notes, Warning or Error for Not Valid Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d648d-148">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="d648d-148">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-149">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="d648d-149">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-150">Verdadero</span><span class="sxs-lookup"><span data-stu-id="d648d-150">True</span></span></p></td>
<td><p><span data-ttu-id="d648d-151">SASL por TLS</span><span class="sxs-lookup"><span data-stu-id="d648d-151">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d648d-152">La devolución de llamada no funcionará si SASL y TLS son obligatorios.</span><span class="sxs-lookup"><span data-stu-id="d648d-152">Dialback will not operate if both SASL and TLS are required.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d648d-153">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="d648d-153">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-154">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="d648d-154">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-155">False</span><span class="sxs-lookup"><span data-stu-id="d648d-155">False</span></span></p></td>
<td><p><span data-ttu-id="d648d-156">SASL por TLS</span><span class="sxs-lookup"><span data-stu-id="d648d-156">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d648d-157">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-157">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-158">Necesario</span><span class="sxs-lookup"><span data-stu-id="d648d-158">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-159">Verdadero</span><span class="sxs-lookup"><span data-stu-id="d648d-159">True</span></span></p></td>
<td><p><span data-ttu-id="d648d-160">SASL por TLS, Devolución de llamada TLS, Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="d648d-160">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d648d-p106">SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.</span><span class="sxs-lookup"><span data-stu-id="d648d-p106">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d648d-163">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-163">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-164">Necesario</span><span class="sxs-lookup"><span data-stu-id="d648d-164">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-165">False</span><span class="sxs-lookup"><span data-stu-id="d648d-165">False</span></span></p></td>
<td><p><span data-ttu-id="d648d-166">SASL por TLS</span><span class="sxs-lookup"><span data-stu-id="d648d-166">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d648d-p107">SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.</span><span class="sxs-lookup"><span data-stu-id="d648d-p107">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d648d-169">No se admite</span><span class="sxs-lookup"><span data-stu-id="d648d-169">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d648d-170">Necesario</span><span class="sxs-lookup"><span data-stu-id="d648d-170">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-171">Verdadero</span><span class="sxs-lookup"><span data-stu-id="d648d-171">True</span></span></p></td>
<td><p><span data-ttu-id="d648d-172">Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="d648d-172">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d648d-p108">SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.</span><span class="sxs-lookup"><span data-stu-id="d648d-p108">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d648d-175">No se admite</span><span class="sxs-lookup"><span data-stu-id="d648d-175">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d648d-176">Necesario</span><span class="sxs-lookup"><span data-stu-id="d648d-176">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-177">False</span><span class="sxs-lookup"><span data-stu-id="d648d-177">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d648d-178">La configuración no es válida</span><span class="sxs-lookup"><span data-stu-id="d648d-178">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d648d-p109">Como SASL requiere TLS y TLS no está disponible, la combinación SASL/TLS no es viable. La Devolución de llamada TCP se ha definido en False y, por tanto, no se puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="d648d-p109">Because SASL requires TLS, and TLS is not available, SASL/TLS cannot succeed. TCP Dialback is set to false, and cannot be used.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d648d-181">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="d648d-181">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-182">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-182">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-183">Verdadero</span><span class="sxs-lookup"><span data-stu-id="d648d-183">True</span></span></p></td>
<td><p><span data-ttu-id="d648d-184">SASL por TLS, Devolución de llamada TLS</span><span class="sxs-lookup"><span data-stu-id="d648d-184">SASL over TLS, TLS Dialback</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d648d-185">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="d648d-185">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-186">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-186">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-187">False</span><span class="sxs-lookup"><span data-stu-id="d648d-187">False</span></span></p></td>
<td><p><span data-ttu-id="d648d-188">SASL por TLS</span><span class="sxs-lookup"><span data-stu-id="d648d-188">SASL over TLS</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d648d-189">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-189">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-190">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-190">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-191">Verdadero</span><span class="sxs-lookup"><span data-stu-id="d648d-191">True</span></span></p></td>
<td><p><span data-ttu-id="d648d-192">SASL por TLS, Devolución de llamada TLS, Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="d648d-192">SASL over TLS, TLS Dialback, TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d648d-p110">SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.</span><span class="sxs-lookup"><span data-stu-id="d648d-p110">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d648d-195">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-195">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-196">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-196">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-197">False</span><span class="sxs-lookup"><span data-stu-id="d648d-197">False</span></span></p></td>
<td><p><span data-ttu-id="d648d-198">SASL por TLS</span><span class="sxs-lookup"><span data-stu-id="d648d-198">SASL over TLS</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d648d-p111">SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.</span><span class="sxs-lookup"><span data-stu-id="d648d-p111">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d648d-201">No se admite</span><span class="sxs-lookup"><span data-stu-id="d648d-201">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d648d-202">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-202">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-203">Verdadero</span><span class="sxs-lookup"><span data-stu-id="d648d-203">True</span></span></p></td>
<td><p><span data-ttu-id="d648d-204">Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="d648d-204">TCP Dialback</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d648d-p112">SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.</span><span class="sxs-lookup"><span data-stu-id="d648d-p112">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d648d-207">No se admite</span><span class="sxs-lookup"><span data-stu-id="d648d-207">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d648d-208">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-208">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-209">False</span><span class="sxs-lookup"><span data-stu-id="d648d-209">False</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d648d-210">La configuración no es válida</span><span class="sxs-lookup"><span data-stu-id="d648d-210">Not Valid Configuration</span></span>


</div></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d648d-p113">SASL requiere TLS. Si se permite que TLS sea opcional, las negociaciones de sesión pueden fracasar.</span><span class="sxs-lookup"><span data-stu-id="d648d-p113">SASL requires TLS. Allowing TLS to be optional may result in failed session negotiations.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d648d-213">Necesario</span><span class="sxs-lookup"><span data-stu-id="d648d-213">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-214">No se admite</span><span class="sxs-lookup"><span data-stu-id="d648d-214">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d648d-215">Verdadero</span><span class="sxs-lookup"><span data-stu-id="d648d-215">True</span></span></p></td>
<td><p><span data-ttu-id="d648d-216">Devolución de llamada TLS</span><span class="sxs-lookup"><span data-stu-id="d648d-216">TLS Dialback</span></span></p></td>
<td><p><span data-ttu-id="d648d-217">La configuración permite la Devolución de llamada TLS.</span><span class="sxs-lookup"><span data-stu-id="d648d-217">Configuration allows for TLS Dialback.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d648d-218">Necesario</span><span class="sxs-lookup"><span data-stu-id="d648d-218">Required</span></span></p></td>
<td><p><span data-ttu-id="d648d-219">No se admite</span><span class="sxs-lookup"><span data-stu-id="d648d-219">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d648d-220">False</span><span class="sxs-lookup"><span data-stu-id="d648d-220">False</span></span></p></td>
<td><p><span data-ttu-id="d648d-221">La configuración no es válida</span><span class="sxs-lookup"><span data-stu-id="d648d-221">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d648d-222">Es necesario activar SASL o la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="d648d-222">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d648d-223">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-223">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-224">No se admite</span><span class="sxs-lookup"><span data-stu-id="d648d-224">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d648d-225">Verdadero</span><span class="sxs-lookup"><span data-stu-id="d648d-225">True</span></span></p></td>
<td><p><span data-ttu-id="d648d-226">Devolución de llamada TLS, Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="d648d-226">TLS Dialback, TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d648d-227">La Devolución de llamada TCP o TLS se aceptarán o no en función de las opciones de negociación del otro extremo.</span><span class="sxs-lookup"><span data-stu-id="d648d-227">Based on negotiation choices of the other end point, TCP or TLS Dialback will be accepted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d648d-228">Opcional</span><span class="sxs-lookup"><span data-stu-id="d648d-228">Optional</span></span></p></td>
<td><p><span data-ttu-id="d648d-229">No se admite</span><span class="sxs-lookup"><span data-stu-id="d648d-229">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d648d-230">False</span><span class="sxs-lookup"><span data-stu-id="d648d-230">False</span></span></p></td>
<td><p><span data-ttu-id="d648d-231">La configuración no es válida</span><span class="sxs-lookup"><span data-stu-id="d648d-231">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d648d-232">Es necesario activar SASL o la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="d648d-232">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d648d-233">No se admite</span><span class="sxs-lookup"><span data-stu-id="d648d-233">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d648d-234">No se admite</span><span class="sxs-lookup"><span data-stu-id="d648d-234">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d648d-235">Verdadero</span><span class="sxs-lookup"><span data-stu-id="d648d-235">True</span></span></p></td>
<td><p><span data-ttu-id="d648d-236">Devolución de llamada TCP</span><span class="sxs-lookup"><span data-stu-id="d648d-236">TCP Dialback</span></span></p></td>
<td><p><span data-ttu-id="d648d-237">La Devolución de llamada TCP es el único método de negociación disponible</span><span class="sxs-lookup"><span data-stu-id="d648d-237">TCP Dialback is the only negotiation method available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d648d-238">No se admite</span><span class="sxs-lookup"><span data-stu-id="d648d-238">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d648d-239">No se admite</span><span class="sxs-lookup"><span data-stu-id="d648d-239">Not Supported</span></span></p></td>
<td><p><span data-ttu-id="d648d-240">False</span><span class="sxs-lookup"><span data-stu-id="d648d-240">False</span></span></p></td>
<td><p><span data-ttu-id="d648d-241">La configuración no es válida</span><span class="sxs-lookup"><span data-stu-id="d648d-241">Not Valid Configuration</span></span></p></td>
<td><div>

> [!WARNING]  
> <span data-ttu-id="d648d-242">Es necesario activar SASL o la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="d648d-242">SASL or Dialback must be enabled.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

