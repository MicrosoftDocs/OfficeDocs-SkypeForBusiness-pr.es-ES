---
title: 'Lync Server 2013: comprobar el entorno físico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8838e5d3dfd1e3590f7988102f187c49114fc233
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="e0806-102">Realización de comprobaciones ambientales físicas</span><span class="sxs-lookup"><span data-stu-id="e0806-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0806-103">_**Última modificación del tema:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="e0806-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="e0806-104">Antes de comprobar el rendimiento, la disponibilidad y la funcionalidad de la implementación de Lync Server 2013, debe comprobar el entorno físico.</span><span class="sxs-lookup"><span data-stu-id="e0806-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="e0806-105">Por ejemplo, es posible que sea necesario reducir la temperatura de la sala de servidores o que sea necesario reemplazar un cable de red.</span><span class="sxs-lookup"><span data-stu-id="e0806-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="e0806-106">Para obtener los mejores resultados, lleve a cabo las siguientes inspecciones ambientales físicas:</span><span class="sxs-lookup"><span data-stu-id="e0806-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="e0806-107">**Medidas de seguridad física**   la protección de seguridad física como, por ejemplo, bloqueos, puertas y salas de acceso restringido.</span><span class="sxs-lookup"><span data-stu-id="e0806-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="e0806-108">Compruebe si hay entradas forzadas y no autorizadas y signos de daños en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e0806-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="e0806-109">**La temperatura y la humedad**   elevada temperatura, un flujo de aire deficiente y la humedad pueden provocar el sobrecalentamiento de los componentes de hardware.</span><span class="sxs-lookup"><span data-stu-id="e0806-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="e0806-110">Compruebe la temperatura y la humedad para asegurarse de que los sistemas ambientales, tales como calefacción y aire acondicionado pueden mantener condiciones aceptables y funcionar dentro de las especificaciones del fabricante del hardware.</span><span class="sxs-lookup"><span data-stu-id="e0806-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="e0806-111">Cuando haya instalado recientemente un nuevo equipo, compruebe que el flujo de aire a y desde los servidores no se haya impedimento y cumpla con las especificaciones del fabricante.</span><span class="sxs-lookup"><span data-stu-id="e0806-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="e0806-112">**Dispositivos y componentes**   la organización de Lync Server 2013 se basa en una red física en funcionamiento y en hardware relacionado.</span><span class="sxs-lookup"><span data-stu-id="e0806-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="e0806-113">Asegúrese de que los enrutadores, conmutadores, concentradores, cables físicos y conectores estén operativos.</span><span class="sxs-lookup"><span data-stu-id="e0806-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="e0806-114">Las características específicas sobre cómo realizar estas comprobaciones dependerán en gran medida del sitio de instalación y del hardware de servidor que se haya elegido.</span><span class="sxs-lookup"><span data-stu-id="e0806-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="e0806-115">La primera vez que realice esta comprobación, consulte la documentación del hardware y anote los parámetros deseados para futuras referencias.</span><span class="sxs-lookup"><span data-stu-id="e0806-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="e0806-116">Entorno de espacio de servidor deseado</span><span class="sxs-lookup"><span data-stu-id="e0806-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0806-117">Parámetro</span><span class="sxs-lookup"><span data-stu-id="e0806-117">Parameter</span></span></th>
<th><span data-ttu-id="e0806-118">Intervalo o valor deseado</span><span class="sxs-lookup"><span data-stu-id="e0806-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0806-119">Temperaturas</span><span class="sxs-lookup"><span data-stu-id="e0806-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0806-120">Humedad</span><span class="sxs-lookup"><span data-stu-id="e0806-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0806-121">Frontal de las caras del servidor</span><span class="sxs-lookup"><span data-stu-id="e0806-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="e0806-122">Pasillo caliente/pasillo Cold</span><span class="sxs-lookup"><span data-stu-id="e0806-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0806-123">Holgura de escape no obstaculizada</span><span class="sxs-lookup"><span data-stu-id="e0806-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

