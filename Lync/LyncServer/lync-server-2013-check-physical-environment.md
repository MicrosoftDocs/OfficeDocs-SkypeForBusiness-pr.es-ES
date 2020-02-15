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
ms.openlocfilehash: 6d8838336fbea4f901b763b7ca034f42e957de33
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="7cf20-102">Realizar comprobaciones físicas del entorno</span><span class="sxs-lookup"><span data-stu-id="7cf20-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cf20-103">_**Última modificación del tema:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="7cf20-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="7cf20-104">Antes de comprobar el rendimiento, la disponibilidad y la funcionalidad de la implementación de Lync Server 2013, debe comprobar el entorno físico.</span><span class="sxs-lookup"><span data-stu-id="7cf20-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="7cf20-105">Por ejemplo, es posible que haya que reducir la temperatura del salón del servidor o que sea necesario reemplazar un cable de red.</span><span class="sxs-lookup"><span data-stu-id="7cf20-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="7cf20-106">Para obtener los mejores resultados, realice los siguientes controles físicos del entorno:</span><span class="sxs-lookup"><span data-stu-id="7cf20-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="7cf20-107">**Medidas de seguridad física**   se debe proteger la protección de seguridad física, como bloqueos, puertas y salas de acceso restringido.</span><span class="sxs-lookup"><span data-stu-id="7cf20-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="7cf20-108">Compruebe si hay entradas no autorizadas, o indicios de daños en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7cf20-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="7cf20-109">\*\*\*\*   La temperatura y la humedad alta temperatura, el flujo de aire deficiente y la humedad pueden provocar el sobrecalentamiento de los componentes de hardware.</span><span class="sxs-lookup"><span data-stu-id="7cf20-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="7cf20-110">Compruebe la temperatura y la humedad para asegurarse de que los sistemas de entorno, como el calentamiento y el aire acondicionado, pueden mantener condiciones aceptables y funcionar dentro de las especificaciones del fabricante del hardware.</span><span class="sxs-lookup"><span data-stu-id="7cf20-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="7cf20-111">Cuando se haya instalado recientemente un nuevo equipo, compruebe también que el flujo de aire hacia y desde los servidores no está obstaculizado y cumple con las especificaciones del fabricante.</span><span class="sxs-lookup"><span data-stu-id="7cf20-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="7cf20-112">**Dispositivos y componentes**   la organización de Lync Server 2013 depende de una red física que funcione y de hardware relacionado.</span><span class="sxs-lookup"><span data-stu-id="7cf20-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="7cf20-113">Asegúrese de que los enrutadores, conmutadores, concentradores, cables físicos y conectores estén operativos.</span><span class="sxs-lookup"><span data-stu-id="7cf20-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="7cf20-114">La información específica sobre cómo realizar estas comprobaciones dependerá en gran medida del sitio de instalación y del hardware del servidor que se haya elegido.</span><span class="sxs-lookup"><span data-stu-id="7cf20-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="7cf20-115">La primera vez que realice esta comprobación, consulte la documentación del hardware y tenga en cuenta los parámetros deseados para futuras referencias.</span><span class="sxs-lookup"><span data-stu-id="7cf20-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="7cf20-116">Entorno de espacio del servidor deseado</span><span class="sxs-lookup"><span data-stu-id="7cf20-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7cf20-117">Parámetro</span><span class="sxs-lookup"><span data-stu-id="7cf20-117">Parameter</span></span></th>
<th><span data-ttu-id="7cf20-118">Intervalo o valor deseado</span><span class="sxs-lookup"><span data-stu-id="7cf20-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7cf20-119">Medidor</span><span class="sxs-lookup"><span data-stu-id="7cf20-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cf20-120">Humedad</span><span class="sxs-lookup"><span data-stu-id="7cf20-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7cf20-121">Anverso de las caras del servidor</span><span class="sxs-lookup"><span data-stu-id="7cf20-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="7cf20-122">Pasillo caliente/pasillo frío</span><span class="sxs-lookup"><span data-stu-id="7cf20-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7cf20-123">Holgura no obstaculizada del escape</span><span class="sxs-lookup"><span data-stu-id="7cf20-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

