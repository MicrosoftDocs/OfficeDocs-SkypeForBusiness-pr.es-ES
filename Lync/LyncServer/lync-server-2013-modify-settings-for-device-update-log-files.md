---
title: 'Lync Server 2013: modificar la configuración de los archivos de registro de actualización de dispositivos'
description: 'Lync Server 2013: modificar la configuración de los archivos de registro de actualización de dispositivos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c2086e11a67207a00ca99773cc818106b16d05c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566976"
---
# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a><span data-ttu-id="753a9-103">Modificar la configuración de los archivos de registro de actualización de dispositivos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="753a9-103">Modify settings for Device Update log files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="753a9-104">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="753a9-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="753a9-105">Puede cambiar la configuración de la información de actualización de dispositivos que se registra en la organización mediante el panel de control de Lync Server o el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="753a9-105">You can change settings for how device update information is logged in your organization by using Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="753a9-106">En la siguiente tabla se muestran los valores que se pueden modificar y las herramientas que se usan para modificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="753a9-106">The following table shows which settings are modifiable, and which tool(s) you use to modify the settings.</span></span>

<span data-ttu-id="753a9-107">La configuración del registro se puede cambiar y aplicar globalmente o por sitio.</span><span class="sxs-lookup"><span data-stu-id="753a9-107">Log settings can be changed and applied globally, or per site.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="753a9-108">Para cambiar</span><span class="sxs-lookup"><span data-stu-id="753a9-108">To change</span></span></th>
<th><span data-ttu-id="753a9-109">Utilice</span><span class="sxs-lookup"><span data-stu-id="753a9-109">Use</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="753a9-110">Tamaño máximo (en bytes) de un archivo de registro</span><span class="sxs-lookup"><span data-stu-id="753a9-110">The maximum size (in bytes) for a log file</span></span></p></td>
<td><p><span data-ttu-id="753a9-111">Panel de Control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="753a9-111">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="753a9-112">– O bien –</span><span class="sxs-lookup"><span data-stu-id="753a9-112">-or-</span></span></p>
<p><span data-ttu-id="753a9-113">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="753a9-113">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="753a9-114">La cantidad máxima de información (en bytes) que se puede almacenar en la memoria caché</span><span class="sxs-lookup"><span data-stu-id="753a9-114">The maximum amount of information (in bytes) that can be held in the cache</span></span></p></td>
<td><p><span data-ttu-id="753a9-115">Panel de Control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="753a9-115">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="753a9-116">– O bien –</span><span class="sxs-lookup"><span data-stu-id="753a9-116">-or-</span></span></p>
<p><span data-ttu-id="753a9-117">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="753a9-117">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="753a9-118">Frecuencia (en minutos) con la que se escribe la información almacenada en caché en el archivo de registro</span><span class="sxs-lookup"><span data-stu-id="753a9-118">How often (in minutes) to write cached information to the log file</span></span></p></td>
<td><p><span data-ttu-id="753a9-119">Panel de Control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="753a9-119">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="753a9-120">– O bien –</span><span class="sxs-lookup"><span data-stu-id="753a9-120">-or-</span></span></p>
<p><span data-ttu-id="753a9-121">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="753a9-121">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="753a9-122">Tiempo (en días) que se conservarán los archivos de registro</span><span class="sxs-lookup"><span data-stu-id="753a9-122">How long (in days) to keep log files</span></span></p></td>
<td><p><span data-ttu-id="753a9-123">Panel de Control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="753a9-123">Lync Server Control Panel</span></span></p>
<p><span data-ttu-id="753a9-124">– O bien –</span><span class="sxs-lookup"><span data-stu-id="753a9-124">-or-</span></span></p>
<p><span data-ttu-id="753a9-125">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="753a9-125">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="753a9-126">Cuándo (hora del día) para comprobar si hay archivos expirados que deben eliminarse</span><span class="sxs-lookup"><span data-stu-id="753a9-126">When (time of day) to check for expired files that should be deleted</span></span></p></td>
<td><p><span data-ttu-id="753a9-127">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="753a9-127">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="753a9-128">Qué extensiones de archivo de registro se permiten</span><span class="sxs-lookup"><span data-stu-id="753a9-128">What log file extensions to permit</span></span></p></td>
<td><p><span data-ttu-id="753a9-129">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="753a9-129">Lync Server Management Shell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="753a9-130">Qué tipos de archivos de registro se deben conservar</span><span class="sxs-lookup"><span data-stu-id="753a9-130">Which log file types to retain</span></span></p></td>
<td><p><span data-ttu-id="753a9-131">Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="753a9-131">Lync Server Management Shell</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="753a9-132">Para cambiar la configuración de registro mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="753a9-132">To change logging settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="753a9-133">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="753a9-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="753a9-134">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="753a9-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="753a9-135">En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en **Configuración de registros de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="753a9-135">In the left navigation bar, click **Clients**, and then click **Device Log Configuration**.</span></span>

3.  <span data-ttu-id="753a9-136">En la página **Configuración de registros de dispositivos**, haga doble clic en la configuración que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="753a9-136">On the **Device Log Configuration** page, double-click the configuration that you want to change.</span></span>

4.  <span data-ttu-id="753a9-137">En el cuadro de diálogo **Editar configuración del registro** , cambie cualquiera de las siguientes opciones de configuración:</span><span class="sxs-lookup"><span data-stu-id="753a9-137">In the **Edit Log Setting** dialog box, change any of the following settings:</span></span>
    
      - <span data-ttu-id="753a9-138">**Tamaño máximo de archivo (bytes)**     Especifica el tamaño máximo que puede llegar a un archivo de registro antes de purgarse.</span><span class="sxs-lookup"><span data-stu-id="753a9-138">**Maximum file size (bytes)**   Specifies the maximum size a log file can become before it is purged.</span></span> <span data-ttu-id="753a9-139">El valor predeterminado es 1.024.000 (1 MB).</span><span class="sxs-lookup"><span data-stu-id="753a9-139">The default is 1,024,000 bytes (1 MB).</span></span>
    
      - <span data-ttu-id="753a9-140">**Tamaño máximo de la memoria caché (bytes)**     Especifica la cantidad máxima de información (en bytes) que se puede conservar en la memoria caché de archivos de registro antes de que se elimine la memoria caché y se escriban los datos en un archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="753a9-140">**Maximum cache size (bytes)**   Specifies the maximum amount of information (in bytes) that can be held in the log file cache before that cache must be cleared and the data is written to a log file.</span></span> <span data-ttu-id="753a9-141">El valor predeterminado es 512.000 (0,5 MB).</span><span class="sxs-lookup"><span data-stu-id="753a9-141">The default is 512,000 bytes (0.5 MB).</span></span>
    
      - <span data-ttu-id="753a9-142">**Número de minutos de vaciado de la memoria caché (1-60)**     Indica la frecuencia con la que la información almacenada en la memoria caché del archivo de registro se escribe en el archivo de registro real.</span><span class="sxs-lookup"><span data-stu-id="753a9-142">**Number of minutes to flush cache (1-60)**   Indicates how often information stored in the log file cache is written to the actual log file.</span></span> <span data-ttu-id="753a9-143">Una vez se ha registrado la información, la memoria caché se borra.</span><span class="sxs-lookup"><span data-stu-id="753a9-143">After the data is logged, the cache is cleared.</span></span> <span data-ttu-id="753a9-144">El valor predeterminado es cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="753a9-144">The default is five minutes.</span></span>
    
      - <span data-ttu-id="753a9-145">**Número de días que se conservarán los archivos de registro (1-365)**     Especifica el número de días que se conservan los archivos de registro antes de que se purguen.</span><span class="sxs-lookup"><span data-stu-id="753a9-145">**Number of days to keep log files (1-365)**   Specifies the number of days the log files are kept before they are purged.</span></span> <span data-ttu-id="753a9-146">El valor predeterminado es 10 días.</span><span class="sxs-lookup"><span data-stu-id="753a9-146">The default is 10 days.</span></span>

5.  <span data-ttu-id="753a9-147">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="753a9-147">Click **Commit**.</span></span>

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="753a9-148">Cambio de la configuración de registro mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="753a9-148">Changing Logging Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="753a9-149">La configuración del archivo de registro de actualización de dispositivos se puede modificar mediante Windows PowerShell y el cmdlet **set-CsDeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="753a9-149">Device update log file settings can be modified by using Windows PowerShell and the **Set-CsDeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="753a9-150">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="753a9-150">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="753a9-151">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="753a9-151">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="753a9-152">En los ejemplos siguientes se muestra un par de las formas en las que puede usar **set-CsDeviceUpdateConfiguration** para modificar la configuración.</span><span class="sxs-lookup"><span data-stu-id="753a9-152">The following examples show a couple of the ways that you can use **Set-CsDeviceUpdateConfiguration** to modify settings.</span></span>

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a><span data-ttu-id="753a9-153">Para modificar el tamaño máximo del archivo de registro y el intervalo de limpieza del registro</span><span class="sxs-lookup"><span data-stu-id="753a9-153">To modify the maximum log file size and the log cleanup interval</span></span>

  - <span data-ttu-id="753a9-154">El siguiente comando modifica la configuración del registro de actualización de dispositivos que se aplica al sitio de Redmond.</span><span class="sxs-lookup"><span data-stu-id="753a9-154">The following command modifies the device update log settings applied to the Redmond site.</span></span> <span data-ttu-id="753a9-155">En este ejemplo, el tamaño máximo del archivo de registro está establecido en 204800 bytes y el intervalo de limpieza de registro se establece en 14 días.</span><span class="sxs-lookup"><span data-stu-id="753a9-155">In this example, the maximum log file size is set to 204800 bytes and the log cleanup interval is set to 14 days.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a><span data-ttu-id="753a9-156">Para modificar el tiempo de limpieza del registro del día</span><span class="sxs-lookup"><span data-stu-id="753a9-156">To modify the log cleanup time of day</span></span>

  - <span data-ttu-id="753a9-157">Este comando establece el tiempo de limpieza de registro del sitio Redmond en 3:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="753a9-157">This command sets the log cleanup time for the Redmond site to 3:00 AM.</span></span>
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

<span data-ttu-id="753a9-158">Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="753a9-158">For details, see the Help topic for the [Set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

