---
title: 'Lync Server 2013: herramienta de diagnóstico de PRELLAMADA de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a63743c634c9e87c743928d7641609ce12c464cb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a><span data-ttu-id="b721f-102">Herramienta de diagnóstico de PRELLAMADA de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b721f-102">Lync PreCall Diagnostics Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b721f-103">_**Última modificación del tema:** 2016-11-04_</span><span class="sxs-lookup"><span data-stu-id="b721f-103">_**Topic Last Modified:** 2016-11-04_</span></span>

<span data-ttu-id="b721f-104">La herramienta de diagnóstico de PRELLAMADA de Lync (PCD) es una aplicación basada en cliente que le permite ver cómo el estado actual de la red puede afectar a la calidad de audio en una próxima llamada de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="b721f-104">The Lync PreCall Diagnostics Tool (PCD) is a client-based application that allows you to see how the current state of your network might impact the audio quality in an upcoming Enterprise Voice call.</span></span>

<span data-ttu-id="b721f-105">PCD es más útil en situaciones en las que es probable que el último salto de una red sea el más débil (por ejemplo, con equipos portátiles de una red WiFi pública o usuarios domésticos).</span><span class="sxs-lookup"><span data-stu-id="b721f-105">PCD is most useful in situations where the last hop of a network is likely to be the weakest (for example, with laptops on a public WiFi network or home users).</span></span> <span data-ttu-id="b721f-106">PCD crea una pequeña secuencia de paquetes que atraviesa esta pierna final de la red.</span><span class="sxs-lookup"><span data-stu-id="b721f-106">PCD creates a small packet stream that traverses this final leg of the network.</span></span> <span data-ttu-id="b721f-107">A continuación, la herramienta analiza la secuencia de paquetes para estimar cómo la vibración y la pérdida a lo largo de esta sección pueden influir en la calidad de la llamada y, a continuación, proporciona un informe.</span><span class="sxs-lookup"><span data-stu-id="b721f-107">The tool then analyzes the packet stream to estimate how the jitter and loss along this leg might impact call quality, and then provides a report.</span></span> <span data-ttu-id="b721f-108">Puede ejecutar PCD continuamente en el cliente, incluso mientras se colocan las llamadas.</span><span class="sxs-lookup"><span data-stu-id="b721f-108">You can run PCD continuously on the client, even while calls are being placed.</span></span> <span data-ttu-id="b721f-109">La secuencia de paquetes no tiene un efecto significativo en el ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="b721f-109">The packet stream does not have a significant effect on bandwidth.</span></span>

<span data-ttu-id="b721f-110">**La versión más reciente del PCD, versión 1,1, incluye las siguientes mejoras:**</span><span class="sxs-lookup"><span data-stu-id="b721f-110">**The latest release of the PCD, version 1.1, includes the following enhancements:**</span></span>

  - <span data-ttu-id="b721f-111">Compatibilidad con contraseñas más largas, que ahora pueden tener hasta 127 caracteres</span><span class="sxs-lookup"><span data-stu-id="b721f-111">Support for longer passwords, which can now be up to 127 characters</span></span>

  - <span data-ttu-id="b721f-112">Diagnósticos adicionales para problemas de inicio de sesión de autenticación</span><span class="sxs-lookup"><span data-stu-id="b721f-112">Additional diagnostics for authentication sign-in issues</span></span>

  - <span data-ttu-id="b721f-113">Mejor compatibilidad con las implementaciones híbridas de Lync</span><span class="sxs-lookup"><span data-stu-id="b721f-113">Better support for Lync hybrid deployments</span></span>

  - <span data-ttu-id="b721f-114">Actualizaciones del selector de credenciales</span><span class="sxs-lookup"><span data-stu-id="b721f-114">Updates to credential picker</span></span>

  - <span data-ttu-id="b721f-115">Mejoras en la estabilidad</span><span class="sxs-lookup"><span data-stu-id="b721f-115">Stability improvements</span></span>

<span data-ttu-id="b721f-116">Agradecemos cualquier comentario.</span><span class="sxs-lookup"><span data-stu-id="b721f-116">We appreciate any feedback.</span></span> <span data-ttu-id="b721f-117">Envíe todas las preguntas o problemas de soporte al alias de [comentarios PCD](mailto:pcdfb@microsoft.com) en <pcdfb@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="b721f-117">Please send all support questions or issues to the [PCD Feedback](mailto:pcdfb@microsoft.com) alias at <pcdfb@microsoft.com>.</span></span>

<span data-ttu-id="b721f-118">En este tema se incluyen las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="b721f-118">This topic includes the following sections:</span></span>

  - <span data-ttu-id="b721f-119">Versiones de PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="b721f-119">Lync PCD Versions</span></span>

  - <span data-ttu-id="b721f-120">Requisitos del sistema para PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="b721f-120">Lync PCD System Requirements</span></span>

  - <span data-ttu-id="b721f-121">Características de PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="b721f-121">Lync PCD Features</span></span>

  - <span data-ttu-id="b721f-122">Ejecutar el PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="b721f-122">Running Lync PCD</span></span>

  - <span data-ttu-id="b721f-123">Desinstalar PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="b721f-123">Uninstalling Lync PCD</span></span>

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a><span data-ttu-id="b721f-124">Versiones de PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="b721f-124">Lync PCD Versions</span></span>

<span data-ttu-id="b721f-125">En este tema se describen las siguientes versiones de la herramienta, disponibles para su descarga gratuita:</span><span class="sxs-lookup"><span data-stu-id="b721f-125">This topic describes the following versions of the tool, available for free download:</span></span>

  - <span data-ttu-id="b721f-126">Aplicación de escritorio de[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)Windows ()</span><span class="sxs-lookup"><span data-stu-id="b721f-126">Windows Desktop App ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))</span></span>

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a><span data-ttu-id="b721f-127">Requisitos del sistema para PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="b721f-127">Lync PCD System Requirements</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b721f-128">PCD requiere que la API Web de comunicaciones unificadas (UCWA) esté instalada y configurada para admitir clientes móviles en la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b721f-128">PCD requires that Unified Communications Web API (UCWA) be installed and configured to support mobile clients in the Lync Server deployment.</span></span> <span data-ttu-id="b721f-129">UCWA se instala con Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b721f-129">UCWA is installed with Lync Server.</span></span>



</div>

<div>

## <a name="windows-desktop-app-requirements"></a><span data-ttu-id="b721f-130">Requisitos de la aplicación de escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="b721f-130">Windows Desktop App Requirements</span></span>

  - <span data-ttu-id="b721f-131">Cualquier edición del sistema operativo Windows 7 o Windows 8</span><span class="sxs-lookup"><span data-stu-id="b721f-131">Any edition of the Windows 7 or Windows 8 operating system</span></span>

  - <span data-ttu-id="b721f-132">Microsoft .NET Framework 4,5 está disponible en[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span><span class="sxs-lookup"><span data-stu-id="b721f-132">Microsoft .NET Framework 4.5 available at [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)</span></span>

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a><span data-ttu-id="b721f-133">Características de PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="b721f-133">Lync PCD Features</span></span>

<span data-ttu-id="b721f-134">El PCD de Lync incluye las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="b721f-134">Lync PCD includes the following features:</span></span>

  - <span data-ttu-id="b721f-135">Ejecutar en valor predeterminado a petición (ráfagas de 2 minutos)</span><span class="sxs-lookup"><span data-stu-id="b721f-135">Run in default On Demand (2 minute bursts)</span></span>

  - <span data-ttu-id="b721f-136">Ejecutar en modo siempre activo (hasta 24 horas en la vista acoplada)</span><span class="sxs-lookup"><span data-stu-id="b721f-136">Run in Always On (up to 24 hours in snapped view) mode</span></span>

  - <span data-ttu-id="b721f-137">Vista histórica de las ejecuciones de prueba</span><span class="sxs-lookup"><span data-stu-id="b721f-137">Historical view of your test runs</span></span>

  - <span data-ttu-id="b721f-138">Diagnóstico de errores de inicio de sesión (PCD de Lync solo para Windows 8)</span><span class="sxs-lookup"><span data-stu-id="b721f-138">Diagnose sign-in failures (Lync PCD for Windows 8 only)</span></span>

<span data-ttu-id="b721f-139">![Captura de pantalla del progreso de inicio de sesión de características de PCD en Lync](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Captura de pantalla del progreso de inicio de sesión de características de PCD en Lync")</span><span class="sxs-lookup"><span data-stu-id="b721f-139">![Lync PCD features Sign in progress screen shot](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Lync PCD features Sign in progress screen shot")</span></span>

  - <span data-ttu-id="b721f-140">Vista gráfica de métricas de red: MOS de red, pérdida de paquetes e vibración de inserción en la vista de pantalla completa y en la vista acoplada.</span><span class="sxs-lookup"><span data-stu-id="b721f-140">Graphical view of network metrics – Network MOS, Packet Loss and Interarrival Jitter in full screen and snapped view.</span></span>

<span data-ttu-id="b721f-141">**Vista de pantalla completa**</span><span class="sxs-lookup"><span data-stu-id="b721f-141">**Full screen view**</span></span>

<span data-ttu-id="b721f-142">![Gráficos de resultados de pruebas de herramienta de diagnóstico precall](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Gráficos de resultados de pruebas de herramienta de diagnóstico precall")</span><span class="sxs-lookup"><span data-stu-id="b721f-142">![PreCall Diagnostic Tool test result graphs](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "PreCall Diagnostic Tool test result graphs")</span></span>

<span data-ttu-id="b721f-143">**Vista acoplada**</span><span class="sxs-lookup"><span data-stu-id="b721f-143">**Snapped view**</span></span>

<span data-ttu-id="b721f-144">![Resultados de la prueba de uso de la herramienta de diagnóstico precall](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Resultados de la prueba de uso de la herramienta de diagnóstico precall")</span><span class="sxs-lookup"><span data-stu-id="b721f-144">![PreCall Diagnostic Tool Utilization test results](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "PreCall Diagnostic Tool Utilization test results")</span></span>

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a><span data-ttu-id="b721f-145">Ejecutar el PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="b721f-145">Running Lync PCD</span></span>

<div>

## <a name="running-windows-desktop-app"></a><span data-ttu-id="b721f-146">Ejecutar la aplicación de escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="b721f-146">Running Windows Desktop App</span></span>

1.  <span data-ttu-id="b721f-147">Para iniciar el PCD en un sistema con Windows 7, seleccione **diagnósticos de PRELLAMADA** del menú **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="b721f-147">To start the PCD on a Windows 7 system, select **PreCall Diagnostics** from the **Start** menu.</span></span>
    
    <span data-ttu-id="b721f-148">Para iniciar PCD en un sistema con Windows 8, seleccione el icono de la pantalla Inicio o busque "diagnósticos de PRELLAMADA".</span><span class="sxs-lookup"><span data-stu-id="b721f-148">To start the PCD on a Windows 8 system, select the icon on your Start screen, or search for “PreCall Diagnostics.”</span></span>
    
    <span data-ttu-id="b721f-149">![Icono de la herramienta de diagnóstico precall](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icono de la herramienta de diagnóstico precall")</span><span class="sxs-lookup"><span data-stu-id="b721f-149">![PreCall Diagnostic tool icon](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "PreCall Diagnostic tool icon")</span></span>

2.  <span data-ttu-id="b721f-150">Cuando se inicie la herramienta, seleccione el método preferido para suministrar credenciales y seleccione el modo de funcionamiento de red en el cuadro de diálogo Opciones de la **herramienta de diagnóstico PRELLAMADA** y, a continuación, seleccione **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="b721f-150">When the tool starts, select your preferred method of providing credentials and select the network operating mode in the **PreCall Diagnostics Tool Options** dialog box, then select **OK**:</span></span>

3.  <span data-ttu-id="b721f-151">Seleccione el botón **iniciar prueba** para empezar a ejecutar diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="b721f-151">Select the **Start Test** button to start running diagnostics.</span></span>
    
    <span data-ttu-id="b721f-152">Si seleccionó la opción **usar credenciales de red** , la prueba comienza inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="b721f-152">If you selected the **Use network credentials** option, the test begins immediately.</span></span>
    
    <span data-ttu-id="b721f-153">Si seleccionó la opción **permitir especificar mis credenciales** , se abrirá el cuadro de diálogo **seguridad de Windows** .</span><span class="sxs-lookup"><span data-stu-id="b721f-153">If you selected the **Let me enter my credentials** option, the **Windows Security** dialog box opens.</span></span> <span data-ttu-id="b721f-154">Después de escribir las credenciales, la prueba se inicia.</span><span class="sxs-lookup"><span data-stu-id="b721f-154">After you enter your credentials, the test starts.</span></span>

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a><span data-ttu-id="b721f-155">Desinstalar PCD de Lync</span><span class="sxs-lookup"><span data-stu-id="b721f-155">Uninstalling Lync PCD</span></span>

<span data-ttu-id="b721f-156">Para quitar el PCD de Lync, siga el procedimiento para su sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="b721f-156">To remove Lync PCD, follow the procedure for your operating system:</span></span>

  - <span data-ttu-id="b721f-157">En un sistema Windows 7, abra el **Panel de control**, seleccione **programas y características**y, a continuación, haga doble clic en **diagnósticos de PRELLAMADA de Lync 2013**.</span><span class="sxs-lookup"><span data-stu-id="b721f-157">On a Windows 7 system, open the **Control Panel**, select **Programs and Features**, and double-click **Lync 2013 PreCall Diagnostics**.</span></span>

  - <span data-ttu-id="b721f-158">En un sistema Windows 8, haga clic con el botón secundario en el icono de PCD y haga clic en **desinstalar** desde la barra de aplicaciones en la parte inferior de la pantalla Inicio.</span><span class="sxs-lookup"><span data-stu-id="b721f-158">On a Windows 8 system, right-click on the PCD tile and click **Uninstall** from the app bar at the bottom of the start screen.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

