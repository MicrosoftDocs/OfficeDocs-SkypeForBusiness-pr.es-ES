---
title: 'Lync Server 2013: iniciar Lync desde otra aplicación'
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
ms.openlocfilehash: 40e049b2a8a88514b9236ee0172474a5252bfdb1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="starting-lync-from-another-application"></a><span data-ttu-id="73652-102">Iniciar Lync desde otra aplicación</span><span class="sxs-lookup"><span data-stu-id="73652-102">Starting Lync from another application</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73652-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="73652-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="73652-104">Puede usar los parámetros de la línea de comandos para iniciar rápidamente Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="73652-104">You can use command-line parameters to quick-start Lync 2013.</span></span> <span data-ttu-id="73652-105">Por ejemplo, si un usuario hace clic en un número de teléfono en otra aplicación, la aplicación puede iniciar una instancia de Lync 2013 e iniciar una llamada a ese número.</span><span class="sxs-lookup"><span data-stu-id="73652-105">For example, if a user clicks a phone number in another application, the application can start an instance of Lync 2013 and initiate a call to that number.</span></span>

<span data-ttu-id="73652-106">Lync 2013 también puede reconocer una lista delimitada por punto y coma de nombres de contacto para conferencias con varios participantes.</span><span class="sxs-lookup"><span data-stu-id="73652-106">Lync 2013 can also recognize a semicolon-delimited list of contact names for multiparty conferencing.</span></span>

<span data-ttu-id="73652-107">Si Lync 2013 está configurado para iniciar sesión automáticamente cuando se inicia, al iniciar Lync 2013 con parámetros de línea de comandos se abrirá la ventana principal de Lync.</span><span class="sxs-lookup"><span data-stu-id="73652-107">If Lync 2013 is configured to automatically sign in when started, then starting Lync 2013 with command-line parameters will open the Lync main window.</span></span> <span data-ttu-id="73652-108">Si Lync no está configurado para que inicie la sesión automáticamente al iniciarse, se abre la ventana de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="73652-108">If Lync is not configured to automatically sign in when started, the sign-in window opens.</span></span>

<span data-ttu-id="73652-109">En la tabla siguiente se muestran los parámetros disponibles.</span><span class="sxs-lookup"><span data-stu-id="73652-109">The following table shows the available parameters.</span></span>

### <a name="lync-2013-command-line-parameters"></a><span data-ttu-id="73652-110">Parámetros de línea de comandos de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="73652-110">Lync 2013 Command-Line Parameters</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73652-111">Extensión</span><span class="sxs-lookup"><span data-stu-id="73652-111">Extension</span></span></th>
<th><span data-ttu-id="73652-112">Formato de datos</span><span class="sxs-lookup"><span data-stu-id="73652-112">Format of Data</span></span></th>
<th><span data-ttu-id="73652-113">Action</span><span class="sxs-lookup"><span data-stu-id="73652-113">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73652-114">Tel</span><span class="sxs-lookup"><span data-stu-id="73652-114">tel:</span></span></p></td>
<td><p><span data-ttu-id="73652-115">URI de tel.</span><span class="sxs-lookup"><span data-stu-id="73652-115">tel URI</span></span></p></td>
<td><p><span data-ttu-id="73652-116">Abre la ventana Conversación para una llamada de audio pero no marca el número especificado.</span><span class="sxs-lookup"><span data-stu-id="73652-116">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73652-117">protocolos callto</span><span class="sxs-lookup"><span data-stu-id="73652-117">callto:</span></span></p></td>
<td><p><span data-ttu-id="73652-118">tel:, sip: o URL de tel que se puede editar</span><span class="sxs-lookup"><span data-stu-id="73652-118">tel:, sip:, or typeable tel URI</span></span></p></td>
<td><p><span data-ttu-id="73652-119">Abre la ventana Conversación para una llamada de audio pero no marca el número especificado.</span><span class="sxs-lookup"><span data-stu-id="73652-119">Opens the Conversation window for an audio call but does not dial the specified number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73652-120">SIP</span><span class="sxs-lookup"><span data-stu-id="73652-120">sip:</span></span></p></td>
<td><p><span data-ttu-id="73652-121">URI de SIP</span><span class="sxs-lookup"><span data-stu-id="73652-121">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="73652-122">Abra la ventana Conversación con el Identificador uniforme de recursos (URI) del SIP especificado en la lista de participantes.</span><span class="sxs-lookup"><span data-stu-id="73652-122">Opens the Conversation window with the specified SIP Uniform Resource Identifier (URI) in the participant list.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73652-123">Módulos</span><span class="sxs-lookup"><span data-stu-id="73652-123">Sips:</span></span></p></td>
<td><p><span data-ttu-id="73652-124">URI de SIP</span><span class="sxs-lookup"><span data-stu-id="73652-124">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="73652-125">Si Lync 2013 está configurado para usar el protocolo de seguridad de la capa de transporte (TLS), funciona exactamente igual que SIP:.</span><span class="sxs-lookup"><span data-stu-id="73652-125">If Lync 2013 is configured to use the Transport Layer Security (TLS) protocol, functions exactly like sip:.</span></span> <span data-ttu-id="73652-126">Si no está usando TLS, muestra un cuadro de diálogo para informar al usuario de que se requiere un alto nivel de seguridad.</span><span class="sxs-lookup"><span data-stu-id="73652-126">If TLS is not being used, displays a dialog box informing the user that a higher level of security is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73652-127">multipunto</span><span class="sxs-lookup"><span data-stu-id="73652-127">conf:</span></span></p></td>
<td><p><span data-ttu-id="73652-128">URI del SIP de la conferencia a la que se va a unir</span><span class="sxs-lookup"><span data-stu-id="73652-128">SIP URI of conference to join</span></span></p></td>
<td><p><span data-ttu-id="73652-p104">Si el URI es automático, crea instancias del foco y solo abre una vista de la lista. En caso contrario, abre una vista de la lista pero no envía INVITE.</span><span class="sxs-lookup"><span data-stu-id="73652-p104">If URI is self, instantiates the focus and brings up roster-only view. Otherwise, brings up roster view but does not send INVITE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73652-131">conversaciones</span><span class="sxs-lookup"><span data-stu-id="73652-131">im:</span></span></p></td>
<td><p><span data-ttu-id="73652-132">URI del SIP</span><span class="sxs-lookup"><span data-stu-id="73652-132">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="73652-133">Muestra la ventana Conversación solo de mensajería instantánea con el URI del SIP.</span><span class="sxs-lookup"><span data-stu-id="73652-133">Displays an instant messaging (IM)-only Conversation window with the SIP URI.</span></span> <span data-ttu-id="73652-134">Acepta varios URI de SIP especificados entre corchetes angulares (&lt;&gt;) sin ningún separador.</span><span class="sxs-lookup"><span data-stu-id="73652-134">Accepts multiple SIP URIs specified inside angle brackets (&lt;&gt;) without any separator.</span></span></p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


<span data-ttu-id="73652-135">En la tabla siguiente se proporcionan ejemplos de estos parámetros de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="73652-135">The following table provides examples of these command-line parameters.</span></span>

### <a name="command-line-parameter-examples"></a><span data-ttu-id="73652-136">Ejemplos de parámetros de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="73652-136">Command-Line Parameter Examples</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73652-137">Instancia</span><span class="sxs-lookup"><span data-stu-id="73652-137">Instance</span></span></th>
<th><span data-ttu-id="73652-138">Resultados</span><span class="sxs-lookup"><span data-stu-id="73652-138">Results</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73652-139">Tel: + 14255550101</span><span class="sxs-lookup"><span data-stu-id="73652-139">Tel:+14255550101</span></span></p></td>
<td><p><span data-ttu-id="73652-140">Abre una vista de solo teléfonos con +14255550101.</span><span class="sxs-lookup"><span data-stu-id="73652-140">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73652-141">Callto:tel:+ 14255550101</span><span class="sxs-lookup"><span data-stu-id="73652-141">Callto:tel:+ 14255550101</span></span></p></td>
<td><p><span data-ttu-id="73652-142">Abre una vista de solo teléfonos con +14255550101.</span><span class="sxs-lookup"><span data-stu-id="73652-142">Opens a phone-only view with +14255550101.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73652-143">Callto:sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="73652-143">Callto:sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="73652-144">Abre una vista de solo teléfonos con kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="73652-144">Opens a phone-only view with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73652-145">sip:kazuto@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="73652-145">sip:kazuto@litwareinc.com</span></span></p></td>
<td><p><span data-ttu-id="73652-146">Abre una ventana Conversación con kazuto@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="73652-146">Opens a Conversation window with kazuto@litwareinc.com.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73652-147">conf: SIP:https://meet.contoso.com/kazuto/7322994</span><span class="sxs-lookup"><span data-stu-id="73652-147">conf:sip:https://meet.contoso.com/kazuto/7322994</span></span></p></td>
<td><p><span data-ttu-id="73652-148">Abre una ventana de conversación y muestra las opciones de unión de audio de la reunión.</span><span class="sxs-lookup"><span data-stu-id="73652-148">Opens a Conversation window and displays meeting audio join options.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

