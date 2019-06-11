---
title: 'Lync Server 2013: visualización y análisis de informes de servidor de supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc942c887175bacb0047c5d82d1ad9a89c18ef5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="93b43-102">Ver y analizar informes del servidor de supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93b43-102">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93b43-103">_**Última modificación del tema:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="93b43-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="93b43-104">Los informes del servidor de supervisión proporcionan varias medidas diferentes de calidad de voz para supervisar el QoE que se envía a los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="93b43-104">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="93b43-105">Además, Monitoring Server incluye varios informes integrados que su organización puede usar para vigilar las tendencias de calidad de uso y multimedia en la red de su organización y solucionar problemas de calidad de medios que surjan.</span><span class="sxs-lookup"><span data-stu-id="93b43-105">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="93b43-106">Una parte fundamental de mantener los informes del servidor de supervisión interesantes para las operaciones diarias y semanales es ver y analizar los informes de calidad de los medios, en concreto:</span><span class="sxs-lookup"><span data-stu-id="93b43-106">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="93b43-107">Resumen/informes de tendencias de QoE</span><span class="sxs-lookup"><span data-stu-id="93b43-107">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="93b43-108">Informes de rendimiento de QoE</span><span class="sxs-lookup"><span data-stu-id="93b43-108">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="93b43-109">Ver informes desde el servidor de supervisión</span><span class="sxs-lookup"><span data-stu-id="93b43-109">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="93b43-110">Desde un explorador Web, busque los servidores que hospedan SQL Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="93b43-110">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="93b43-111">Ver los informes necesarios en la pantalla del explorador.</span><span class="sxs-lookup"><span data-stu-id="93b43-111">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="93b43-112">Faculta Exporte un informe seleccionando la opción de exportación y el formato de salida requerido.</span><span class="sxs-lookup"><span data-stu-id="93b43-112">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="93b43-113">Configurar grabación de detalles de llamadas (CDR)</span><span class="sxs-lookup"><span data-stu-id="93b43-113">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="93b43-114">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene permisos equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que implementó Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93b43-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="93b43-115">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93b43-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="93b43-116">En la barra de navegación de la izquierda, haga clic en **Supervisión y archivado** y en **Registro de detallado de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="93b43-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="93b43-117">En la página **Registro detallado de llamadas**, haga clic en el sitio apropiado de la tabla, en **Editar** y en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="93b43-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="93b43-118">Para activar la purga, seleccione **Habilitar purgado para supervisar servidores**.</span><span class="sxs-lookup"><span data-stu-id="93b43-118">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="93b43-119">En **mantener grabaciones de detalles de llamadas para una duración máxima (días):** Seleccione el número máximo de días que deben conservarse las grabaciones de llamadas detalladas.</span><span class="sxs-lookup"><span data-stu-id="93b43-119">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="93b43-120">En **Conservar los datos de los informes de errores durante el período de duración máximo (días):**, seleccione el número máximo de días que desea retener los registros de error.</span><span class="sxs-lookup"><span data-stu-id="93b43-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="93b43-121">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="93b43-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="93b43-122">Configurar el QoE</span><span class="sxs-lookup"><span data-stu-id="93b43-122">Configure QoE</span></span>

1.  <span data-ttu-id="93b43-123">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="93b43-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="93b43-124">Para más información, consulte Delegate Setup Permissions.</span><span class="sxs-lookup"><span data-stu-id="93b43-124">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="93b43-125">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93b43-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="93b43-126">En la barra de navegación izquierda, haga clic en **Configuración y archivado** y, luego, en **Datos sobre la calidad de la experiencia**.</span><span class="sxs-lookup"><span data-stu-id="93b43-126">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="93b43-127">En la página **Datos sobre la calidad de la experiencia**, haga clic en el sitio apropiado de la tabla, haga clic en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="93b43-127">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="93b43-128">Para activar la purga, seleccione **Habilitar purgado para supervisar servidores**.</span><span class="sxs-lookup"><span data-stu-id="93b43-128">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="93b43-129">En **mantener grabaciones de detalles de llamadas para duración máxima (días):** Seleccione el número máximo de días que se deben conservar los datos de QoE.</span><span class="sxs-lookup"><span data-stu-id="93b43-129">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="93b43-130">Haga clic en Confirmar.</span><span class="sxs-lookup"><span data-stu-id="93b43-130">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="93b43-131">Cambiar la Directiva de archivado</span><span class="sxs-lookup"><span data-stu-id="93b43-131">Change the archiving policy</span></span>

1.  <span data-ttu-id="93b43-132">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="93b43-132">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="93b43-133">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93b43-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="93b43-134">En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Directiva de archivado**.</span><span class="sxs-lookup"><span data-stu-id="93b43-134">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="93b43-135">Haga clic en **Global** en la lista de directivas, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="93b43-135">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="93b43-136">En **Editar directiva de archivado: global**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="93b43-136">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="93b43-137">Para habilitar o deshabilitar el archivado interno para la implementación, Active o desactive la casilla de verificación **archivar comunicaciones internas** .</span><span class="sxs-lookup"><span data-stu-id="93b43-137">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="93b43-138">Para habilitar o deshabilitar el archivado externo para la implementación, Active o desactive la casilla **archivar comunicaciones externas** .</span><span class="sxs-lookup"><span data-stu-id="93b43-138">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="93b43-139">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="93b43-139">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="93b43-140">Aplicar una directiva de archivado a un usuario</span><span class="sxs-lookup"><span data-stu-id="93b43-140">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="93b43-141">Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="93b43-141">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="93b43-142">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="93b43-142">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="93b43-143">En la barra de navegación izquierda, haga clic en **Usuarios** y, luego, busque la cuenta de usuario que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="93b43-143">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="93b43-144">En la tabla donde se enumeran los resultados de la búsqueda, haga clic en la cuenta de usuario, en **Editar** y, luego, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="93b43-144">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="93b43-145">En **Editar usuario de Lync Server** , en **Directiva**de archivado, seleccione la Directiva de usuario de archivado que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="93b43-145">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="93b43-146">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="93b43-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="93b43-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="93b43-147">See Also</span></span>


[<span data-ttu-id="93b43-148">Usar informes de supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93b43-148">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="93b43-149">Informe de rendimiento del servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93b43-149">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="93b43-150">Informe de comparación de calidad multimedia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93b43-150">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

