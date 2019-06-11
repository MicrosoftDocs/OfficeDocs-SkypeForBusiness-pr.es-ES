---
title: 'Lync Server 2013: asignación de directivas de presencia por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 905065e231869b4b6075fc1894e51c91df8f0aee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="d1b94-102">Asignar directivas de presencia por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1b94-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1b94-103">_**Última modificación del tema:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="d1b94-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="d1b94-104">Una directiva de presencia es un conjunto de límites y restricciones que afectan a la presencia.</span><span class="sxs-lookup"><span data-stu-id="d1b94-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="d1b94-105">La siguiente tabla describe la configuración de la Directiva de presencia disponible en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1b94-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="d1b94-106">Configuración de la Directiva de presencia</span><span class="sxs-lookup"><span data-stu-id="d1b94-106">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="d1b94-107">Nombre XML</span><span class="sxs-lookup"><span data-stu-id="d1b94-107">XML name</span></span></th>
<th><span data-ttu-id="d1b94-108">Nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="d1b94-108">Display name</span></span></th>
<th><span data-ttu-id="d1b94-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1b94-109">Description</span></span></th>
<th><span data-ttu-id="d1b94-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="d1b94-110">Type</span></span></th>
<th><span data-ttu-id="d1b94-111">Valor</span><span class="sxs-lookup"><span data-stu-id="d1b94-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1b94-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="d1b94-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="d1b94-113">Número máximo de suscripciones de categorías de suscriptores</span><span class="sxs-lookup"><span data-stu-id="d1b94-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="d1b94-114">Limita la cantidad de suscripciones de categorías de abonados.</span><span class="sxs-lookup"><span data-stu-id="d1b94-114">Limits the number of subscriber category subscriptions.</span></span> <span data-ttu-id="d1b94-115">Por ejemplo, cuando Communicator se suscribe a la presencia de un usuario, obtiene una suscripción de categoría para cada una de las categorías de tarjeta de contacto, datos de calendario, notas, servicios y estado.</span><span class="sxs-lookup"><span data-stu-id="d1b94-115">For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="d1b94-116">El valor 0 significa que otros usuarios no pueden suscribirse al objeto de usuario o contacto.</span><span class="sxs-lookup"><span data-stu-id="d1b94-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d1b94-117">Esta configuración puede tener un impacto significativo en el rendimiento si se establece en un número alto y el usuario promedio tiene un gran número de usuarios que se suscriben a su presencia.</span><span class="sxs-lookup"><span data-stu-id="d1b94-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="d1b94-118">Entero</span><span class="sxs-lookup"><span data-stu-id="d1b94-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="d1b94-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="d1b94-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1b94-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="d1b94-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="d1b94-121">Número máximo de alertas de suscripción de presencia en cola</span><span class="sxs-lookup"><span data-stu-id="d1b94-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="d1b94-122">Limita el número de entradas de la tabla suscriptores solicitada.</span><span class="sxs-lookup"><span data-stu-id="d1b94-122">Limits the number of entries in the prompted subscribers table.</span></span> <span data-ttu-id="d1b94-123">Esta configuración determina el número máximo de mensajes que se pueden poner en cola para un usuario dado.</span><span class="sxs-lookup"><span data-stu-id="d1b94-123">This setting determines the maximum number of prompts that can be queued for a given user.</span></span> <span data-ttu-id="d1b94-124">Por ejemplo, cuando el usuario se suscribe a la presencia del usuario B, recibe un mensaje que indica que el usuario A ya está suscrito al usuario B y se crea un mensaje de confirmación en la tabla de suscriptores solicitada por el usuario B.</span><span class="sxs-lookup"><span data-stu-id="d1b94-124">For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table.</span></span> <span data-ttu-id="d1b94-125">Después de que el usuario B acepte o confirme la suscripción, se eliminará la solicitud de confirmación de la tabla de suscriptores solicitada por el usuario B.</span><span class="sxs-lookup"><span data-stu-id="d1b94-125">After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="d1b94-126">Un valor de 0 significa que no se le pide confirmación al usuario cuando alguien se suscribe a su presencia.</span><span class="sxs-lookup"><span data-stu-id="d1b94-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="d1b94-127">Entero o token</span><span class="sxs-lookup"><span data-stu-id="d1b94-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="d1b94-128">0-500</span><span class="sxs-lookup"><span data-stu-id="d1b94-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d1b94-129">De forma predeterminada, la **Directiva** y el servicio predeterminados: las directivas de presencia **media** se instalan al implementar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d1b94-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="d1b94-130">En la siguiente tabla se describen las opciones específicas de las dos directivas de presencia.</span><span class="sxs-lookup"><span data-stu-id="d1b94-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="d1b94-131">Directivas de presencia</span><span class="sxs-lookup"><span data-stu-id="d1b94-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1b94-132">Nombre de la directiva</span><span class="sxs-lookup"><span data-stu-id="d1b94-132">Policy name</span></span></th>
<th><span data-ttu-id="d1b94-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1b94-133">Description</span></span></th>
<th><span data-ttu-id="d1b94-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="d1b94-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="d1b94-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="d1b94-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1b94-136">Directiva predeterminada</span><span class="sxs-lookup"><span data-stu-id="d1b94-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="d1b94-137">Directiva para usuarios típicos.</span><span class="sxs-lookup"><span data-stu-id="d1b94-137">Policy for typical users.</span></span> <span data-ttu-id="d1b94-138">Esta es la Directiva de presencia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d1b94-138">This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="d1b94-139">1000</span><span class="sxs-lookup"><span data-stu-id="d1b94-139">1000</span></span></p></td>
<td><p><span data-ttu-id="d1b94-140">200</span><span class="sxs-lookup"><span data-stu-id="d1b94-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1b94-141">Servicio: medio</span><span class="sxs-lookup"><span data-stu-id="d1b94-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="d1b94-142">Directiva para las aplicaciones que requieren más usuarios para suscribirse a la presencia del objeto.</span><span class="sxs-lookup"><span data-stu-id="d1b94-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="d1b94-143">1000</span><span class="sxs-lookup"><span data-stu-id="d1b94-143">1000</span></span></p></td>
<td><p><span data-ttu-id="d1b94-144">,0</span><span class="sxs-lookup"><span data-stu-id="d1b94-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

