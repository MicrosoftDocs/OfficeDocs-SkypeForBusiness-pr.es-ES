---
title: Preguntas más frecuentes de la herramienta stress and performance de Lync Server 2013
description: Preguntas más frecuentes sobre la herramienta stress and performance de Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 716325390bc33df209be3bdc67ed8b6cd7d1ec30
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573546"
---
# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="cd777-103">Preguntas más frecuentes de la herramienta stress and performance de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd777-103">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd777-104">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="cd777-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="cd777-105">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="cd777-105">Frequently Asked Questions</span></span>

<span data-ttu-id="cd777-106">Estas son algunas de las preguntas más frecuentes sobre la herramienta de esfuerzo y rendimiento de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd777-106">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="cd777-107">¿Puedo ejecutar LyncPerfTool.exe en producción?</span><span class="sxs-lookup"><span data-stu-id="cd777-107">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="cd777-108">No se recomienda esto.</span><span class="sxs-lookup"><span data-stu-id="cd777-108">We do not recommend this.</span></span> <span data-ttu-id="cd777-109">Esta herramienta afectará al rendimiento del servidor, la seguridad y la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="cd777-109">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="cd777-110">Estoy registrando en mis usuarios por primera vez.</span><span class="sxs-lookup"><span data-stu-id="cd777-110">I am logging on my users for the first time.</span></span> <span data-ttu-id="cd777-111">¿Por qué los servidores se ejecutan con una carga tan alta?</span><span class="sxs-lookup"><span data-stu-id="cd777-111">Why are the servers running at such high load?</span></span>

<span data-ttu-id="cd777-112">La primera vez que los usuarios inician sesión, hay otras operaciones que se producen.</span><span class="sxs-lookup"><span data-stu-id="cd777-112">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="cd777-113">Como resultado, se degradará el rendimiento del servidor back-end de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cd777-113">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="cd777-114">Le recomendamos que ejecute una breve prueba que inicie sesión en todos los usuarios y, a continuación, reinicie los clientes antes de medir los resultados.</span><span class="sxs-lookup"><span data-stu-id="cd777-114">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="cd777-115">No se admiten más de 12 sesiones de inicio de sesión de usuario simultáneas por segundo, pero esto depende de la configuración de hardware.</span><span class="sxs-lookup"><span data-stu-id="cd777-115">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="cd777-116">Los clientes se están quedando sin memoria.</span><span class="sxs-lookup"><span data-stu-id="cd777-116">My clients are running out of memory.</span></span> <span data-ttu-id="cd777-117">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="cd777-117">What should I do?</span></span>

<span data-ttu-id="cd777-118">Si los clientes se están quedando sin memoria, debe reducir el número de usuarios por equipo.</span><span class="sxs-lookup"><span data-stu-id="cd777-118">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="cd777-119">Mis clientes tienen un 100 por ciento de CPU todo el tiempo.</span><span class="sxs-lookup"><span data-stu-id="cd777-119">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="cd777-120">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="cd777-120">What should I do?</span></span>

<span data-ttu-id="cd777-121">Si los clientes están ejecutando una CPU muy alta después de que todos los usuarios hayan iniciado sesión, debe reducir el número de usuarios por equipo.</span><span class="sxs-lookup"><span data-stu-id="cd777-121">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="cd777-122">Los picos de CPU elevados son aceptables, pero si se mantiene, es necesario reducir la carga.</span><span class="sxs-lookup"><span data-stu-id="cd777-122">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="cd777-123">¿Puedo ejecutar la herramienta en el servidor en sí?</span><span class="sxs-lookup"><span data-stu-id="cd777-123">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="cd777-124">No.</span><span class="sxs-lookup"><span data-stu-id="cd777-124">No.</span></span> <span data-ttu-id="cd777-125">Este escenario no es compatible y puede producirse un error debido a un error de coincidencia binaria.</span><span class="sxs-lookup"><span data-stu-id="cd777-125">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="cd777-126">Además, como el punto es medir el consumo de recursos en el servidor, ejecutar la herramienta hará que las medidas no tengan sentido.</span><span class="sxs-lookup"><span data-stu-id="cd777-126">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="cd777-127">¿Puedo ejecutar LyncPerfTool.exe en un servidor virtual o en Microsoft Hyper-V Server 2008/2012?</span><span class="sxs-lookup"><span data-stu-id="cd777-127">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="cd777-128">Sí.</span><span class="sxs-lookup"><span data-stu-id="cd777-128">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="cd777-129">¿Qué significa MPOP?</span><span class="sxs-lookup"><span data-stu-id="cd777-129">What does MPOP mean?</span></span>

<span data-ttu-id="cd777-130">MPOP representa varios puntos de presencia.</span><span class="sxs-lookup"><span data-stu-id="cd777-130">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="cd777-131">Se pretende simular el escenario en el que los usuarios inician sesión en Lync 2013 desde varios equipos.</span><span class="sxs-lookup"><span data-stu-id="cd777-131">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="cd777-132">Tenga en cuenta que en LyncPerfTool.exe, cada punto de conexión usa el perfil predeterminado (es decir, el perfil no se divide entre los dos puntos de presencia).</span><span class="sxs-lookup"><span data-stu-id="cd777-132">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="cd777-133">Comencé LyncPerfTool.exe pero no ocurre nada.</span><span class="sxs-lookup"><span data-stu-id="cd777-133">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="cd777-134">¿Qué sucede?</span><span class="sxs-lookup"><span data-stu-id="cd777-134">What’s going on?</span></span>

<span data-ttu-id="cd777-135">Compruebe el contador de extremos activos totales en los clientes para ver si los usuarios se conectan.</span><span class="sxs-lookup"><span data-stu-id="cd777-135">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="cd777-136">Si los usuarios no se conectan, Compruebe la configuración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd777-136">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="cd777-137">Este problema suele producirse porque el nombre del servidor, el prefijo de usuario o la contraseña son incorrectos.</span><span class="sxs-lookup"><span data-stu-id="cd777-137">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="cd777-138">Tenga en cuenta que los clientes externos deben especificar el proxy de acceso como el valor TargetServer.</span><span class="sxs-lookup"><span data-stu-id="cd777-138">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="cd777-139">Compruebe el puerto en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="cd777-139">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="cd777-140">¿Cómo puedo saber si algo está ocurriendo?</span><span class="sxs-lookup"><span data-stu-id="cd777-140">How do I know something is happening?</span></span>

<span data-ttu-id="cd777-141">Los distintos contadores de rendimiento de LyncPerfTool indican si los usuarios están conectando y realizando acciones.</span><span class="sxs-lookup"><span data-stu-id="cd777-141">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="cd777-142">Sin embargo, una forma sencilla de comprobar es iniciar sesión en una de las cuentas con Lync 2013 y realizar la acción deseada.</span><span class="sxs-lookup"><span data-stu-id="cd777-142">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="cd777-143">Tengo instaladas las herramientas de planeación de capacidad de Live Communications Server 2007 R2 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="cd777-143">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="cd777-144">¿Es correcto?</span><span class="sxs-lookup"><span data-stu-id="cd777-144">Is that OK?</span></span>

<span data-ttu-id="cd777-145">No.</span><span class="sxs-lookup"><span data-stu-id="cd777-145">No.</span></span> <span data-ttu-id="cd777-146">Hay problemas de interoperabilidad y debe desinstalar todas las versiones anteriores de este producto.</span><span class="sxs-lookup"><span data-stu-id="cd777-146">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="cd777-147">¿Las herramientas de estrés y rendimiento configuran la topología del servidor de información de llamadas de CAA?</span><span class="sxs-lookup"><span data-stu-id="cd777-147">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="cd777-148">No.</span><span class="sxs-lookup"><span data-stu-id="cd777-148">No.</span></span> <span data-ttu-id="cd777-149">Las herramientas solo crean usuarios, contactos y listas de distribución, y simulan la carga de usuarios.</span><span class="sxs-lookup"><span data-stu-id="cd777-149">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="cd777-150">¿Cuál es el número máximo de usuarios que admiten las herramientas?</span><span class="sxs-lookup"><span data-stu-id="cd777-150">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="cd777-151">Hemos creado hasta un total de 80.000 usuarios y pruebas ejecutadas que totalizan 30.000 usuarios con estas herramientas.</span><span class="sxs-lookup"><span data-stu-id="cd777-151">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="cd777-152">Se recomienda un máximo de 120.000 usuarios, aunque las limitaciones técnicas permiten un valor superior, según el hardware del servidor y el cliente disponibles.</span><span class="sxs-lookup"><span data-stu-id="cd777-152">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

