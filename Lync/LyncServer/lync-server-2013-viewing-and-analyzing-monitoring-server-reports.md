---
title: 'Lync Server 2013: visualización y análisis de informes del servidor de supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8bf51f2836ed7e4bd81fc66aea2ea8755086298
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="82c8e-102">Ver y analizar los informes del servidor de supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82c8e-102">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82c8e-103">_**Última modificación del tema:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="82c8e-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="82c8e-104">Los informes del servidor de supervisión proporcionan distintas medidas de calidad de voz para supervisar el QoE que se entrega a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="82c8e-104">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="82c8e-105">Además, el servidor de supervisión incluye varios informes integrados que su organización puede usar para ver las tendencias de calidad de medios y de uso en la red de su organización y solucionar los problemas de calidad de los medios que surjan.</span><span class="sxs-lookup"><span data-stu-id="82c8e-105">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="82c8e-106">Una parte principal de la conservación de informes del servidor de supervisión interesante para las operaciones diarias y semanales es ver y analizar los informes de calidad de los medios, en particular:</span><span class="sxs-lookup"><span data-stu-id="82c8e-106">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="82c8e-107">Informe de tendencias/Resumen de QoE</span><span class="sxs-lookup"><span data-stu-id="82c8e-107">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="82c8e-108">Informes de rendimiento de QoE</span><span class="sxs-lookup"><span data-stu-id="82c8e-108">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="82c8e-109">Ver informes desde el servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="82c8e-109">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="82c8e-110">En un explorador Web, busque los servidores que hospedan SQL Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="82c8e-110">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="82c8e-111">Vea los informes necesarios en la pantalla del explorador.</span><span class="sxs-lookup"><span data-stu-id="82c8e-111">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="82c8e-112">Opcional Exporte un informe seleccionando la opción de exportación y el formato de salida necesario.</span><span class="sxs-lookup"><span data-stu-id="82c8e-112">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="82c8e-113">Configuración del registro de detalles de llamadas (CDR)</span><span class="sxs-lookup"><span data-stu-id="82c8e-113">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="82c8e-114">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga permisos equivalentes), o esté asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que se implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="82c8e-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="82c8e-115">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82c8e-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="82c8e-116">En la barra de navegación de la izquierda, haga clic en **Supervisión y archivado** y en **Registro de detallado de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="82c8e-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="82c8e-117">En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la tabla, en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="82c8e-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="82c8e-118">Para activar la purga, seleccione **Habilitar depuración para los servidores de supervisión**.</span><span class="sxs-lookup"><span data-stu-id="82c8e-118">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="82c8e-119">En **conservar grabaciones de detalles de llamadas durante un máximo de (días):,** Seleccione el número máximo de días que se conservarán los registros detallados de llamadas.</span><span class="sxs-lookup"><span data-stu-id="82c8e-119">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="82c8e-120">En **Conservar los datos de los informes de errores durante el período de duración máximo (días):**, seleccione el número máximo de días que desea retener los registros de error.</span><span class="sxs-lookup"><span data-stu-id="82c8e-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="82c8e-121">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="82c8e-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="82c8e-122">Configurar QoE</span><span class="sxs-lookup"><span data-stu-id="82c8e-122">Configure QoE</span></span>

1.  <span data-ttu-id="82c8e-123">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="82c8e-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="82c8e-124">Para obtener más información, consulte Delegate Setup Permissions.</span><span class="sxs-lookup"><span data-stu-id="82c8e-124">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="82c8e-125">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82c8e-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="82c8e-126">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Datos sobre la calidad de la experiencia**.</span><span class="sxs-lookup"><span data-stu-id="82c8e-126">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="82c8e-127">En la página **Calidad de la experiencia**, haga clic en el sitio apropiado de la tabla, haga clic en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="82c8e-127">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="82c8e-128">Para activar la purga, seleccione **Habilitar depuración para los servidores de supervisión**.</span><span class="sxs-lookup"><span data-stu-id="82c8e-128">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="82c8e-129">En **conservar grabaciones de detalles de llamadas durante un máximo de (días):,** Seleccione el número máximo de días que se deben conservar los datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="82c8e-129">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="82c8e-130">Haga clic en  Confirmar .</span><span class="sxs-lookup"><span data-stu-id="82c8e-130">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="82c8e-131">Cambiar la Directiva de archivado</span><span class="sxs-lookup"><span data-stu-id="82c8e-131">Change the archiving policy</span></span>

1.  <span data-ttu-id="82c8e-132">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="82c8e-132">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="82c8e-133">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82c8e-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="82c8e-134">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, a continuación, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="82c8e-134">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="82c8e-135">Haga clic en **Global** en la lista de directivas, en **Editar** y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="82c8e-135">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="82c8e-136">En **Editar directiva de archivado - Global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="82c8e-136">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="82c8e-137">Para habilitar o deshabilitar el archivado interno para la implementación, Active o desactive la casilla **archivar comunicaciones internas** .</span><span class="sxs-lookup"><span data-stu-id="82c8e-137">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="82c8e-138">Para habilitar o deshabilitar el archivado externo para la implementación, Active o desactive la casilla de verificación **archivar comunicaciones externas** .</span><span class="sxs-lookup"><span data-stu-id="82c8e-138">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="82c8e-139">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="82c8e-139">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="82c8e-140">Aplicar una directiva de archivado a un usuario</span><span class="sxs-lookup"><span data-stu-id="82c8e-140">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="82c8e-141">Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="82c8e-141">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="82c8e-142">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="82c8e-142">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="82c8e-143">En la barra de navegación izquierda, haga clic en  \*\*Usuarios \*\* y, a continuación, busque en la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="82c8e-143">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="82c8e-144">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en  \*\*Editar \*\* y, a continuación, en  \*\*Mostrar detalles \*\*.</span><span class="sxs-lookup"><span data-stu-id="82c8e-144">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="82c8e-145">En **Editar usuario de Lync Server** en **Directiva de archivado**, seleccione la Directiva de usuario de archivado que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="82c8e-145">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="82c8e-146">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="82c8e-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="82c8e-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="82c8e-147">See Also</span></span>


[<span data-ttu-id="82c8e-148">Uso de informes de supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82c8e-148">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="82c8e-149">Informe de rendimiento del servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82c8e-149">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="82c8e-150">Informe de comparación de calidad de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82c8e-150">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

