---
title: 'Lync Server 2013: herramienta de diagnóstico de PRELLAMADA de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e22b542a5840714455d4abdb0a7163e6a8ba748
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="2162b-102">Herramienta de diagnóstico de PRELLAMADA de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2162b-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2162b-103">_**Última modificación del tema:** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="2162b-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="2162b-104">La herramienta de diagnóstico de PRELLAMADA de Lync (PCD) es una aplicación basada en cliente que le permite ver cómo el estado actual de su red puede influir en la calidad del audio en una próxima llamada de telefonía empresarial.</span><span class="sxs-lookup"><span data-stu-id="2162b-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="2162b-105">PCD es más útil en situaciones en las que es probable que el último salto de una red sea el más débil (por ejemplo, con equipos portátiles en una red WiFi pública o usuarios domésticos).</span><span class="sxs-lookup"><span data-stu-id="2162b-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="2162b-106">PCD crea una pequeña secuencia de paquetes que atraviesa esta pierna final de la red.</span><span class="sxs-lookup"><span data-stu-id="2162b-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="2162b-107">Después, la herramienta analiza la secuencia de paquetes para estimar cómo la vibración y la pérdida de este segmento pueden influir en la calidad de la llamada y, a continuación, proporciona un informe.</span><span class="sxs-lookup"><span data-stu-id="2162b-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="2162b-108">Puede ejecutar PCD continuamente en el cliente, incluso mientras se están colocando las llamadas.</span><span class="sxs-lookup"><span data-stu-id="2162b-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="2162b-109">La secuencia de paquetes no tiene un efecto significativo en el ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="2162b-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="2162b-110">**La última versión del PCD, versión 1,1, incluye las siguientes mejoras:**</span><span class="sxs-lookup"><span data-stu-id="2162b-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="2162b-111">Compatibilidad con contraseñas más largas, que ahora pueden tener hasta 127 caracteres</span><span class="sxs-lookup"><span data-stu-id="2162b-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="2162b-112">Diagnósticos adicionales para problemas de inicio de sesión de autenticación</span><span class="sxs-lookup"><span data-stu-id="2162b-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="2162b-113">Mejor compatibilidad para implementaciones híbridas de Lync</span><span class="sxs-lookup"><span data-stu-id="2162b-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="2162b-114">Actualizaciones del selector de credenciales</span><span class="sxs-lookup"><span data-stu-id="2162b-114">Updates to credential picker</span></span>

  - <span data-ttu-id="2162b-115">Mejoras en la estabilidad</span><span class="sxs-lookup"><span data-stu-id="2162b-115">Stability improvements</span></span>

<span data-ttu-id="2162b-116">Agradecemos todos los comentarios.</span><span class="sxs-lookup"><span data-stu-id="2162b-116">We appreciate any feedback.</span></span> <span data-ttu-id="2162b-117">Envía todas las preguntas o problemas de soporte al alias de [comentarios PCD](mailto:pcdfb@microsoft.com) en <pcdfb@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="2162b-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="2162b-118">Este tema incluye las secciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2162b-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="2162b-119">Versiones de PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="2162b-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="2162b-120">Requisitos del sistema de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="2162b-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="2162b-121">Características de PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="2162b-121">Lync PCD Features</span></span>

  - <span data-ttu-id="2162b-122">Ejecución de PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="2162b-122">Running Lync PCD</span></span>

  - <span data-ttu-id="2162b-123">Desinstalar PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="2162b-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="2162b-124">Versiones de PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="2162b-124">Lync PCD Versions</span></span>

<span data-ttu-id="2162b-125">En este tema se describen las siguientes versiones de la herramienta, disponibles para su descarga gratis:</span><span class="sxs-lookup"><span data-stu-id="2162b-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="2162b-126">Aplicación de escritorio de[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)Windows ()</span><span class="sxs-lookup"><span data-stu-id="2162b-126">Windows Desktop App ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="2162b-127">Requisitos del sistema de Lync PCD</span><span class="sxs-lookup"><span data-stu-id="2162b-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2162b-128">PCD requiere que la API Web de comunicaciones unificadas (UCWA) se instale y configure para admitir clientes móviles en la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2162b-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="2162b-129">UCWA se instala con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2162b-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="2162b-130">Requisitos de la aplicación de escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="2162b-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="2162b-131">Cualquier versión del sistema operativo Windows 7 o Windows 8</span><span class="sxs-lookup"><span data-stu-id="2162b-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="2162b-132">Microsoft .NET Framework 4,5 está disponible en[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="2162b-132">Microsoft .NET Framework 4.5 available at [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="2162b-133">Características de PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="2162b-133">Lync PCD Features</span></span>

<span data-ttu-id="2162b-134">El PCD de Lync incluye las características siguientes:</span><span class="sxs-lookup"><span data-stu-id="2162b-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="2162b-135">Ejecutar en forma predeterminada a petición (2 minutos de ráfagas)</span><span class="sxs-lookup"><span data-stu-id="2162b-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="2162b-136">Ejecutar en modo siempre activo (hasta 24 horas en la vista acoplada)</span><span class="sxs-lookup"><span data-stu-id="2162b-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="2162b-137">Vista histórica de las ejecuciones de pruebas</span><span class="sxs-lookup"><span data-stu-id="2162b-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="2162b-138">Diagnosticar errores de inicio de sesión (PCD de Lync para Windows 8 solamente)</span><span class="sxs-lookup"><span data-stu-id="2162b-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="2162b-139">![Captura de pantalla de características de PCD de Lync] (images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Captura de pantalla de características de PCD de Lync")</span><span class="sxs-lookup"><span data-stu-id="2162b-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="2162b-140">Vista gráfica de métricas de red: MOS de red, pérdida de paquetes e vibración de la interrecepción en la vista de pantalla completa y acoplada.</span><span class="sxs-lookup"><span data-stu-id="2162b-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="2162b-141">**Vista pantalla completa**</span><span class="sxs-lookup"><span data-stu-id="2162b-141">**Full screen view**</span></span>

<span data-ttu-id="2162b-142">![Gráficos de resultados de pruebas] de la herramienta de diagnóstico prellamar (images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Gráficos de resultados de pruebas") de la herramienta de diagnóstico prellamar</span><span class="sxs-lookup"><span data-stu-id="2162b-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="2162b-143">**Vista acoplada**</span><span class="sxs-lookup"><span data-stu-id="2162b-143">**Snapped view**</span></span>

<span data-ttu-id="2162b-144">![Resultados de pruebas de uso de la herramienta de diagnóstico PRELLAMADA] (images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Resultados de pruebas de uso de la herramienta de diagnóstico PRELLAMADA")</span><span class="sxs-lookup"><span data-stu-id="2162b-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="2162b-145">Ejecución de PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="2162b-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="2162b-146">Ejecutando la aplicación de escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="2162b-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="2162b-147">Para iniciar el PCD en un sistema Windows 7, seleccione **diagnósticos** de PRELLAMADA en el menú **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="2162b-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="2162b-148">Para iniciar el PCD en un sistema Windows 8, seleccione el icono de la pantalla de inicio o busque "diagnósticos de PRELLAMADA".</span><span class="sxs-lookup"><span data-stu-id="2162b-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="2162b-149">![Icono] de la herramienta de diagnóstico de PRELLAMADA (images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icono") de la herramienta de diagnóstico de PRELLAMADA</span><span class="sxs-lookup"><span data-stu-id="2162b-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="2162b-150">Cuando se inicie la herramienta, seleccione el método preferido para proporcionar credenciales y seleccione el modo de funcionamiento de red en el cuadro de diálogo Opciones de la **herramienta de diagnóstico PRELLAMADA** y, a continuación, seleccione **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="2162b-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="2162b-151">Seleccione el botón **iniciar prueba** para empezar a ejecutar diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="2162b-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="2162b-152">Si seleccionó la opción **usar credenciales de red** , la prueba se iniciará inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="2162b-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="2162b-153">Si seleccionó la opción **permitir especificar mis credenciales** , se abrirá el cuadro de diálogo **seguridad de Windows** .</span><span class="sxs-lookup"><span data-stu-id="2162b-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="2162b-154">Después de escribir sus credenciales, se inicia la prueba.</span><span class="sxs-lookup"><span data-stu-id="2162b-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="2162b-155">Desinstalar PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="2162b-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="2162b-156">Para quitar el PCD de Lync, siga el procedimiento correspondiente a su sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="2162b-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="2162b-157">En un sistema Windows 7, abra el **Panel de control**, seleccione **programas y características**y haga doble clic en diagnósticos de prellamada de **Lync 2013**.</span><span class="sxs-lookup"><span data-stu-id="2162b-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="2162b-158">En un sistema Windows 8, haga clic con el botón derecho en el mosaico \*\*\*\* de PCD y haga clic en desinstalar en la barra de aplicaciones de la parte inferior de la pantalla de inicio.</span><span class="sxs-lookup"><span data-stu-id="2162b-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

