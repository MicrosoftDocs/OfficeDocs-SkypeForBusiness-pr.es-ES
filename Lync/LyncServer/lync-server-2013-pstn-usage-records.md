---
title: 'Lync Server 2013: Registros de uso de RTC'
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
ms.openlocfilehash: 5909494b4e4b6901964a7642481302ca221fe086
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="5182f-102">Registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5182f-102">PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5182f-103">_**Última modificación del tema:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="5182f-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="5182f-104">Planificar los registros de uso de RTC consiste principalmente en elaborar una lista de todos los permisos de llamada vigentes actualmente en la organización, desde los permisos del presidente hasta los de los empleados temporales, consultores y personal contingente.</span><span class="sxs-lookup"><span data-stu-id="5182f-104">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff.</span></span> <span data-ttu-id="5182f-105">Este proceso también brinda la oportunidad de volver a examinar los permisos de llamada existentes y modificarlos.</span><span class="sxs-lookup"><span data-stu-id="5182f-105">This process also provides an opportunity to reexamine existing call permissions and revise them.</span></span> <span data-ttu-id="5182f-106">Puede crear registros de uso de RTC solo para los permisos de llamada que se aplican a los usuarios de voz de empresa previstos, pero una mejor solución de larga duración podría ser crear registros de uso de RTC para todos los permisos de llamadas, independientemente de si algunos usuarios no pueden aplicar al grupo de usuarios que desea habilitar para la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="5182f-106">You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice.</span></span> <span data-ttu-id="5182f-107">Si cambian los permisos de llamada o se agregan usuarios nuevos con permisos de llamada diferentes, ya estarán creados los registros de uso de RTC necesarios.</span><span class="sxs-lookup"><span data-stu-id="5182f-107">If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="5182f-108">A continuación se muestra una tabla del uso de RTC típico.</span><span class="sxs-lookup"><span data-stu-id="5182f-108">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="5182f-109">Registros de uso de RTC</span><span class="sxs-lookup"><span data-stu-id="5182f-109">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5182f-110">Atributo de teléfono</span><span class="sxs-lookup"><span data-stu-id="5182f-110">Phone attribute</span></span></th>
<th><span data-ttu-id="5182f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="5182f-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5182f-112">Local</span><span class="sxs-lookup"><span data-stu-id="5182f-112">Local</span></span></p></td>
<td><p><span data-ttu-id="5182f-113">Llamadas locales</span><span class="sxs-lookup"><span data-stu-id="5182f-113">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5182f-114">Long-Distance</span><span class="sxs-lookup"><span data-stu-id="5182f-114">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="5182f-115">Llamadas de larga distancia</span><span class="sxs-lookup"><span data-stu-id="5182f-115">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5182f-116">International</span><span class="sxs-lookup"><span data-stu-id="5182f-116">International</span></span></p></td>
<td><p><span data-ttu-id="5182f-117">Llamadas internacionales</span><span class="sxs-lookup"><span data-stu-id="5182f-117">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5182f-118">Delhi</span><span class="sxs-lookup"><span data-stu-id="5182f-118">Delhi</span></span></p></td>
<td><p><span data-ttu-id="5182f-119">Empleados de jornada completa de Delhi</span><span class="sxs-lookup"><span data-stu-id="5182f-119">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5182f-120">Redmond</span><span class="sxs-lookup"><span data-stu-id="5182f-120">Redmond</span></span></p></td>
<td><p><span data-ttu-id="5182f-121">Empleados de jornada completa de Redmond</span><span class="sxs-lookup"><span data-stu-id="5182f-121">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5182f-122">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="5182f-122">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="5182f-123">Empleados temporales de Redmond</span><span class="sxs-lookup"><span data-stu-id="5182f-123">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5182f-124">Zurich</span><span class="sxs-lookup"><span data-stu-id="5182f-124">Zurich</span></span></p></td>
<td><p><span data-ttu-id="5182f-125">Empleados de jornada completa de Zúrich</span><span class="sxs-lookup"><span data-stu-id="5182f-125">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5182f-p102">Por sí mismos, los registros de uso de RTC no hacen nada. Para que funcionen, hay que asociarlos a:</span><span class="sxs-lookup"><span data-stu-id="5182f-p102">By themselves, PSTN usage records do not do anything. For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="5182f-128">Directivas de voz, que se asignan a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5182f-128">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="5182f-129">Rutas, que se asignan a los números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="5182f-129">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="5182f-130">Para obtener más información sobre las rutas y directivas de voz, vea [directivas de voz en Lync server 2013](lync-server-2013-voice-policies.md) y [rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="5182f-130">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="5182f-131">Para obtener más información sobre cómo crear y configurar estos, vea [configurar rutas de voz para llamadas salientes en Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="5182f-131">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

