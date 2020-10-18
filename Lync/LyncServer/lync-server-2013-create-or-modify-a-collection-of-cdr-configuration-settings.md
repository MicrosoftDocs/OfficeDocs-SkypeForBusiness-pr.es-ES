---
title: 'Lync Server 2013: crear o modificar una colección de opciones de configuración de CDR'
description: 'Lync Server 2013: crear o modificar una colección de opciones de configuración de CDR.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ba911607db55a7b7206645495e70a27ed453784
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578336"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="869b6-103">Crear o modificar una colección de opciones de configuración de CDR en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="869b6-103">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="869b6-104">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="869b6-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="869b6-p101">El registro detallado de llamadas (CDR) permite realizar un seguimiento del uso de aspectos como las sesiones de mensajería instantánea de punto a punto, llamadas telefónicas de voz sobre IP (VoIP) y llamadas de conferencia. Estos datos de uso contienen información sobre quién llamó a quién, cuándo se realizó la llamada y la duración de la misma.</span><span class="sxs-lookup"><span data-stu-id="869b6-p101">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="869b6-107">Al instalar Microsoft Lync Server 2013, se creará una única colección global de opciones de configuración de CDR.</span><span class="sxs-lookup"><span data-stu-id="869b6-107">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="869b6-108">Los administradores pueden también crear una configuración personalizada en el ámbito de sitio.</span><span class="sxs-lookup"><span data-stu-id="869b6-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="869b6-109">Cuando se usa esta configuración en el ámbito del sitio, predomina sobre la configuración global.</span><span class="sxs-lookup"><span data-stu-id="869b6-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="869b6-110">Por ejemplo, si crea una configuración cuyo ámbito es el sitio para el sitio de Redmond, se usará dicha configuración (en lugar de la configuración global) para administrar el CDR de Redmond.</span><span class="sxs-lookup"><span data-stu-id="869b6-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="869b6-111">Puede crear opciones de configuración de CDR con el panel de control de Lync Server o con el cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="869b6-111">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="869b6-112">Puede usar el panel de control de Lync Server o el cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) para modificar la configuración existente.</span><span class="sxs-lookup"><span data-stu-id="869b6-112">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="869b6-113">Si usa el panel de control de Lync Server para crear o modificar la configuración, estarán disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="869b6-113">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="869b6-114">Valor de IU</span><span class="sxs-lookup"><span data-stu-id="869b6-114">UI Setting</span></span></th>
<th><span data-ttu-id="869b6-115">Parámetro de PowerShell</span><span class="sxs-lookup"><span data-stu-id="869b6-115">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="869b6-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="869b6-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="869b6-117">Name</span><span class="sxs-lookup"><span data-stu-id="869b6-117">Name</span></span></p></td>
<td><p><span data-ttu-id="869b6-118">Identidad</span><span class="sxs-lookup"><span data-stu-id="869b6-118">Identity</span></span></p></td>
<td><p><span data-ttu-id="869b6-p104">Identificador único de los valores de configuración del CDR que se crean. Estos parámetros solo se pueden crear en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="869b6-p104">Unique identifier for the CDR configuration settings being created. These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="869b6-121">Habilitar supervisión del CDR</span><span class="sxs-lookup"><span data-stu-id="869b6-121">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="869b6-122">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="869b6-122">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="869b6-123">Indica si está o no habilitado el CDR.</span><span class="sxs-lookup"><span data-stu-id="869b6-123">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="869b6-124">Habilitar depuración de registros de detalles de llamadas (CDR)</span><span class="sxs-lookup"><span data-stu-id="869b6-124">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="869b6-125">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="869b6-125">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="869b6-126">Indica si los registros del CDR se eliminarán periódicamente de su base de datos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="869b6-126">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="869b6-127">Conservar registros de detalles de llamadas durante un máximo de (días)</span><span class="sxs-lookup"><span data-stu-id="869b6-127">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="869b6-128">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="869b6-128">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="869b6-p105">Indica el número de días que los registros del CDR se conservarán en su base de datos correspondiente. Los registros con una antigüedad superior al número de días especificado se eliminarán automáticamente. Tenga en cuenta que debe habilitar la purga para que pueda completarse.</span><span class="sxs-lookup"><span data-stu-id="869b6-p105">Indicates the number of days that CDR records will be kept in the CDR database. Any records older than the specified number of days will automatically be deleted. (Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="869b6-132">Conservar los datos de los informes de errores durante el período de duración máximo (días)</span><span class="sxs-lookup"><span data-stu-id="869b6-132">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="869b6-133">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="869b6-133">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="869b6-p106">Indica el número de días que se conservarán los informes de errores del CDR. Cualquier informe con una antigüedad superior al número de días especificado se eliminará automáticamente. Los informes de errores del CDR son informes de diagnóstico que se cargan desde las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="869b6-p106">Indicates the number of days that CDR error reports are kept. Any reports older than the specified number of days will automatically be deleted. CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="869b6-137">Los cmdlets New-CsCdrConfiguration y Set-CsCdrConfiguration incluyen opciones adicionales que no están disponibles en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="869b6-137">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="869b6-138">Vea los temas de ayuda de <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> y <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">set-CsCdrConfiguration</A> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="869b6-138">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="869b6-139">Para crear opciones de configuración de CDR mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="869b6-139">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="869b6-140">En el panel de control de Lync Server, haga clic en **supervisión y archivado**.</span><span class="sxs-lookup"><span data-stu-id="869b6-140">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="869b6-141">En la pestaña **registro detallado de llamadas** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="869b6-141">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="869b6-p108">En el cuadro de diálogo **Seleccionar un sitio**, seleccione el sitio donde desea crear los nuevo valores de configuración. Si el cuadro de diálogo está vacío, significa que ya se han asignado valores de configuración del CDR a todos los sitios (cada sitio solo puede tener una colección de valores). En tal caso, elimine o vuelva a crear la configuración, o simplemente modifique la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="869b6-p108">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created. If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings. Each site is limited to a single such collection. In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="869b6-146">En el cuadro de diálogo **Nueva configuración de registro detallado de llamadas (CDR)**, elija las opciones que desee y haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="869b6-146">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="869b6-147">Para modificar las opciones de configuración de CDR existentes mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="869b6-147">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="869b6-148">En el panel de control de Lync Server, haga clic en **supervisión y archivado**.</span><span class="sxs-lookup"><span data-stu-id="869b6-148">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="869b6-149">Haga doble clic en la colección de valores que desea modificar, o seleccione la colección, y haga clic en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="869b6-149">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="869b6-150">Tenga en cuenta que solo puede modificar una colección a la vez.</span><span class="sxs-lookup"><span data-stu-id="869b6-150">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="869b6-151">Para realizar los mismos cambios en varias colecciones, use el shell de administración de Lync Server en su lugar.</span><span class="sxs-lookup"><span data-stu-id="869b6-151">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="869b6-152">En el cuadro de diálogo **Editar configuración de registro detallado de llamadas (CDR)**, elija las opciones que desee y haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="869b6-152">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="869b6-153">Creación de opciones de configuración de CDR con los cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="869b6-153">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="869b6-154">Puede crear opciones de configuración de CDR también mediante Windows PowerShell y el cmdlet **New-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="869b6-154">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="869b6-155">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="869b6-155">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="869b6-156">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="869b6-156">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="869b6-157">Para crear una nueva colección de valores de configuración del CDR:</span><span class="sxs-lookup"><span data-stu-id="869b6-157">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="869b6-158">Este comando crea una nueva colección de valores de configuración del CDR para el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="869b6-158">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="869b6-159">Para crear una colección de valores de configuración del CDR que deshabiliten el registro detallado de llamadas:</span><span class="sxs-lookup"><span data-stu-id="869b6-159">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="869b6-p111">Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades. Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados. Por ejemplo, para crear una colección de parámetros de configuración de detalle de llamadas que, de forma predeterminada, permita el registro detallado de llamadas, use solo un comando como este:</span><span class="sxs-lookup"><span data-stu-id="869b6-p111">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="869b6-163">Para especificar varios valores de propiedad al crear una nueva colección de valores de configuración del CDR:</span><span class="sxs-lookup"><span data-stu-id="869b6-163">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="869b6-p112">Puede incluir varios parámetros para modificar varios valores de propiedad. Por ejemplo, este comando configura los nuevos valores para conservar los registros detallados de llamadas durante 30 días y los informes de error durante 90 días:</span><span class="sxs-lookup"><span data-stu-id="869b6-p112">You can modify multiple property values by including multiple parameters. For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="869b6-166">Para obtener más información, consulte el tema de ayuda del cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="869b6-166">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

