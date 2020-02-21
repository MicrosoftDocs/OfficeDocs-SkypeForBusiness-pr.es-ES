---
title: 'Lync Server 2013: Planeación de la capacidad para la recogida de llamadas de grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0fa12b04507e5b42767d551af4b4b9c004175b4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="fa81b-102">Planeación de la capacidad para la recogida de llamadas grupales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa81b-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa81b-103">_**Última modificación del tema:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="fa81b-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="fa81b-104">En la tabla siguiente se describe el modelo de usuario de llamada de grupo que puede usar como base para los requisitos de planeación de capacidad.</span><span class="sxs-lookup"><span data-stu-id="fa81b-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fa81b-105">La recogida de llamadas de grupo se basa en la aplicación de estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fa81b-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="fa81b-106">Tenga en cuenta que, para la planeación de la capacidad de recuperación ante desastres, cada grupo de servidores emparejados debe poder administrar las cargas de trabajo para los servicios de estacionamiento de llamadas, incluida la atención de llamadas grupales, en ambos grupos.</span><span class="sxs-lookup"><span data-stu-id="fa81b-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="fa81b-107">Modelo de usuario de llamada de grupo</span><span class="sxs-lookup"><span data-stu-id="fa81b-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa81b-108">Biometría</span><span class="sxs-lookup"><span data-stu-id="fa81b-108">Metric</span></span></th>
<th><span data-ttu-id="fa81b-109">Por grupo de servidores front-end (con 8 servidores front-end)</span><span class="sxs-lookup"><span data-stu-id="fa81b-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="fa81b-110">Por servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="fa81b-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa81b-111">Número recomendado de usuarios por grupo</span><span class="sxs-lookup"><span data-stu-id="fa81b-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="fa81b-112">50</span><span class="sxs-lookup"><span data-stu-id="fa81b-112">50</span></span></p></td>
<td><p><span data-ttu-id="fa81b-113">50</span><span class="sxs-lookup"><span data-stu-id="fa81b-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa81b-114">Número de grupos recomendados</span><span class="sxs-lookup"><span data-stu-id="fa81b-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="fa81b-115">500</span><span class="sxs-lookup"><span data-stu-id="fa81b-115">500</span></span></p></td>
<td><p><span data-ttu-id="fa81b-116">60</span><span class="sxs-lookup"><span data-stu-id="fa81b-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa81b-117">Número máximo de usuarios por grupo de servidores habilitados para la recogida de llamadas de grupo</span><span class="sxs-lookup"><span data-stu-id="fa81b-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="fa81b-118">25 000</span><span class="sxs-lookup"><span data-stu-id="fa81b-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="fa81b-119">3,000</span><span class="sxs-lookup"><span data-stu-id="fa81b-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa81b-120">Tasa máxima de llamadas entrantes a los usuarios totales habilitados para la atención de llamadas grupales por grupo por minuto</span><span class="sxs-lookup"><span data-stu-id="fa81b-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="fa81b-121">500</span><span class="sxs-lookup"><span data-stu-id="fa81b-121">500</span></span></p></td>
<td><p><span data-ttu-id="fa81b-122">60</span><span class="sxs-lookup"><span data-stu-id="fa81b-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa81b-123">Tasa máxima de llamadas recuperadas por los usuarios con la atención de llamadas grupales por grupo por minuto</span><span class="sxs-lookup"><span data-stu-id="fa81b-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="fa81b-124">200</span><span class="sxs-lookup"><span data-stu-id="fa81b-124">200</span></span></p></td>
<td><p><span data-ttu-id="fa81b-125">IVA</span><span class="sxs-lookup"><span data-stu-id="fa81b-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="fa81b-126">Para los grupos de servidores front-end que tienen menos de ocho servidores front-end, calcule las métricas linealmente.</span><span class="sxs-lookup"><span data-stu-id="fa81b-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="fa81b-127">Por ejemplo, si el grupo de servidores front-end tiene un servidor front-end, calcule la carga máxima como 1/8 de los valores que se muestran en la tabla.</span><span class="sxs-lookup"><span data-stu-id="fa81b-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="fa81b-128">Puede aumentar o disminuir el número recomendado de usuarios por grupo y el número de grupos siempre que no supere el número máximo de usuarios por grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="fa81b-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="fa81b-129">Por ejemplo, el servidor Standard Edition puede tener 120 grupos con 25 usuarios por grupo, ya que el número de usuarios habilitados para la atención de llamadas grupales está todavía dentro del modelo de usuario máximo (es decir, 120 grupos de 25 usuarios es 3.000 usuarios habilitados para la atención de llamadas grupales).</span><span class="sxs-lookup"><span data-stu-id="fa81b-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

