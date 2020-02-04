---
title: 'Lync Server 2013: Inicio de Lync desde otra aplicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Starting Lync from another application
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398376(v=OCS.15)
ms:contentKeyID: 48184184
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dafb8295d3070cd9f38e8691e654146978156d45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a><span data-ttu-id="ac420-102">Iniciar Lync desde otra aplicación</span><span class="sxs-lookup"><span data-stu-id="ac420-102">Starting Lync from another application</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac420-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ac420-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ac420-104">Puede usar parámetros de la línea de comandos para iniciar rápidamente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ac420-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="ac420-105">Por ejemplo, si un usuario hace clic en un número de teléfono de otra aplicación, la aplicación puede iniciar una instancia de Lync 2013 e iniciar una llamada a ese número.</span><span class="sxs-lookup"><span data-stu-id="ac420-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="ac420-106">Lync 2013 también puede reconocer una lista de nombres de contactos delimitados por punto y coma para las conferencias de varias partes.</span><span class="sxs-lookup"><span data-stu-id="ac420-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="ac420-107">Si Lync 2013 está configurado para iniciar sesión automáticamente al iniciarse, al iniciar Lync 2013 con parámetros de línea de comandos se abrirá la ventana principal de Lync.</span><span class="sxs-lookup"><span data-stu-id="ac420-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="ac420-108">Si Lync no está configurado para iniciar sesión automáticamente al iniciarse, se abrirá la ventana de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="ac420-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="ac420-109">En la tabla siguiente se muestran los parámetros disponibles.</span><span class="sxs-lookup"><span data-stu-id="ac420-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="ac420-110">Parámetros de la línea de comandos de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ac420-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac420-111">Extensiones</span><span class="sxs-lookup"><span data-stu-id="ac420-111">Extension</span></span></th>
<th><span data-ttu-id="ac420-112">Formato de datos</span><span class="sxs-lookup"><span data-stu-id="ac420-112">Format of Data</span></span></th>
<th><span data-ttu-id="ac420-113">Acción</span><span class="sxs-lookup"><span data-stu-id="ac420-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac420-114">Tel</span><span class="sxs-lookup"><span data-stu-id="ac420-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="ac420-115">URI de Tel</span><span class="sxs-lookup"><span data-stu-id="ac420-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="ac420-116">Abre la ventana de conversación de una llamada de audio, pero no marca el número especificado.</span><span class="sxs-lookup"><span data-stu-id="ac420-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac420-117">callto</span><span class="sxs-lookup"><span data-stu-id="ac420-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="ac420-118">Tel:, SIP:, o URI de Tel.</span><span class="sxs-lookup"><span data-stu-id="ac420-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="ac420-119">Abre la ventana de conversación de una llamada de audio, pero no marca el número especificado.</span><span class="sxs-lookup"><span data-stu-id="ac420-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac420-120">SIP</span><span class="sxs-lookup"><span data-stu-id="ac420-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="ac420-121">URI del SIP</span><span class="sxs-lookup"><span data-stu-id="ac420-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="ac420-122">Abre la ventana de conversación con el identificador uniforme de recursos (URI) SIP especificado en la lista de participantes.</span><span class="sxs-lookup"><span data-stu-id="ac420-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac420-123">SIPs</span><span class="sxs-lookup"><span data-stu-id="ac420-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="ac420-124">URI del SIP</span><span class="sxs-lookup"><span data-stu-id="ac420-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="ac420-125">Si Lync 2013 está configurado para usar el protocolo seguridad de la capa de transporte (TLS), funciona exactamente igual que SIP:.</span><span class="sxs-lookup"><span data-stu-id="ac420-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="ac420-126">Si no se usa TLS, se muestra un cuadro de diálogo que informa al usuario de que se requiere un mayor nivel de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ac420-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac420-127">Conferencia</span><span class="sxs-lookup"><span data-stu-id="ac420-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="ac420-128">URI SIP de conferencia para unirse</span><span class="sxs-lookup"><span data-stu-id="ac420-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="ac420-129">Si el URI es self, crea una instancia del foco y abre la vista de solo configuración.</span><span class="sxs-lookup"><span data-stu-id="ac420-129">If URI is self, instantiates the focus and brings up roster-only view.</span></span> <span data-ttu-id="ac420-130">De lo contrario, muestra la vista de lista, pero no envía la invitación.</span><span class="sxs-lookup"><span data-stu-id="ac420-130">Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac420-131">mensajería</span><span class="sxs-lookup"><span data-stu-id="ac420-131">im:</span></span></p></td>
<td><p><span data-ttu-id="ac420-132">URI del SIP</span><span class="sxs-lookup"><span data-stu-id="ac420-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="ac420-133">Muestra una ventana de conversación de mensajería instantánea solo con el URI del SIP.</span><span class="sxs-lookup"><span data-stu-id="ac420-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="ac420-134">Acepta varios URI de SIP especificados entre corchetes angulares (&lt;&gt;) sin separador.</span><span class="sxs-lookup"><span data-stu-id="ac420-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ac420-135">En la tabla siguiente se muestran algunos ejemplos de estos parámetros de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ac420-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="ac420-136">Ejemplos de parámetros de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="ac420-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac420-137">Vez</span><span class="sxs-lookup"><span data-stu-id="ac420-137">Instance</span></span></th>
<th><span data-ttu-id="ac420-138">Obtenidos</span><span class="sxs-lookup"><span data-stu-id="ac420-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac420-139">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="ac420-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="ac420-140">Abre una vista de solo teléfono con + 14255550101.</span><span class="sxs-lookup"><span data-stu-id="ac420-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac420-141">Callto: Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="ac420-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="ac420-142">Abre una vista de solo teléfono con + 14255550101.</span><span class="sxs-lookup"><span data-stu-id="ac420-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac420-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ac420-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="ac420-144">Abre una vista solo para teléfono con kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ac420-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac420-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ac420-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="ac420-146">Abre una ventana de conversación con kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ac420-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac420-147">conf: SIP:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="ac420-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="ac420-148">Abre una ventana de conversación y muestra las opciones de combinación de audio de la reunión.</span><span class="sxs-lookup"><span data-stu-id="ac420-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

