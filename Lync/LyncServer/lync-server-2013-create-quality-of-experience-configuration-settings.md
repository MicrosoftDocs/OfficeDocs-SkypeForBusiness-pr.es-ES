---
title: 'Lync Server 2013: crear opciones de configuración de la calidad de la experiencia'
description: 'Lync Server 2013: crear opciones de configuración de la calidad de la experiencia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279265f396fc8fcbfba80d195fc587924a2979f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562196"
---
# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="5299f-103">Crear opciones de configuración de la calidad de la experiencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5299f-103">Create Quality of Experience configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5299f-104">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5299f-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5299f-p101">Las métricas de calidad de la experiencia (QoE) realizan un seguimiento de la calidad de las llamadas de audio y vídeo que se han efectuado en la organización, incluido el número de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes). Esta información se almacena en una base de datos independiente de otras estadísticas, como los registros de detalles de llamadas, lo que permite activar y desactivar las métricas QoE de manera independiente de otros datos registrados.</span><span class="sxs-lookup"><span data-stu-id="5299f-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="5299f-107">Al instalar Microsoft Lync Server 2013, se crea una única colección global de opciones de configuración de QoE.</span><span class="sxs-lookup"><span data-stu-id="5299f-107">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="5299f-108">Los administradores pueden también crear una configuración personalizada en el ámbito de sitio.</span><span class="sxs-lookup"><span data-stu-id="5299f-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="5299f-109">Cuando se usa esta configuración en el ámbito del sitio, predomina sobre la configuración global.</span><span class="sxs-lookup"><span data-stu-id="5299f-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="5299f-110">Por ejemplo, si crea una configuración de ámbito de sitio para el sitio de Redmond, se utilizará esa configuración (en lugar de la configuración global) para administrar el QoE en Redmond.</span><span class="sxs-lookup"><span data-stu-id="5299f-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>

<span data-ttu-id="5299f-111">Las opciones de configuración de QoE se pueden crear mediante el panel de control de Lync Server o el cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="5299f-111">QoE configuration settings can be created by using either Lync Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span> <span data-ttu-id="5299f-112">Si está usando el panel de control de Lync Server para crear una nueva configuración, estarán disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="5299f-112">If you are using Lync Server Control Panel to create new settings the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5299f-113">Valor de IU</span><span class="sxs-lookup"><span data-stu-id="5299f-113">UI Setting</span></span></th>
<th><span data-ttu-id="5299f-114">Parámetro de PowerShell</span><span class="sxs-lookup"><span data-stu-id="5299f-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="5299f-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="5299f-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5299f-116">Name</span><span class="sxs-lookup"><span data-stu-id="5299f-116">Name</span></span></p></td>
<td><p><span data-ttu-id="5299f-117">Identidad</span><span class="sxs-lookup"><span data-stu-id="5299f-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="5299f-118">Identificador único de la configuración que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="5299f-118">Unique identifier for the settings to be created.</span></span> <span data-ttu-id="5299f-119">Las opciones de configuración de QoE solo se pueden crear en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="5299f-119">QoE configuration settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5299f-120">Habilitar la supervisión de los datos de QoE</span><span class="sxs-lookup"><span data-stu-id="5299f-120">Enable monitoring of QoE data</span></span></p></td>
<td><p><span data-ttu-id="5299f-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="5299f-121">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="5299f-122">Especifica si los registros QoE se recopilarán y guardarán en la base de datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="5299f-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5299f-123">Habilitar la depuración de datos de QoE</span><span class="sxs-lookup"><span data-stu-id="5299f-123">Enable purging of QoE data</span></span></p></td>
<td><p><span data-ttu-id="5299f-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="5299f-124">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="5299f-125">Especifica si los registros se purgarán una vez transcurrida la duración definida en la propiedad <strong>conservar datos de QoE durante el período de duración máximo (días)</strong> .</span><span class="sxs-lookup"><span data-stu-id="5299f-125">Specifies whether records will be purged after the duration defined in the <strong>Keep QoE data for a maximum duration (days)</strong> property has elapsed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5299f-126">Mantener los datos de QoE durante la duración máxima (días)</span><span class="sxs-lookup"><span data-stu-id="5299f-126">Keep QoE data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="5299f-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="5299f-127">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="5299f-128">Número de días que se almacenarán los datos de QoE antes de que se purguen de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5299f-128">Number of days QoE data will be stored before being purged from the database.</span></span> <span data-ttu-id="5299f-129">Este valor se omite si la depuración está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="5299f-129">This value is ignored if purging is disabled.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5299f-130">El cmdlet New-CsQoEConfiguration incluye opciones adicionales que no están disponibles en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5299f-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="5299f-131">Para obtener más información, vea el tema de ayuda <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="5299f-131">For more information, see the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> help topic.</span></span>



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="5299f-132">Para crear opciones de configuración de QoE mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="5299f-132">To create QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5299f-133">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5299f-133">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="5299f-134">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5299f-134">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="5299f-135">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5299f-135">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5299f-136">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5299f-136">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5299f-137">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Datos sobre la calidad de la experiencia**.</span><span class="sxs-lookup"><span data-stu-id="5299f-137">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="5299f-138">En la página **datos de calidad de la experiencia** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5299f-138">On the **Quality of Experience Data** page, click **New**.</span></span>

5.  <span data-ttu-id="5299f-139">En **seleccionar un sitio**, haga clic en el sitio al que se va a aplicar la Directiva y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5299f-139">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>

6.  <span data-ttu-id="5299f-140">En **nueva configuración de calidad de la experiencia**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5299f-140">In **New Quality of Experience Setting**, do the following:</span></span>
    
      - <span data-ttu-id="5299f-141">Seleccione **activar la supervisión de los datos de QoE** para activar la supervisión.</span><span class="sxs-lookup"><span data-stu-id="5299f-141">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
      - <span data-ttu-id="5299f-142">Seleccione **Habilitar la purga de los datos de QoE** para activar la depuración.</span><span class="sxs-lookup"><span data-stu-id="5299f-142">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
      - <span data-ttu-id="5299f-143">En **conservar QoE durante la duración máxima (días)**, seleccione el número máximo de días que se deben conservar los registros de QoE.</span><span class="sxs-lookup"><span data-stu-id="5299f-143">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>

7.  <span data-ttu-id="5299f-144">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="5299f-144">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5299f-145">Creación de opciones de configuración de QoE con los cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5299f-145">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5299f-146">Puede crear opciones de configuración de QoE con Windows PowerShell y el cmdlet New-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="5299f-146">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="5299f-147">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5299f-147">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5299f-148">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="5299f-148">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="5299f-149">Para crear una nueva colección de opciones de configuración de QoE</span><span class="sxs-lookup"><span data-stu-id="5299f-149">To create a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="5299f-150">Este comando crea una nueva colección de opciones de configuración de QoE que se aplican al sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="5299f-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="5299f-151">Para crear una nueva colección de opciones de configuración de QoE cuando la supervisión de QoE está deshabilitada</span><span class="sxs-lookup"><span data-stu-id="5299f-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="5299f-152">Dado que, en el comando anterior, no se especificaron parámetros (además del parámetro de identidad obligatorio), la nueva colección de valores de configuración usará los valores predeterminados para todas sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="5299f-152">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="5299f-153">Para crear una configuración que use otros valores de propiedad, basta con incluir el parámetro y el valor correspondiente adecuados.</span><span class="sxs-lookup"><span data-stu-id="5299f-153">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="5299f-154">Por ejemplo, para crear una colección de opciones de configuración de calidad de la experiencia que, de forma predeterminada, permitir la grabación de QoE, use un comando como este:</span><span class="sxs-lookup"><span data-stu-id="5299f-154">For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="5299f-155">Para especificar varios valores de propiedad al crear una nueva colección de opciones de configuración de QoE</span><span class="sxs-lookup"><span data-stu-id="5299f-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="5299f-156">Puede incluir varios parámetros para varios valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="5299f-156">You can multiple property values by including multiple parameters.</span></span> <span data-ttu-id="5299f-157">Por ejemplo, este comando configura la nueva configuración para conservar los datos de QoE durante 30 días y para depurar los datos antiguos a las 3:00 A.M.:</span><span class="sxs-lookup"><span data-stu-id="5299f-157">For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

<span data-ttu-id="5299f-158">Para obtener más información, consulte el tema de ayuda del cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="5299f-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

