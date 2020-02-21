---
title: 'Lync Server 2013: registros de uso de RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81f459c7ae6b581dedc5843fd2a89568a2f755a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="f565d-102">Registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f565d-102">PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f565d-103">_**Última modificación del tema:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="f565d-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="f565d-104">La planeación de los registros de uso de RTC consiste principalmente en enumerar todos los permisos de llamada que hay actualmente en vigor en la organización, desde el CEO hasta trabajadores temporales, consultores y personal contingente.</span><span class="sxs-lookup"><span data-stu-id="f565d-104">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff.</span></span> <span data-ttu-id="f565d-105">Este proceso también ofrece la oportunidad de volver a examinar los permisos de llamada existentes y revisarlos.</span><span class="sxs-lookup"><span data-stu-id="f565d-105">This process also provides an opportunity to reexamine existing call permissions and revise them.</span></span> <span data-ttu-id="f565d-106">Puede crear registros de uso de RTC solo para los permisos de llamada que se aplican a los usuarios de voz de empresa que se prevén, pero una mejor solución de largo alcance puede ser crear registros de uso de RTC para todos los permisos de llamadas, independientemente de si algunos no se encuentran se aplican al grupo de usuarios que se van a habilitar para la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="f565d-106">You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice.</span></span> <span data-ttu-id="f565d-107">Si los permisos de llamada cambian o se agregan nuevos usuarios con permisos de llamada diferentes, ya habrá creado los registros de uso de RTC necesarios.</span><span class="sxs-lookup"><span data-stu-id="f565d-107">If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="f565d-108">En la tabla siguiente se muestra una tabla típica de uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="f565d-108">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="f565d-109">Registros de uso de RTC</span><span class="sxs-lookup"><span data-stu-id="f565d-109">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f565d-110">Atributo de teléfono</span><span class="sxs-lookup"><span data-stu-id="f565d-110">Phone attribute</span></span></th>
<th><span data-ttu-id="f565d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="f565d-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f565d-112">Local</span><span class="sxs-lookup"><span data-stu-id="f565d-112">Local</span></span></p></td>
<td><p><span data-ttu-id="f565d-113">Llamadas locales</span><span class="sxs-lookup"><span data-stu-id="f565d-113">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f565d-114">A larga distancia</span><span class="sxs-lookup"><span data-stu-id="f565d-114">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="f565d-115">Llamadas de larga distancia</span><span class="sxs-lookup"><span data-stu-id="f565d-115">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f565d-116">International</span><span class="sxs-lookup"><span data-stu-id="f565d-116">International</span></span></p></td>
<td><p><span data-ttu-id="f565d-117">Llamadas internacionales</span><span class="sxs-lookup"><span data-stu-id="f565d-117">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f565d-118">Delhi</span><span class="sxs-lookup"><span data-stu-id="f565d-118">Delhi</span></span></p></td>
<td><p><span data-ttu-id="f565d-119">Empleados de jornada completa de Delhi</span><span class="sxs-lookup"><span data-stu-id="f565d-119">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f565d-120">Redmond</span><span class="sxs-lookup"><span data-stu-id="f565d-120">Redmond</span></span></p></td>
<td><p><span data-ttu-id="f565d-121">Empleados de jornada completa de Redmond</span><span class="sxs-lookup"><span data-stu-id="f565d-121">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f565d-122">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="f565d-122">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="f565d-123">Empleados temporales de Redmond</span><span class="sxs-lookup"><span data-stu-id="f565d-123">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f565d-124">Zúrich</span><span class="sxs-lookup"><span data-stu-id="f565d-124">Zurich</span></span></p></td>
<td><p><span data-ttu-id="f565d-125">Zurich empleados a tiempo completo</span><span class="sxs-lookup"><span data-stu-id="f565d-125">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f565d-126">Por sí mismos, los registros de uso de RTC no hacen nada.</span><span class="sxs-lookup"><span data-stu-id="f565d-126">By themselves, PSTN usage records do not do anything.</span></span> <span data-ttu-id="f565d-127">Para que funcionen, debe asociarlos con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f565d-127">For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="f565d-128">Directivas de voz, que se asignan a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f565d-128">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="f565d-129">Rutas, que se asignan a números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="f565d-129">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="f565d-130">Para obtener más información sobre las rutas y directivas de voz, consulte [directivas de voz en Lync server 2013](lync-server-2013-voice-policies.md) y [rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="f565d-130">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="f565d-131">Para obtener más información sobre cómo crear y configurar estas rutas de voz, consulte [Configuring Voice Routes for Outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="f565d-131">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

