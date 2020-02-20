---
title: 'Lync Server 2013: informe de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5dbfb056107d84aa0f3c483100619b27251feff4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a><span data-ttu-id="d66f9-102">Informe de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d66f9-102">Device Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d66f9-103">_**Última modificación del tema:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="d66f9-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="d66f9-104">Puede que el informe del dispositivo sea mejor titulado el informe de micrófonos y altavoces; Esto se debe a que el informe de dispositivos recupera las métricas relacionadas con llamadas (por ejemplo, el porcentaje de llamadas deficientes, el eco y el tiempo de conmutación de voz) agrupados por los micrófonos y los altavoces que se usan en la llamada.</span><span class="sxs-lookup"><span data-stu-id="d66f9-104">The Device Report might be better titled the Microphone and Speakers Report; that's because the Device Report retrieves call-related metrics (such as poor call percentage, echo, and voice switch time) grouped by the microphones and speakers used in the call.</span></span> <span data-ttu-id="d66f9-105">Si está interesado en los teléfonos IP (también conocidos como "dispositivos"), use el [Informe de inventario de teléfono IP en Lync Server 2013 en](lync-server-2013-ip-phone-inventory-report.md) su lugar.</span><span class="sxs-lookup"><span data-stu-id="d66f9-105">If you are interested in IP phones (also commonly referred to as "devices"), use the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) instead.</span></span>

<span data-ttu-id="d66f9-106">El informe de dispositivos es muy útil para los administradores que determinan si un tipo específico de dispositivo está experimentando grandes cantidades de llamadas de mala calidad que otras.</span><span class="sxs-lookup"><span data-stu-id="d66f9-106">The Device Report is extremely useful for administrators in determining if a specific type of device is experiencing high volumes of poor quality calls than others.</span></span> <span data-ttu-id="d66f9-107">A su vez, esto podría influir en las decisiones que debe tomar cuando llegue el momento de comprar nuevos dispositivos o reemplazar los dispositivos existentes.</span><span class="sxs-lookup"><span data-stu-id="d66f9-107">In turn, this could influence any decisions you must make when it comes time to buy new devices or to replace existing devices.</span></span>

<span data-ttu-id="d66f9-108">De forma predeterminada, la información que se muestra en el informe de dispositivos también se basa en el micrófono (el dispositivo de captura) y los altavoces y los auriculares (el dispositivo de presentación) que se usan en la llamada.</span><span class="sxs-lookup"><span data-stu-id="d66f9-108">By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="d66f9-109">Por ejemplo, supongamos que tiene varios usuarios que usan el siguiente dispositivo de captura y el siguiente dispositivo de representación: de forma predeterminada, la información que se muestra en el informe de dispositivos también se basa en el micrófono (el dispositivo de captura) y los altavoces y los auriculares (el dispositivo de presentación) que se usan en la llamada.</span><span class="sxs-lookup"><span data-stu-id="d66f9-109">For example, suppose you have several users who use the following capture device and the following render device: By default, the information displayed in the Device Report is also based on the microphone (the capture device) and speakers/headset (the render device) used in the call.</span></span> <span data-ttu-id="d66f9-110">Por ejemplo, supongamos que tiene varios usuarios que usan el siguiente dispositivo de captura y el siguiente dispositivo de representación:</span><span class="sxs-lookup"><span data-stu-id="d66f9-110">For example, suppose you have several users who use the following capture device and the following render device:</span></span>

  - <span data-ttu-id="d66f9-111">Dispositivo de captura: micrófono (audio HD digital integrado SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="d66f9-111">Capture device -- Microphone (SoundMAX Integrated Digital HD Audio)</span></span>

  - <span data-ttu-id="d66f9-112">Dispositivo de representación: Presentación: de auriculares (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="d66f9-112">Render device -- Headset Earphone (Microsoft LifeChat LX-3000)</span></span>

<span data-ttu-id="d66f9-113">Si estos usuarios realizaron un total de 254 llamadas, verá una entrada como la siguiente en el informe:</span><span class="sxs-lookup"><span data-stu-id="d66f9-113">If those users made a total of 254 calls you'll see an entry like this in the report:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d66f9-114">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="d66f9-114">Capture device</span></span></th>
<th><span data-ttu-id="d66f9-115">Dispositivo de presentación</span><span class="sxs-lookup"><span data-stu-id="d66f9-115">Render device</span></span></th>
<th><span data-ttu-id="d66f9-116">Volumen de llamadas</span><span class="sxs-lookup"><span data-stu-id="d66f9-116">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d66f9-117">Micrófono (audio HD digital integrado SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="d66f9-117">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="d66f9-118">Auriculares con presentación: (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="d66f9-118">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="d66f9-119">254</span><span class="sxs-lookup"><span data-stu-id="d66f9-119">254</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d66f9-120">Ahora, supongamos que tiene una serie de usuarios que usan el mismo dispositivo de captura, pero un dispositivo de representación diferente.</span><span class="sxs-lookup"><span data-stu-id="d66f9-120">Now, suppose you have a number of users who use that same capture device but a different render device.</span></span> <span data-ttu-id="d66f9-121">En ese caso, tendrá una segunda entrada de línea en el informe, una para esa combinación única de dispositivo de captura y dispositivo de presentación:</span><span class="sxs-lookup"><span data-stu-id="d66f9-121">In that case, you'll have a second line entry in the report, one for that unique combination of capture device and render device:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d66f9-122">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="d66f9-122">Capture device</span></span></th>
<th><span data-ttu-id="d66f9-123">Dispositivo de presentación</span><span class="sxs-lookup"><span data-stu-id="d66f9-123">Render device</span></span></th>
<th><span data-ttu-id="d66f9-124">Volumen de llamadas</span><span class="sxs-lookup"><span data-stu-id="d66f9-124">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d66f9-125">Micrófono (audio HD digital integrado SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="d66f9-125">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="d66f9-126">Auriculares con presentación: (Microsoft LifeChat LX-3000)</span><span class="sxs-lookup"><span data-stu-id="d66f9-126">Headset Earphone (Microsoft LifeChat LX-3000)</span></span></p></td>
<td><p><span data-ttu-id="d66f9-127">254</span><span class="sxs-lookup"><span data-stu-id="d66f9-127">254</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d66f9-128">Micrófono (audio HD digital integrado SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="d66f9-128">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="d66f9-129">Altavoces (audio HD digital integrado SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="d66f9-129">Speakers (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="d66f9-130">319</span><span class="sxs-lookup"><span data-stu-id="d66f9-130">319</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d66f9-131">Si prefiere ver los totales combinados de un dispositivo determinado (por ejemplo, para el dispositivo de captura de SoundMAX, independientemente del dispositivo de representación usado), seleccione la opción adecuada en la lista desplegable tipo de dispositivo (dispositivo de captura o dispositivo de presentación).</span><span class="sxs-lookup"><span data-stu-id="d66f9-131">If you would rather see combined totals for a given device (for example, for the SoundMAX capture device, regardless of the render device used), select the appropriate option from the Device type dropdown list (either Capture device or Render device).</span></span> <span data-ttu-id="d66f9-132">Si selecciona dispositivo de captura en este ejemplo, obtendrá un resultado similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="d66f9-132">If you select Capture device in this example, that will give you output similar to this:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d66f9-133">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="d66f9-133">Capture device</span></span></th>
<th><span data-ttu-id="d66f9-134">Volumen de llamadas</span><span class="sxs-lookup"><span data-stu-id="d66f9-134">Call volume</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d66f9-135">Micrófono (audio HD digital integrado SoundMAX)</span><span class="sxs-lookup"><span data-stu-id="d66f9-135">Microphone (SoundMAX Integrated Digital HD Audio)</span></span></p></td>
<td><p><span data-ttu-id="d66f9-136">573</span><span class="sxs-lookup"><span data-stu-id="d66f9-136">573</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a><span data-ttu-id="d66f9-137">Acceso al informe de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d66f9-137">Accessing the Device Report</span></span>

<span data-ttu-id="d66f9-138">El acceso al informe de dispositivos se suele obtener desde la Página principal de informes de supervisión.</span><span class="sxs-lookup"><span data-stu-id="d66f9-138">The Device Report is typically accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="d66f9-139">Sin embargo, si está viendo el [Informe de detalles de llamadas en Lync Server 2013](lync-server-2013-call-detail-report.md) , puede hacer clic en cualquiera de las siguientes métricas para obtener acceso al informe de dispositivos de un dispositivo específico:</span><span class="sxs-lookup"><span data-stu-id="d66f9-139">However, if you are viewing the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) you can drill down to the Device Report for a specific device by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="d66f9-140">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="d66f9-140">Capture Device</span></span>

  - <span data-ttu-id="d66f9-141">Dispositivo de representación</span><span class="sxs-lookup"><span data-stu-id="d66f9-141">Render Device</span></span>

<span data-ttu-id="d66f9-142">En el informe de dispositivos, puede profundizar hasta el [Informe de lista de llamadas en Lync Server 2013](lync-server-2013-call-list-report.md) haciendo clic en cualquiera de las métricas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d66f9-142">From the Device Report you can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="d66f9-143">Volumen de llamadas</span><span class="sxs-lookup"><span data-stu-id="d66f9-143">Call volume</span></span>

  - <span data-ttu-id="d66f9-144">Porcentaje de llamadas deficientes</span><span class="sxs-lookup"><span data-stu-id="d66f9-144">Poor call percentage</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a><span data-ttu-id="d66f9-145">Cómo hacer el mejor uso del informe de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d66f9-145">Making the Best Use of the Device Report</span></span>

<span data-ttu-id="d66f9-146">En cuanto a los nombres de dispositivo, el informe de dispositivo es muy detallado; por ejemplo, supongamos que tiene los dispositivos de captura siguientes:</span><span class="sxs-lookup"><span data-stu-id="d66f9-146">When it comes to device names, the Device Report is extremely detailed; for example, suppose you have the following capture devices:</span></span>

  - <span data-ttu-id="d66f9-147">Micrófono Aastra 3002 (2-Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="d66f9-147">Aastra 3002 Microphone (2- Aastra 3002)</span></span>

  - <span data-ttu-id="d66f9-148">Micrófono Aastra 3002 (3-Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="d66f9-148">Aastra 3002 Microphone (3- Aastra 3002)</span></span>

  - <span data-ttu-id="d66f9-149">Micrófono Aastra 3002 (Aastra 3002)</span><span class="sxs-lookup"><span data-stu-id="d66f9-149">Aastra 3002 Microphone (Aastra 3002)</span></span>

  - <span data-ttu-id="d66f9-150">Aastra 6725ip</span><span class="sxs-lookup"><span data-stu-id="d66f9-150">Aastra 6725ip</span></span>

  - <span data-ttu-id="d66f9-151">Micrófono 6725ip Aastra (10-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d66f9-151">Aastra 6725ip Microphone (10- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d66f9-152">Micrófono 6725ip Aastra (10-Aastra 6725ip)-v0</span><span class="sxs-lookup"><span data-stu-id="d66f9-152">Aastra 6725ip Microphone (10- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="d66f9-153">Micrófono 6725ip Aastra (2-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d66f9-153">Aastra 6725ip Microphone (2- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d66f9-154">Micrófono 6725ip Aastra (3-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d66f9-154">Aastra 6725ip Microphone (3- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d66f9-155">Micrófono 6725ip Aastra (4-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d66f9-155">Aastra 6725ip Microphone (4- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d66f9-156">Micrófono 6725ip Aastra (5-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d66f9-156">Aastra 6725ip Microphone (5- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d66f9-157">Micrófono 6725ip Aastra (6-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d66f9-157">Aastra 6725ip Microphone (6- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d66f9-158">Micrófono 6725ip Aastra (7-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d66f9-158">Aastra 6725ip Microphone (7- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d66f9-159">Micrófono 6725ip Aastra (9-Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d66f9-159">Aastra 6725ip Microphone (9- Aastra 6725ip)</span></span>

  - <span data-ttu-id="d66f9-160">Micrófono 6725ip Aastra (9-Aastra 6725ip)-v0</span><span class="sxs-lookup"><span data-stu-id="d66f9-160">Aastra 6725ip Microphone (9- Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="d66f9-161">Micrófono 6725ip de Aastra (Aastra 6725ip)</span><span class="sxs-lookup"><span data-stu-id="d66f9-161">Aastra 6725ip Microphone (Aastra 6725ip)</span></span>

  - <span data-ttu-id="d66f9-162">Aastra 6725ip micrófono (Aastra 6725ip)-v0</span><span class="sxs-lookup"><span data-stu-id="d66f9-162">Aastra 6725ip Microphone (Aastra 6725ip)-V0</span></span>

  - <span data-ttu-id="d66f9-163">Micrófono 6725ip Aastra (dispositivo de audio USB)</span><span class="sxs-lookup"><span data-stu-id="d66f9-163">Aastra 6725ip Microphone (USB Audio Device)</span></span>

  - <span data-ttu-id="d66f9-164">Aastra 6725ip micrófono (dispositivo de audio USB)-v0</span><span class="sxs-lookup"><span data-stu-id="d66f9-164">Aastra 6725ip Microphone (USB Audio Device)-V0</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d66f9-165">Tenga en cuenta que los nombres de los dispositivos de captura podrían no ser los mismos si ejecuta versiones localizadas de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d66f9-165">Keep in mind that capture device names might not be the same if you are running localized versions of Lync Server 2013.</span></span> <span data-ttu-id="d66f9-166">Un dispositivo denominado Aastra 6725ip micrófono (Aastra 6725ip)-v0 en Inglés de Estados Unidos podría tener un nombre distinto en francés o en español.</span><span class="sxs-lookup"><span data-stu-id="d66f9-166">A device named Aastra 6725ip Microphone (Aastra 6725ip)-V0 in US English could have a different name in French or Spanish.</span></span>



</div>

<span data-ttu-id="d66f9-167">A menudo deseará un nivel de detalle; en otras ocasiones, sin embargo, es posible que solo le interese el número de llamadas que usan un micrófono Aastra, independientemente del número de modelo.</span><span class="sxs-lookup"><span data-stu-id="d66f9-167">Often times you'll want that level of detail; at other times, however, you might only be interested in how many calls use any Aastra microphone, regardless of model number.</span></span> <span data-ttu-id="d66f9-168">Una forma de obtener información como ésta es exportar los datos del informe de dispositivos a Microsoft Excel y, a continuación, guardarlos en un archivo de valores separados por comas (\\por\\ejemplo\_, C: Data Devices Report. csv).</span><span class="sxs-lookup"><span data-stu-id="d66f9-168">One way to get information like that is to export the Device Report data to Microsoft Excel and then save that data to a comma-separated values file (for example, C:\\Data\\Devices\_Report.csv).</span></span> <span data-ttu-id="d66f9-169">A continuación, puede usar un conjunto de comandos similares a estos para importar el. CSV en Windows PowerShell e Informe sobre el número total de llamadas realizadas con un dispositivo de captura de Aastra:</span><span class="sxs-lookup"><span data-stu-id="d66f9-169">You can then use a set of commands similar to these to import the .CSV file into Windows PowerShell and report back the total number of calls made using an Aastra capture device:</span></span>

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

<span data-ttu-id="d66f9-170">Esto devolverá un valor único que representa el número total de llamadas realizadas mediante un dispositivo de captura Aastra.</span><span class="sxs-lookup"><span data-stu-id="d66f9-170">That will return a single value representing the total number of calls made using an Aastra capture device.</span></span> <span data-ttu-id="d66f9-171">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d66f9-171">For example:</span></span>

    384

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d66f9-172">Filtros</span><span class="sxs-lookup"><span data-stu-id="d66f9-172">Filters</span></span>

<span data-ttu-id="d66f9-173">Los filtros se emplean para recuperar un conjunto de datos más específico o para ver los datos devueltos de diferentes formas.</span><span class="sxs-lookup"><span data-stu-id="d66f9-173">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="d66f9-174">Por ejemplo, el informe de dispositivos le permite filtrar en aspectos como el tipo de llamada (es decir, que fue la llamada a una llamada de cliente), una llamada de conferencia o una llamada de red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="d66f9-174">For example, the Device Report enables you to filter on such things as call type (that is, was the call a client call), a conference call, or a public switched telephone network (PSTN) call.</span></span> <span data-ttu-id="d66f9-175">También se puede elegir cómo agrupar los datos.</span><span class="sxs-lookup"><span data-stu-id="d66f9-175">You can also choose how data should be grouped.</span></span> <span data-ttu-id="d66f9-176">En este caso, los dispositivos se agrupan por hora, día, semana o mes.</span><span class="sxs-lookup"><span data-stu-id="d66f9-176">In this case, devices are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="d66f9-177">En la siguiente tabla se enumeran los filtros que se pueden usar con el informe de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d66f9-177">The following table lists the filters that you can use with the Device Report.</span></span>

### <a name="device-report-filters"></a><span data-ttu-id="d66f9-178">Filtros de informes de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d66f9-178">Device Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d66f9-179">Nombre</span><span class="sxs-lookup"><span data-stu-id="d66f9-179">Name</span></span></th>
<th><span data-ttu-id="d66f9-180">Descripción</span><span class="sxs-lookup"><span data-stu-id="d66f9-180">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d66f9-181"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-181"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-p111">Fecha y hora de inicio del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de inicio tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="d66f9-p111">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d66f9-184">7/7/2012 1:00 pm</span><span class="sxs-lookup"><span data-stu-id="d66f9-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d66f9-p112">Si no escribe una hora de inicio, el informe comienza automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="d66f9-p112">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d66f9-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d66f9-187">7/7/2012</span></span></p>
<p><span data-ttu-id="d66f9-188">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="d66f9-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d66f9-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d66f9-189">7/3/2012</span></span></p>
<p><span data-ttu-id="d66f9-190">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="d66f9-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d66f9-191"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-191"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-p113">Fecha y hora de finalización del intervalo de tiempo. Para ver los datos por horas, escriba la fecha y hora de finalización tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="d66f9-p113">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d66f9-194">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d66f9-194">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d66f9-p114">Si no escribe una hora de finalización, el informe termina automáticamente a las 12:00 h del día especificado. Para ver los datos por día, escriba solo la fecha:</span><span class="sxs-lookup"><span data-stu-id="d66f9-p114">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d66f9-197">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d66f9-197">7/7/2012</span></span></p>
<p><span data-ttu-id="d66f9-198">Para verlos por semanas o por meses, escriba una fecha que caiga en cualquier punto de la semana o del mes que desee ver (no es necesario escribir el primer día de la semana o del mes):</span><span class="sxs-lookup"><span data-stu-id="d66f9-198">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d66f9-199">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d66f9-199">7/3/2012</span></span></p>
<p><span data-ttu-id="d66f9-200">Las semanas siempre van del domingo al sábado.</span><span class="sxs-lookup"><span data-stu-id="d66f9-200">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d66f9-201"><strong>Causa del cambio de voz</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-201"><strong>Voice switch cause</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-202">Razón por la que se ha tenido que poner una llamada en modo de dúplex medio para evitar el eco.</span><span class="sxs-lookup"><span data-stu-id="d66f9-202">Reason why a call had to be placed into half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="d66f9-203">En el modo de dúplex medio, la comunicación sólo puede realizarse en una dirección a la vez, de manera similar a como se convierten los usuarios al comunicarse con un walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="d66f9-203">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span> <span data-ttu-id="d66f9-204">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d66f9-204">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-205">Todos</span><span class="sxs-lookup"><span data-stu-id="d66f9-205">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-206">Ninguno</span><span class="sxs-lookup"><span data-stu-id="d66f9-206">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-207">Marca de hora incorrecta</span><span class="sxs-lookup"><span data-stu-id="d66f9-207">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-208">Echo</span><span class="sxs-lookup"><span data-stu-id="d66f9-208">Echo</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-209">DNLP (procesador no lineal dinámico)</span><span class="sxs-lookup"><span data-stu-id="d66f9-209">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-210">Complejidad baja</span><span class="sxs-lookup"><span data-stu-id="d66f9-210">Low complexity</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-211">Estado de dispositivo incorrecto</span><span class="sxs-lookup"><span data-stu-id="d66f9-211">Bad device state</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-212">Eco posterior a AEC (cancelación del eco acústico)</span><span class="sxs-lookup"><span data-stu-id="d66f9-212">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d66f9-213"><strong>Causa del eco</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-213"><strong>Echo cause</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-214">Razón por la que se detectó un eco por encima del nivel aceptado en una llamada.</span><span class="sxs-lookup"><span data-stu-id="d66f9-214">Reason why echo above the accepted level was detected in a call.</span></span> <span data-ttu-id="d66f9-215">(En telecomunicaciones, ECHO es un reflejo del sonido, el mismo fenómeno que oirá si Yell a la parte inferior de un bien.) Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d66f9-215">(In telecommunications, echo is a reflection of sound, the same phenomenon you will hear if you yell down to the bottom of a well.) Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-216">Todos</span><span class="sxs-lookup"><span data-stu-id="d66f9-216">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-217">Ninguno</span><span class="sxs-lookup"><span data-stu-id="d66f9-217">None</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-218">Marca de hora incorrecta</span><span class="sxs-lookup"><span data-stu-id="d66f9-218">Bad timestamp</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-219">Eco posterior a AEC (cancelación del eco acústico)</span><span class="sxs-lookup"><span data-stu-id="d66f9-219">Post-AEC echo (acoustic echo cancellation)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-220">ANLP (procesador no lineal adaptable)</span><span class="sxs-lookup"><span data-stu-id="d66f9-220">ANLP (adaptive nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-221">DNLP (procesador no lineal dinámico)</span><span class="sxs-lookup"><span data-stu-id="d66f9-221">DNLP (dynamic nonlinear processor)</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-222">Recorte de micrófono</span><span class="sxs-lookup"><span data-stu-id="d66f9-222">Microphone clipping</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d66f9-223"><strong>Tipo de llamada</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-223"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-224">Indica el tipo de llamada que se realizó.</span><span class="sxs-lookup"><span data-stu-id="d66f9-224">Indicates the type of call that was made.</span></span> <span data-ttu-id="d66f9-225">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d66f9-225">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-226">Todos</span><span class="sxs-lookup"><span data-stu-id="d66f9-226">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-227">Llamada de cliente</span><span class="sxs-lookup"><span data-stu-id="d66f9-227">Client call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-228">Llamada RTC</span><span class="sxs-lookup"><span data-stu-id="d66f9-228">PSTN call</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-229">Llamada de conferencia</span><span class="sxs-lookup"><span data-stu-id="d66f9-229">Conference call</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d66f9-230"><strong>Tipo de acceso</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-230"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-p118">Indica si el cliente había iniciado sesión en la red interna o en la externa cuando se realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d66f9-p118">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-233">Todos</span><span class="sxs-lookup"><span data-stu-id="d66f9-233">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-234">Interno</span><span class="sxs-lookup"><span data-stu-id="d66f9-234">Internal</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-235">External</span><span class="sxs-lookup"><span data-stu-id="d66f9-235">External</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d66f9-236"><strong>Tipo de red</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-236"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-p119">Indica el tipo de red al que estaba conectado el cliente cuando realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d66f9-p119">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-239">Todos</span><span class="sxs-lookup"><span data-stu-id="d66f9-239">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-240">Cableada</span><span class="sxs-lookup"><span data-stu-id="d66f9-240">Wired</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-241">Wireless</span><span class="sxs-lookup"><span data-stu-id="d66f9-241">Wireless</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d66f9-242"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-242"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-p120">Indica si un cliente externo estaba utilizando una conexión de red privada virtual (VPN) cuando se realizó la llamada. Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d66f9-p120">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-245">Todos</span><span class="sxs-lookup"><span data-stu-id="d66f9-245">[All]</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-246">VPN</span><span class="sxs-lookup"><span data-stu-id="d66f9-246">VPN</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-247">No VPN</span><span class="sxs-lookup"><span data-stu-id="d66f9-247">Non-VPN</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d66f9-248"><strong>Tipo de dispositivo</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-248"><strong>Device type</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-249">Indica el tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d66f9-249">Indicates the type of device.</span></span> <span data-ttu-id="d66f9-250">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d66f9-250">Select one of the following:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-251">Dispositivo de captura</span><span class="sxs-lookup"><span data-stu-id="d66f9-251">Capture device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-252">Dispositivo de presentación</span><span class="sxs-lookup"><span data-stu-id="d66f9-252">Render device</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="d66f9-253">Par de dispositivos de captura/representación</span><span class="sxs-lookup"><span data-stu-id="d66f9-253">Capture/Render device pair</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d66f9-254"><strong>Nombre de dispositivo</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-254"><strong>Device name</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-255">Nombre del dispositivo de captura o representación.</span><span class="sxs-lookup"><span data-stu-id="d66f9-255">Name of the capture or render device.</span></span> <span data-ttu-id="d66f9-256">Puede escribir el nombre completo del dispositivo o cualquier parte del nombre del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d66f9-256">You can enter the complete device name or any portion of the device name.</span></span> <span data-ttu-id="d66f9-257">Por ejemplo, para encontrar el micrófono del dispositivo (Microsoft LifeCam VX-1000.), puede escribir el nombre completo del dispositivo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d66f9-257">For example, to find the device Microphone (Microsoft LifeCam VX-1000.), you can enter the complete device name as follows:</span></span></p>
<p><span data-ttu-id="d66f9-258">Micrófono (Microsoft LifeCam VX-1000.)</span><span class="sxs-lookup"><span data-stu-id="d66f9-258">Microphone (Microsoft LifeCam VX-1000.)</span></span></p>
<p><span data-ttu-id="d66f9-259">O bien, puede escribir sólo una parte del nombre.</span><span class="sxs-lookup"><span data-stu-id="d66f9-259">Or, you can enter just a portion of the name.</span></span> <span data-ttu-id="d66f9-260">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d66f9-260">For example:</span></span></p>
<p><span data-ttu-id="d66f9-261">LifeCam</span><span class="sxs-lookup"><span data-stu-id="d66f9-261">LifeCam</span></span></p>
<p><span data-ttu-id="d66f9-262">Tenga en cuenta que el filtro anterior devuelve cualquier dispositivo que contenga la cadena &quot;LifeCam&quot; en cualquier lugar en su nombre.</span><span class="sxs-lookup"><span data-stu-id="d66f9-262">Note that the preceding filter returns any device that contains the string &quot;LifeCam&quot; anywhere in its name.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d66f9-263">Métricas</span><span class="sxs-lookup"><span data-stu-id="d66f9-263">Metrics</span></span>

<span data-ttu-id="d66f9-264">En la siguiente tabla se muestra la información proporcionada en el informe de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d66f9-264">The following table lists the information provided in the Device Report.</span></span>

### <a name="device-report-metrics"></a><span data-ttu-id="d66f9-265">Métricas del informe de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d66f9-265">Device Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d66f9-266">Nombre</span><span class="sxs-lookup"><span data-stu-id="d66f9-266">Name</span></span></th>
<th><span data-ttu-id="d66f9-267">¿Se pueden ordenar los datos en este elemento?</span><span class="sxs-lookup"><span data-stu-id="d66f9-267">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d66f9-268">Descripción</span><span class="sxs-lookup"><span data-stu-id="d66f9-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d66f9-269"><strong>Dispositivo de captura</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-269"><strong>Capture device</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-270">Sí</span><span class="sxs-lookup"><span data-stu-id="d66f9-270">Yes</span></span></p></td>
<td><p><span data-ttu-id="d66f9-271">Dispositivo (por ejemplo, un micrófono o una cámara web) que se usa para transmitir audio.</span><span class="sxs-lookup"><span data-stu-id="d66f9-271">Device (for example, a microphone or webcam) used for transmitting audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d66f9-272"><strong>Dispositivo de presentación</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-272"><strong>Render device</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-273">Sí</span><span class="sxs-lookup"><span data-stu-id="d66f9-273">Yes</span></span></p></td>
<td><p><span data-ttu-id="d66f9-274">Dispositivo (por ejemplo, unos auriculares o altavoces) que se usa para recibir audio.</span><span class="sxs-lookup"><span data-stu-id="d66f9-274">Device (for example, a headset or speakers) used for receiving audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d66f9-275"><strong>Volumen de llamadas</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-275"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-276">Sí</span><span class="sxs-lookup"><span data-stu-id="d66f9-276">Yes</span></span></p></td>
<td><p><span data-ttu-id="d66f9-277">Número total de llamadas realizadas.</span><span class="sxs-lookup"><span data-stu-id="d66f9-277">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d66f9-278"><strong>Porcentaje de llamadas deficientes</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-278"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-279">Sí</span><span class="sxs-lookup"><span data-stu-id="d66f9-279">Yes</span></span></p></td>
<td><p><span data-ttu-id="d66f9-280">Porcentaje de llamadas que se han clasificado &quot;como malas. &quot; Una llamada deficiente es cualquier llamada que al menos una de las métricas medidas superó el valor permitido (por ejemplo, una llamada que experimentó una vibración excesiva).</span><span class="sxs-lookup"><span data-stu-id="d66f9-280">Percentage of calls that were classified as &quot;poor.&quot; A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d66f9-281"><strong>Usuarios únicos</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-281"><strong>Unique users</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-282">Sí</span><span class="sxs-lookup"><span data-stu-id="d66f9-282">Yes</span></span></p></td>
<td><p><span data-ttu-id="d66f9-283">Usuarios únicos que han usado el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d66f9-283">Unique users who used the device.</span></span> <span data-ttu-id="d66f9-284">Si un usuario ha utilizado el dispositivo 13 veces, puede contar como un usuario único, igual que un usuario que solo usó el dispositivo una sola vez.</span><span class="sxs-lookup"><span data-stu-id="d66f9-284">If a user used the device 13 times he or she would count as one unique user, the same as a user who only used the device a single time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d66f9-285"><strong>Relación de tiempo de conmutación de voz</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-285"><strong>Ratio of voice switch time</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-286">Sí</span><span class="sxs-lookup"><span data-stu-id="d66f9-286">Yes</span></span></p></td>
<td><p><span data-ttu-id="d66f9-287">Porcentaje de la llamada que tuvo que realizarse en modo de dúplex medio para evitar el eco.</span><span class="sxs-lookup"><span data-stu-id="d66f9-287">Percentage of the call that had to be conducted in half duplex mode in order to prevent echo.</span></span> <span data-ttu-id="d66f9-288">En el modo de dúplex medio, la comunicación sólo puede realizarse en una dirección a la vez, de manera similar a como se convierten los usuarios al comunicarse con un walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="d66f9-288">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d66f9-289"><strong>Relación de que el micrófono no funciona</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-289"><strong>Ratio of microphone not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-290">Sí</span><span class="sxs-lookup"><span data-stu-id="d66f9-290">Yes</span></span></p></td>
<td><p><span data-ttu-id="d66f9-291">Porcentaje de la llamada en la que el dispositivo de captura no estaba funcionando a un nivel aceptable.</span><span class="sxs-lookup"><span data-stu-id="d66f9-291">Percentage of the call in which the capture device was not functioning at an acceptable level.</span></span> <span data-ttu-id="d66f9-292">Un valor alto sugiere que los problemas de calidad con la llamada se deben principalmente a que el dispositivo de captura no funciona como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="d66f9-292">A high values suggests that quality issues with the call were primarily due to the capture device not working as expected.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d66f9-293"><strong>Relación de que el altavoz no funciona</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-293"><strong>Ratio of speaker not functioning</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-294">Sí</span><span class="sxs-lookup"><span data-stu-id="d66f9-294">Yes</span></span></p></td>
<td><p><span data-ttu-id="d66f9-295">Porcentaje de la llamada en la que el dispositivo de representación no funcionaba a un nivel aceptable.</span><span class="sxs-lookup"><span data-stu-id="d66f9-295">Percentage of the call in which the render device was not functioning at an acceptable level.</span></span> <span data-ttu-id="d66f9-296">Un valor alto sugiere que los problemas de calidad con la llamada se deben principalmente a que el dispositivo de presentación no funciona como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="d66f9-296">A high values suggests that quality issues with the call were primarily due to the render device not working as expected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d66f9-297"><strong>Llamadas con conmutación de voz (%)</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-297"><strong>Calls with voice switch (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-298">Sí</span><span class="sxs-lookup"><span data-stu-id="d66f9-298">Yes</span></span></p></td>
<td><p><span data-ttu-id="d66f9-299">Porcentaje del total de llamadas que se han tenido que poner en modo de dúplex medio.</span><span class="sxs-lookup"><span data-stu-id="d66f9-299">Percentage of the total calls which had to be placed into half duplex mode.</span></span> <span data-ttu-id="d66f9-300">En el modo de dúplex medio, la comunicación sólo puede realizarse en una dirección a la vez, de manera similar a como se convierten los usuarios al comunicarse con un walkie-talkie.</span><span class="sxs-lookup"><span data-stu-id="d66f9-300">In half duplex mode, communication can travel in only one direction at a time, similar to the way users take turns when communicating with a walkie-talkie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d66f9-301"><strong>Eco de micrófono en (%)</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-301"><strong>Echo microphone in (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-302">Sí</span><span class="sxs-lookup"><span data-stu-id="d66f9-302">Yes</span></span></p></td>
<td><p><span data-ttu-id="d66f9-303">Porcentaje de tiempo durante el que se detectó el eco en la secuencia de captura del micrófono.</span><span class="sxs-lookup"><span data-stu-id="d66f9-303">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="d66f9-304">Normalmente, los valores son bajos para auriculares o auriculares, y más arriba para los teléfonos de altavoces o los altavoces autónomos.</span><span class="sxs-lookup"><span data-stu-id="d66f9-304">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="d66f9-305">Para los dispositivos que admiten la cancelación del eco acústico en la tarjeta, los valores altos indican la pérdida de eco.</span><span class="sxs-lookup"><span data-stu-id="d66f9-305">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="d66f9-306">Para otros dispositivos, esta métrica no debe usarse para evaluar la calidad del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d66f9-306">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d66f9-307"><strong>Envío de Eco (%)</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-307"><strong>Echo send (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-308">Sí</span><span class="sxs-lookup"><span data-stu-id="d66f9-308">Yes</span></span></p></td>
<td><p><span data-ttu-id="d66f9-309">Porcentaje de eco transmitido a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="d66f9-309">Percentage of echo transmitted to other users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d66f9-310"><strong>Llamadas con Eco (%)</strong></span><span class="sxs-lookup"><span data-stu-id="d66f9-310"><strong>Calls with echo (%)</strong></span></span></p></td>
<td><p><span data-ttu-id="d66f9-311">Sí</span><span class="sxs-lookup"><span data-stu-id="d66f9-311">Yes</span></span></p></td>
<td><p><span data-ttu-id="d66f9-312">Porcentaje del total de llamadas que ha tenido un eco que supera el nivel aceptable.</span><span class="sxs-lookup"><span data-stu-id="d66f9-312">Percentage of the total calls that had echo exceeding the acceptable level.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

