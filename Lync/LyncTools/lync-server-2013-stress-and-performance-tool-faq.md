---
title: Preguntas más frecuentes de la herramienta stress and performance de Lync Server 2013
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
ms.openlocfilehash: 445448633bc35b8071455ccd0c8e6ff93c3862b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509217"
---
# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="8ff7d-102">Preguntas más frecuentes de la herramienta stress and performance de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ff7d-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ff7d-103">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="8ff7d-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="8ff7d-104">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="8ff7d-104">Frequently Asked Questions</span></span>

<span data-ttu-id="8ff7d-105">Estas son algunas de las preguntas más frecuentes sobre la herramienta de esfuerzo y rendimiento de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="8ff7d-106">¿Puedo ejecutar LyncPerfTool.exe en producción?</span><span class="sxs-lookup"><span data-stu-id="8ff7d-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="8ff7d-107">No se recomienda esto.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-107">We do not recommend this.</span></span> <span data-ttu-id="8ff7d-108">Esta herramienta afectará al rendimiento del servidor, la seguridad y la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="8ff7d-109">Estoy registrando en mis usuarios por primera vez.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="8ff7d-110">¿Por qué los servidores se ejecutan con una carga tan alta?</span><span class="sxs-lookup"><span data-stu-id="8ff7d-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="8ff7d-111">La primera vez que los usuarios inician sesión, hay otras operaciones que se producen.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="8ff7d-112">Como resultado, se degradará el rendimiento del servidor back-end de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="8ff7d-113">Le recomendamos que ejecute una breve prueba que inicie sesión en todos los usuarios y, a continuación, reinicie los clientes antes de medir los resultados.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="8ff7d-114">No se admiten más de 12 sesiones de inicio de sesión de usuario simultáneas por segundo, pero esto depende de la configuración de hardware.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="8ff7d-115">Los clientes se están quedando sin memoria.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-115">My clients are running out of memory.</span></span> <span data-ttu-id="8ff7d-116">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="8ff7d-116">What should I do?</span></span>

<span data-ttu-id="8ff7d-117">Si los clientes se están quedando sin memoria, debe reducir el número de usuarios por equipo.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="8ff7d-118">Mis clientes tienen un 100 por ciento de CPU todo el tiempo.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="8ff7d-119">¿Qué tengo que hacer?</span><span class="sxs-lookup"><span data-stu-id="8ff7d-119">What should I do?</span></span>

<span data-ttu-id="8ff7d-120">Si los clientes están ejecutando una CPU muy alta después de que todos los usuarios hayan iniciado sesión, debe reducir el número de usuarios por equipo.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="8ff7d-121">Los picos de CPU elevados son aceptables, pero si se mantiene, es necesario reducir la carga.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="8ff7d-122">¿Puedo ejecutar la herramienta en el servidor en sí?</span><span class="sxs-lookup"><span data-stu-id="8ff7d-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="8ff7d-123">No.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-123">No.</span></span> <span data-ttu-id="8ff7d-124">Este escenario no es compatible y puede producirse un error debido a un error de coincidencia binaria.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="8ff7d-125">Además, como el punto es medir el consumo de recursos en el servidor, ejecutar la herramienta hará que las medidas no tengan sentido.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="8ff7d-126">¿Puedo ejecutar LyncPerfTool.exe en un servidor virtual o en Microsoft Hyper-V Server 2008/2012?</span><span class="sxs-lookup"><span data-stu-id="8ff7d-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="8ff7d-127">Sí.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="8ff7d-128">¿Qué significa MPOP?</span><span class="sxs-lookup"><span data-stu-id="8ff7d-128">What does MPOP mean?</span></span>

<span data-ttu-id="8ff7d-129">MPOP representa varios puntos de presencia.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="8ff7d-130">Se pretende simular el escenario en el que los usuarios inician sesión en Lync 2013 desde varios equipos.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="8ff7d-131">Tenga en cuenta que en LyncPerfTool.exe, cada punto de conexión usa el perfil predeterminado (es decir, el perfil no se divide entre los dos puntos de presencia).</span><span class="sxs-lookup"><span data-stu-id="8ff7d-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="8ff7d-132">Comencé LyncPerfTool.exe pero no ocurre nada.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="8ff7d-133">¿Qué sucede?</span><span class="sxs-lookup"><span data-stu-id="8ff7d-133">What’s going on?</span></span>

<span data-ttu-id="8ff7d-134">Compruebe el contador de extremos activos totales en los clientes para ver si los usuarios se conectan.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="8ff7d-135">Si los usuarios no se conectan, Compruebe la configuración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="8ff7d-136">Este problema suele producirse porque el nombre del servidor, el prefijo de usuario o la contraseña son incorrectos.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="8ff7d-137">Tenga en cuenta que los clientes externos deben especificar el proxy de acceso como el valor TargetServer.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="8ff7d-138">Compruebe el puerto en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="8ff7d-139">¿Cómo puedo saber si algo está ocurriendo?</span><span class="sxs-lookup"><span data-stu-id="8ff7d-139">How do I know something is happening?</span></span>

<span data-ttu-id="8ff7d-140">Los distintos contadores de rendimiento de LyncPerfTool indican si los usuarios están conectando y realizando acciones.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="8ff7d-141">Sin embargo, una forma sencilla de comprobar es iniciar sesión en una de las cuentas con Lync 2013 y realizar la acción deseada.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="8ff7d-142">Tengo instaladas las herramientas de planeación de capacidad de Live Communications Server 2007 R2 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="8ff7d-143">¿Es correcto?</span><span class="sxs-lookup"><span data-stu-id="8ff7d-143">Is that OK?</span></span>

<span data-ttu-id="8ff7d-144">No.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-144">No.</span></span> <span data-ttu-id="8ff7d-145">Hay problemas de interoperabilidad y debe desinstalar todas las versiones anteriores de este producto.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="8ff7d-146">¿Las herramientas de estrés y rendimiento configuran la topología del servidor de información de llamadas de CAA?</span><span class="sxs-lookup"><span data-stu-id="8ff7d-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="8ff7d-147">No.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-147">No.</span></span> <span data-ttu-id="8ff7d-148">Las herramientas solo crean usuarios, contactos y listas de distribución, y simulan la carga de usuarios.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="8ff7d-149">¿Cuál es el número máximo de usuarios que admiten las herramientas?</span><span class="sxs-lookup"><span data-stu-id="8ff7d-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="8ff7d-150">Hemos creado hasta un total de 80.000 usuarios y pruebas ejecutadas que totalizan 30.000 usuarios con estas herramientas.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="8ff7d-151">Se recomienda un máximo de 120.000 usuarios, aunque las limitaciones técnicas permiten un valor superior, según el hardware del servidor y el cliente disponibles.</span><span class="sxs-lookup"><span data-stu-id="8ff7d-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

