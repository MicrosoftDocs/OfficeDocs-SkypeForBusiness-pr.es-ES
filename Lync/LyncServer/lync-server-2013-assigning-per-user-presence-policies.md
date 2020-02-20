---
title: 'Lync Server 2013: asignación de directivas de presencia por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4ae464e37c7d4061c9a7311d7df427b7a66db1c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a><span data-ttu-id="bb8bc-102">Asignación de directivas de presencia por usuario en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb8bc-102">Assigning per-user presence policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb8bc-103">_**Última modificación del tema:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="bb8bc-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="bb8bc-104">Una directiva de presencia es un conjunto de límites y restricciones que afectan a la presencia.</span><span class="sxs-lookup"><span data-stu-id="bb8bc-104">A presence policy is a set of limits and restrictions that affect presence.</span></span> <span data-ttu-id="bb8bc-105">En la tabla siguiente se describe la configuración de la Directiva de presencia disponible en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb8bc-105">The following table describes the presence policy settings available in Lync Server 2013.</span></span>

### <a name="presence-policy-settings"></a><span data-ttu-id="bb8bc-106">Configuración de directivas de presencia</span><span class="sxs-lookup"><span data-stu-id="bb8bc-106">Presence Policy Settings</span></span>

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
<th><span data-ttu-id="bb8bc-107">Nombre XML</span><span class="sxs-lookup"><span data-stu-id="bb8bc-107">XML name</span></span></th>
<th><span data-ttu-id="bb8bc-108">Nombre para mostrar</span><span class="sxs-lookup"><span data-stu-id="bb8bc-108">Display name</span></span></th>
<th><span data-ttu-id="bb8bc-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb8bc-109">Description</span></span></th>
<th><span data-ttu-id="bb8bc-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="bb8bc-110">Type</span></span></th>
<th><span data-ttu-id="bb8bc-111">Valor</span><span class="sxs-lookup"><span data-stu-id="bb8bc-111">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb8bc-112">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="bb8bc-112">CategorySubscriptions</span></span></p></td>
<td><p><span data-ttu-id="bb8bc-113">Número máximo de suscripciones a categorías de suscriptores</span><span class="sxs-lookup"><span data-stu-id="bb8bc-113">Maximum Number of Subscriber Category Subscriptions</span></span></p></td>
<td><p><span data-ttu-id="bb8bc-p102">Limita el número de suscripciones a categorías de suscriptores. Por ejemplo, cuando Communicator se suscribe a la presencia de un usuario, obtiene una suscripción de categoría por cada categoría de tarjeta de contacto, datos de calendario, notas, servicios y estado.</span><span class="sxs-lookup"><span data-stu-id="bb8bc-p102">Limits the number of subscriber category subscriptions. For example, when Communicator subscribes to a user’s presence, it obtains a category subscription for each of the contact card, calendar data, notes, services, and state categories.</span></span></p>
<p><span data-ttu-id="bb8bc-116">Si el valor es 0, significa que no se puede suscribir al objeto de contacto o usuario.</span><span class="sxs-lookup"><span data-stu-id="bb8bc-116">A setting of 0 means that the user or contact object cannot be subscribed to by others.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bb8bc-117">Esta configuración puede influir en gran medida en el rendimiento si se configura con un número alto y cada usuario suele tener una gran cantidad de usuarios suscritos a su presencia.</span><span class="sxs-lookup"><span data-stu-id="bb8bc-117">This setting can have a significant impact on performance if it is set to a high number, and the average user has a large number of users subscribing to his or her presence.</span></span>


</div></td>
<td><p><span data-ttu-id="bb8bc-118">Entero</span><span class="sxs-lookup"><span data-stu-id="bb8bc-118">Integer</span></span></p></td>
<td><p><span data-ttu-id="bb8bc-119">0-3000</span><span class="sxs-lookup"><span data-stu-id="bb8bc-119">0-3000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb8bc-120">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="bb8bc-120">PromptedSubscribers</span></span></p></td>
<td><p><span data-ttu-id="bb8bc-121">Número máximo de alertas de suscripción de presencia en la cola</span><span class="sxs-lookup"><span data-stu-id="bb8bc-121">Maximum Number of Queued Presence Subscription Alerts</span></span></p></td>
<td><p><span data-ttu-id="bb8bc-p103">Limita el número de entradas de la tabla de suscriptores avisados. Esta configuración determina la cantidad máxima de avisos que se pueden colocar en la cola de un usuario determinado. Por ejemplo, cuando el usuario A se suscribe a la presencia del usuario B, el usuario B recibe un aviso de que el usuario A se ha suscrito al usuario B, y un aviso de reconocimiento se crea en la tabla de suscriptores avisados del usuario B. Cuando el usuario B acepta, o reconoce, la suscripción, el aviso de reconocimiento se quita de la tabla de suscriptores avisados del usuario B.</span><span class="sxs-lookup"><span data-stu-id="bb8bc-p103">Limits the number of entries in the prompted subscribers table. This setting determines the maximum number of prompts that can be queued for a given user. For example, when user A subscribes to user B’s presence, user B receives a prompt that user A is now subscribed to user B, and an acknowledgement prompt is created in user B’s prompted subscribers table. After user B accepts, or acknowledges, the subscription, the acknowledgement prompt is removed from user B’s prompted subscribers table.</span></span></p>
<p><span data-ttu-id="bb8bc-126">Si el valor es 0, significa que no se avisará al usuario cuando alguien se suscriba a su presencia.</span><span class="sxs-lookup"><span data-stu-id="bb8bc-126">A setting of 0 means that the user is not prompted when someone subscribes to his or her presence.</span></span></p></td>
<td><p><span data-ttu-id="bb8bc-127">Entero o token</span><span class="sxs-lookup"><span data-stu-id="bb8bc-127">Integer or Token</span></span></p></td>
<td><p><span data-ttu-id="bb8bc-128">0-500</span><span class="sxs-lookup"><span data-stu-id="bb8bc-128">0-500</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bb8bc-129">De forma predeterminada, la **Directiva** y el servicio predeterminado: las directivas de presencia **mediana** se instalan al implementar Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb8bc-129">By default, the **Default Policy** and **Service: Medium** presence policies are installed when you deploy Lync Server.</span></span> <span data-ttu-id="bb8bc-130">En la siguiente tabla se describe la configuración concreta de estas dos directivas de presencia.</span><span class="sxs-lookup"><span data-stu-id="bb8bc-130">The following table describes the specific settings of the two presence policies.</span></span>

### <a name="presence-policies"></a><span data-ttu-id="bb8bc-131">Directivas de presencia</span><span class="sxs-lookup"><span data-stu-id="bb8bc-131">Presence Policies</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb8bc-132">Nombre de directiva</span><span class="sxs-lookup"><span data-stu-id="bb8bc-132">Policy name</span></span></th>
<th><span data-ttu-id="bb8bc-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb8bc-133">Description</span></span></th>
<th><span data-ttu-id="bb8bc-134">CategorySubscriptions</span><span class="sxs-lookup"><span data-stu-id="bb8bc-134">CategorySubscriptions</span></span></th>
<th><span data-ttu-id="bb8bc-135">PromptedSubscribers</span><span class="sxs-lookup"><span data-stu-id="bb8bc-135">PromptedSubscribers</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb8bc-136">Directiva predeterminada</span><span class="sxs-lookup"><span data-stu-id="bb8bc-136">Default Policy</span></span></p></td>
<td><p><span data-ttu-id="bb8bc-p105">Directiva para usuarios normales. Es la directiva de presencia predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bb8bc-p105">Policy for typical users. This is the default presence policy.</span></span></p></td>
<td><p><span data-ttu-id="bb8bc-139">1000</span><span class="sxs-lookup"><span data-stu-id="bb8bc-139">1000</span></span></p></td>
<td><p><span data-ttu-id="bb8bc-140">200</span><span class="sxs-lookup"><span data-stu-id="bb8bc-140">200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb8bc-141">Service: Medium</span><span class="sxs-lookup"><span data-stu-id="bb8bc-141">Service: Medium</span></span></p></td>
<td><p><span data-ttu-id="bb8bc-142">Directiva para las aplicaciones que requieren la suscripción de más usuarios a la presencia del objeto.</span><span class="sxs-lookup"><span data-stu-id="bb8bc-142">Policy for applications that require more users to subscribe to the object’s presence.</span></span></p></td>
<td><p><span data-ttu-id="bb8bc-143">1000</span><span class="sxs-lookup"><span data-stu-id="bb8bc-143">1000</span></span></p></td>
<td><p><span data-ttu-id="bb8bc-144">comprendi</span><span class="sxs-lookup"><span data-stu-id="bb8bc-144">0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

