---
title: 'Lync Server 2013: registros de uso de RTC'
description: 'Lync Server 2013: registros de uso de RTC.'
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
ms.openlocfilehash: 0f8ff428dc2fa5cf8cf0f10e37f0f79c38d70d70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565586"
---
# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="2c6f7-103">Registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c6f7-103">PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c6f7-104">_**Última modificación del tema:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="2c6f7-104">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="2c6f7-105">La planeación de los registros de uso de RTC consiste principalmente en enumerar todos los permisos de llamada que hay actualmente en vigor en la organización, desde el CEO hasta trabajadores temporales, consultores y personal contingente.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-105">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff.</span></span> <span data-ttu-id="2c6f7-106">Este proceso también ofrece la oportunidad de volver a examinar los permisos de llamada existentes y revisarlos.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-106">This process also provides an opportunity to reexamine existing call permissions and revise them.</span></span> <span data-ttu-id="2c6f7-107">Puede crear registros de uso de RTC solo para los permisos de llamada que se aplican a los usuarios de telefonía IP empresarial previstos, pero una mejor solución de larga duración podría ser crear registros de uso de RTC para todos los permisos de llamadas, independientemente de si algunos usuarios no se aplican actualmente al grupo de usuarios para que estén habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-107">You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice.</span></span> <span data-ttu-id="2c6f7-108">Si los permisos de llamada cambian o se agregan nuevos usuarios con permisos de llamada diferentes, ya habrá creado los registros de uso de RTC necesarios.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-108">If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="2c6f7-109">En la tabla siguiente se muestra una tabla típica de uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-109">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="2c6f7-110">Registros de uso de RTC</span><span class="sxs-lookup"><span data-stu-id="2c6f7-110">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2c6f7-111">Atributo de teléfono</span><span class="sxs-lookup"><span data-stu-id="2c6f7-111">Phone attribute</span></span></th>
<th><span data-ttu-id="2c6f7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c6f7-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2c6f7-113">Local</span><span class="sxs-lookup"><span data-stu-id="2c6f7-113">Local</span></span></p></td>
<td><p><span data-ttu-id="2c6f7-114">Llamadas locales</span><span class="sxs-lookup"><span data-stu-id="2c6f7-114">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c6f7-115">Long-Distance</span><span class="sxs-lookup"><span data-stu-id="2c6f7-115">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="2c6f7-116">Llamadas de larga distancia</span><span class="sxs-lookup"><span data-stu-id="2c6f7-116">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c6f7-117">International</span><span class="sxs-lookup"><span data-stu-id="2c6f7-117">International</span></span></p></td>
<td><p><span data-ttu-id="2c6f7-118">Llamadas internacionales</span><span class="sxs-lookup"><span data-stu-id="2c6f7-118">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c6f7-119">Delhi</span><span class="sxs-lookup"><span data-stu-id="2c6f7-119">Delhi</span></span></p></td>
<td><p><span data-ttu-id="2c6f7-120">Empleados de jornada completa de Delhi</span><span class="sxs-lookup"><span data-stu-id="2c6f7-120">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c6f7-121">Redmond</span><span class="sxs-lookup"><span data-stu-id="2c6f7-121">Redmond</span></span></p></td>
<td><p><span data-ttu-id="2c6f7-122">Empleados de jornada completa de Redmond</span><span class="sxs-lookup"><span data-stu-id="2c6f7-122">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2c6f7-123">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="2c6f7-123">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="2c6f7-124">Empleados temporales de Redmond</span><span class="sxs-lookup"><span data-stu-id="2c6f7-124">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2c6f7-125">Zúrich</span><span class="sxs-lookup"><span data-stu-id="2c6f7-125">Zurich</span></span></p></td>
<td><p><span data-ttu-id="2c6f7-126">Zurich empleados a tiempo completo</span><span class="sxs-lookup"><span data-stu-id="2c6f7-126">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2c6f7-127">Por sí mismos, los registros de uso de RTC no hacen nada.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-127">By themselves, PSTN usage records do not do anything.</span></span> <span data-ttu-id="2c6f7-128">Para que funcionen, debe asociarlos con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c6f7-128">For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="2c6f7-129">Directivas de voz, que se asignan a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-129">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="2c6f7-130">Rutas, que se asignan a números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="2c6f7-130">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="2c6f7-131">Para obtener más información sobre las rutas y directivas de voz, consulte [directivas de voz en Lync server 2013](lync-server-2013-voice-policies.md) y [rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="2c6f7-131">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="2c6f7-132">Para obtener más información sobre cómo crear y configurar estas rutas de voz, consulte [Configuring Voice Routes for Outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="2c6f7-132">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

