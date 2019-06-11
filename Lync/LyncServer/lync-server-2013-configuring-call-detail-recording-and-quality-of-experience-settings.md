---
title: Configuración del registro detallado de llamadas y de las opciones de la calidad de la experiencia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67c9759faad4ed96cdf65d8bd22c5778512933de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="2867f-102">Configuración de la grabación de detalles de llamadas y la configuración de la calidad de la experiencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2867f-102">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2867f-103">_**Última modificación del tema:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="2867f-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="2867f-104">Después de asociar un almacén de supervisión con un grupo de servidores front-end, configurar el almacén de supervisión y, a continuación, instalar y configurar SQL Server Reporting Services y supervisar los informes, puede administrar la grabación de detalles de llamadas (CDR) y la calidad de la experiencia (QoE). supervisión mediante el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2867f-104">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Lync Server Management Shell.</span></span> <span data-ttu-id="2867f-105">Los cmdlets del shell de administración de Lync Server le permiten habilitar y deshabilitar la supervisión de CDR o QoE para un sitio en particular o para toda la implementación de Lync Server; Esto se puede llevar a cabo con un comando tan sencillo como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="2867f-105">Lync Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Lync Server deployment; that can be done with a command as simple as this:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

<span data-ttu-id="2867f-106">Al instalar Microsoft Lync Server 2013, también instalará una colección predefinida de opciones de configuración global tanto para CDR como para QoE.</span><span class="sxs-lookup"><span data-stu-id="2867f-106">When you install Microsoft Lync Server 2013, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="2867f-107">En la siguiente tabla se muestran los valores predeterminados para algunos de los valores usados más frecuentemente por el registro detallado de llamadas:</span><span class="sxs-lookup"><span data-stu-id="2867f-107">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2867f-108">Propiedad</span><span class="sxs-lookup"><span data-stu-id="2867f-108">Property</span></span></th>
<th><span data-ttu-id="2867f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2867f-109">Description</span></span></th>
<th><span data-ttu-id="2867f-110">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="2867f-110">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2867f-111">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="2867f-111">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="2867f-p103">Indica si está habilitado o no el CDR. Si se establece en True, se recopilarán y se escribirán todos los registros del CDR en la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="2867f-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="2867f-114">True</span><span class="sxs-lookup"><span data-stu-id="2867f-114">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2867f-115">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="2867f-115">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="2867f-p104">Indica si los registros del CDR se eliminarán o no periódicamente de la base de datos. Si se establece en True, los registros se eliminarán tras el período de tiempo especificado por las propiedades KeepCallDetailForDays (para registros del CDR) y KeepErrorReportForDays (para errores del CDR). Si se define como False, los registros detallados de llamadas se conservarán indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="2867f-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="2867f-119">True</span><span class="sxs-lookup"><span data-stu-id="2867f-119">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2867f-120">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="2867f-120">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="2867f-p105">Indica la cantidad de días que se conservarán los registros del CDR en la base de datos; los registros con mayor antigüedad que la cantidad de días especificada se eliminarán automáticamente. Pero, esto solo ocurrirá si la depuración está habilitada.</span><span class="sxs-lookup"><span data-stu-id="2867f-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="2867f-123">KeepCallDetailForDays puede definirse como cualquier valor entero entre 1 y 2562 días (aproximadamente 7 años).</span><span class="sxs-lookup"><span data-stu-id="2867f-123">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span></p></td>
<td><p><span data-ttu-id="2867f-124">60 días</span><span class="sxs-lookup"><span data-stu-id="2867f-124">60 days</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2867f-125">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="2867f-125">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="2867f-126">Indica la cantidad de días que se conservarán los informes de errores del CDR; cualquier informe con una antigüedad superior a la cantidad de días especificada se eliminará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2867f-126">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="2867f-127">Los informes de errores de CDR son informes de diagnóstico cargados por aplicaciones cliente como Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="2867f-127">CDR error reports are diagnostic reports uploaded by client applications such as Microsoft Lync 2013.</span></span></p>
<p><span data-ttu-id="2867f-128">Puede establecer esta propiedad en cualquier valor entero entre 1 y 2562 días.</span><span class="sxs-lookup"><span data-stu-id="2867f-128">You can set this property to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="2867f-129">60 días</span><span class="sxs-lookup"><span data-stu-id="2867f-129">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2867f-130">De manera similar, los valores predeterminados para la configuración de QoE se muestran en esta tabla:</span><span class="sxs-lookup"><span data-stu-id="2867f-130">Similarly, default values for selected QoE settings are shown in this table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2867f-131">Propiedad</span><span class="sxs-lookup"><span data-stu-id="2867f-131">Property</span></span></th>
<th><span data-ttu-id="2867f-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="2867f-132">Description</span></span></th>
<th><span data-ttu-id="2867f-133">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="2867f-133">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2867f-134">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="2867f-134">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="2867f-p107">Indica si la supervisión de QoE está o no habilitada. Si se establece en True, todos los registros de QoE se recopilarán y se escribirán en la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="2867f-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="2867f-137">True</span><span class="sxs-lookup"><span data-stu-id="2867f-137">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2867f-138">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="2867f-138">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="2867f-p108">Indica si los registros de QoE se eliminarán periódicamente de la base de datos. Si se establece en True, se eliminarán los registros tras el período de tiempo especificado por la propiedad KeepQoEDataForDays. Si se establece en False, los registros de QoE se mantendrán de manera indefinida.</span><span class="sxs-lookup"><span data-stu-id="2867f-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="2867f-142">True</span><span class="sxs-lookup"><span data-stu-id="2867f-142">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2867f-143">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="2867f-143">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="2867f-p109">Indica la cantidad de días que los registros de QoE se conservarán en la base de datos; los registros de mayor antigüedad que la cantidad de días especificada se eliminarán automáticamente. Pero, esto solo ocurrirá si la depuración está habilitada.</span><span class="sxs-lookup"><span data-stu-id="2867f-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="2867f-146">KeepCallDetailForDays se puede establecer en cualquier valor entero entre 1 y 2562 días.</span><span class="sxs-lookup"><span data-stu-id="2867f-146">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="2867f-147">60 días</span><span class="sxs-lookup"><span data-stu-id="2867f-147">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2867f-148">Si tiene que modificar estos valores globales puede hacerlo con los cmdlets Set-CsCdrConfiguration y Set-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="2867f-148">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets.</span></span> <span data-ttu-id="2867f-149">Por ejemplo, este comando (se ejecuta desde el shell de administración de Lync Server) deshabilita la supervisión de CDR en el ámbito global; Esto se hace estableciendo la propiedad EnableCDR en false ($False):</span><span class="sxs-lookup"><span data-stu-id="2867f-149">For example, this command (run from within the Lync Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

<span data-ttu-id="2867f-150">Tenga en cuenta que la deshabilitación de la supervisión no desasocia el almacén de supervisión del grupo de servidores front-end, ni desinstala o afecta de otra manera la base de datos de supervisión de back-end.</span><span class="sxs-lookup"><span data-stu-id="2867f-150">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="2867f-151">Cuando usa el shell de administración de Lync Server para deshabilitar la supervisión de CDR o QoE, todo lo que realmente hace es detener temporalmente Lync Server para recopilar y archivar los datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="2867f-151">When you use Lync Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Lync Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="2867f-152">Si desea reanudar, en este caso, la colección y el archivado de datos de CDR, lo único que tiene que hacer es establecer la propiedad EnableCDR de nuevo en True ($True):</span><span class="sxs-lookup"><span data-stu-id="2867f-152">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="2867f-153">De manera similar, este comando deshabilita la depuración de los registros de QoE en el ámbito global:</span><span class="sxs-lookup"><span data-stu-id="2867f-153">Similarly, this command disables the purging of QoE records at the global scope:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

<span data-ttu-id="2867f-p112">Además de la configuración global, los valores de configuración de CDR y QoE se pueden asignar al ámbito de sitio. Esto proporciona flexibilidad de administración adicional en lo referente a la supervisión; por ejemplo, un administrador puede habilitar la supervisión de CDR para el sitio de Redmond pero deshabilitar la supervisión de CDR para el sitio de Dublín. Para crear nuevos valores de configuración de CDR en el ámbito de sitio, use un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="2867f-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

<span data-ttu-id="2867f-p113">Tenga en cuenta que los valores configurados en el ámbito del sitio tienen prioridad frente a los valores configurados en el ámbito global. Por ejemplo, supongamos que la supervisión de CDR está habilitada en el ámbito global pero deshabilitada en el ámbito de sitio (para el sitio de Redmond). Eso significa que la información del registro detallado de llamadas no se archivará para usuarios en el sitio de Redmond. Pero, los usuarios de otros sitios (es decir, los usuarios administrados por los valores globales en lugar de la configuración de sitio de Redmond) tendrán su información del registro detallado de llamadas archivada.</span><span class="sxs-lookup"><span data-stu-id="2867f-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>

<span data-ttu-id="2867f-161">Los nuevos valores de configuración de QoE se pueden crear en el ámbito de sitio con un comando como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="2867f-161">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

<span data-ttu-id="2867f-162">Para obtener más información, escriba los siguientes comandos en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="2867f-162">For more information, type the following commands from within the Lync Server Management Shell:</span></span>

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

