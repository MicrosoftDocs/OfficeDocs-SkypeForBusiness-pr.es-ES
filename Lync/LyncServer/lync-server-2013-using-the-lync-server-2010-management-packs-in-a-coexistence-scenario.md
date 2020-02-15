---
title: Uso de los paquetes de administración de Lync Server 2010 en un escenario de coexistencia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8014f947a669b7b636061f17e40dee0fef287345
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="6fd7d-102">Uso de los paquetes de administración de Lync Server 2010 en un escenario de coexistencia</span><span class="sxs-lookup"><span data-stu-id="6fd7d-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fd7d-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="6fd7d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6fd7d-104">Muchos clientes adoptan un programa de implementación dentro de sus empresas en el que los usuarios se migran progresivamente desde Microsoft Lync Server 2010 a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="6fd7d-105">Los administradores de estas empresas le interesarán la supervisión de ambas versiones de Lync Server para ayudar a garantizar que todos sus usuarios finales obtengan la mejor experiencia de comunicación posible.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="6fd7d-106">Para este escenario, el módulo de administración de Lync Server 2013 admite una ruta de migración en paralelo con el módulo de administración de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="6fd7d-107">En Lync Server 2010, los equipos con Lync Server se detectaron a través del documento de topología almacenado con el almacén de administración central.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="6fd7d-108">En esta configuración, un único equipo notificaría la existencia de todos los demás equipos de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="6fd7d-109">Los paquetes de administración de Lync Server 2013 ahora usan la detección en el nivel de equipo en lugar del mecanismo de detección central que se usó en Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="6fd7d-110">Por ello, cada agente de System Center, básicamente, se detecta a sí mismo e informa de su existencia a System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="6fd7d-111">El uso de la detección en el nivel de máquina simplifica la administración de la infraestructura de System Center y también habilita distintas versiones de los paquetes de administración de Lync Server (por ejemplo, módulos de administración para Lync Server 2010 y paquetes de administración para Lync Server 2013) coexistir más fácilmente.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="6fd7d-112">Para admitir esta migración, primero tendrá que actualizar la supervisión de Lync Server 2010 existente para evitar brechas en la cobertura.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="6fd7d-113">Para ello, elija un equipo de Lync Server 2010 existente para que servicio el script de detección central de Lync Server 2010 antes de actualizar el almacén de administración central a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="6fd7d-114">Este proceso tiene cuatro pasos:</span><span class="sxs-lookup"><span data-stu-id="6fd7d-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="6fd7d-115">Actualice los paquetes de administración de Lync Server 2010 a la actualización acumulativa 7.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="6fd7d-116">Indique a un equipo de Lync Server 2010 que ejecute el script de detección central.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="6fd7d-117">Invalide el candidato de detección central en el módulo de administración de Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="6fd7d-118">Compruebe que se ha detectado el nuevo candidato de detección central.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="6fd7d-119">Ordenar a un equipo de Lync Server 2010 que ejecute el script de detección central</span><span class="sxs-lookup"><span data-stu-id="6fd7d-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="6fd7d-120">Para designar un equipo que no sea el almacén de administración central (por ejemplo, un servidor front-end de Lync Server) que controle la detección central, deberá crear la siguiente clave del registro en el servidor no central de almacenamiento de administración:</span><span class="sxs-lookup"><span data-stu-id="6fd7d-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="6fd7d-121">Software\\\\HKLM CentralDiscoveryCandidate\\de estado\\de comunicaciones\\en tiempo real de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6fd7d-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="6fd7d-122">Puede crear esta clave del Registro llevando a cabo el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="6fd7d-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="6fd7d-123">Haga clic en **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="6fd7d-124">En el cuadro de diálogo **Ejecutar**, escriba **regedit** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="6fd7d-125">En el editor del registro, expanda el **\_equipo local\_HKEY**, expanda **software**, expanda **Microsoft**y, a continuación, expanda **comunicaciones en tiempo real**.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="6fd7d-p105">Haga clic con el botón secundario en **Health**, haga clic en **Nuevo** y, después, haga clic en **Clave**. Si no existe la clave **Health**, haga clic con el botón secundario en **Real-Time Communications**, elija **Nuevo** y, luego, haga clic en **Clave**. Cuando se haya creado la nueva clave, escriba Health y presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-p105">Right-click **Health**, click **New**, and then click **Key**. If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**. When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="6fd7d-129">Después de que se haya creado la nueva clave, escriba **CentralDiscoveryCandidate** y presione ENTRAR para cambiar el nombre de la clave.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="6fd7d-130">El equipo puede tardar varias horas en adoptar este cambio.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="6fd7d-131">Para que el cambio se aplique de inmediato, detenga el servicio Agente de mantenimiento y reinícielo.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="6fd7d-132">Para reiniciar el servicio de agente de mantenimiento, complete el siguiente procedimiento en el equipo con Lync Server 2010:</span><span class="sxs-lookup"><span data-stu-id="6fd7d-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="6fd7d-133">Haga clic en **Inicio**, **Todos los programas**, **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="6fd7d-134">En la ventana de la consola, escriba el siguiente comando y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="6fd7d-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="6fd7d-p107">Verá el siguiente mensaje: "El servicio de administración de System Center se está deteniendo", seguido de un segundo mensaje para informarle de que el servicio se ha detenido. Después de que el servicio se haya detenido, puede reiniciarlo escribiendo el siguiente comando y presionando ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="6fd7d-p107">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="6fd7d-137">Invalidación del candidato de detección central del módulo de administración de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="6fd7d-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="6fd7d-138">Después de indicar a un equipo de Lync Server 2010 que informe sobre los equipos de Lync Server 2010, deberá informar también al módulo de administración de Lync Server 2010 sobre este cambio.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="6fd7d-139">Para ello, tendrá que crear una invalidación en el módulo de administración.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="6fd7d-140">Se puede hacer siguiendo este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="6fd7d-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="6fd7d-141">En la consola de Operations Manager, haga clic en **Creación**.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="6fd7d-142">En la pestaña Creación, expanda **Objetos del módulo de administración**, haga clic en **Detecciones de objetos** y, después, haga clic en **Ámbito**.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="6fd7d-143">En el cuadro de diálogo **Objetos de módulo de administración de ámbito**, seleccione el elemento que tenga el **candidato de detección de LS** de destino y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="6fd7d-144">Tenga en cuenta que LS Discovery Candidate solo aparecerá si ha instalado el módulo de administración de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="6fd7d-145">En la consola de Operations Manager, haga clic con el botón secundario en **Candidato de detección de LS**, elija **Invalidaciones**, elija **Invalidar la detección de objetos** y, luego, haga clic en **Para todos los objetos de la clase: candidato de detección de LS**.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="6fd7d-146">En el cuadro de diálogo **Propiedades de invalidación**, active la casilla **Invalidar** que hay junto al parámetro **Fqdn de WatcherNode de detección central**.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="6fd7d-147">Escriba el nombre de dominio completo del equipo de Lync Server 2010 en los cuadros **valor de reemplazo** y **valor efectivo** .</span><span class="sxs-lookup"><span data-stu-id="6fd7d-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="6fd7d-148">Active la casilla **Aplicado** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="6fd7d-p111">Una vez haya creado la invalidación, debe reiniciar el servicio de mantenimiento del Servidor de administración raíz. Para reiniciar el servicio de mantenimiento, lleve a cabo el siguiente procedimiento en el Servidor de administración raíz:</span><span class="sxs-lookup"><span data-stu-id="6fd7d-p111">After you have created the override, you need to restart the health service on the Root Management Server. To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="6fd7d-151">Haga clic en **Inicio**, **Todos los programas**, **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="6fd7d-152">En la ventana de la consola, escriba el siguiente comando y presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="6fd7d-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="6fd7d-p112">Verá el siguiente mensaje: "El servicio de administración de System Center se está deteniendo", seguido de un segundo mensaje para informarle de que el servicio se ha detenido. Después de que el servicio se haya detenido, puede reiniciarlo escribiendo el siguiente comando y presionando ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="6fd7d-p112">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="6fd7d-155">Comprobar que se detectó el nuevo candidato de detección central</span><span class="sxs-lookup"><span data-stu-id="6fd7d-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="6fd7d-156">El último paso antes de actualizar el almacén de administración central es asegurarse de que el módulo de administración de Lync Server 2010 detectó el nuevo candidato de detección central.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="6fd7d-157">Para ello, abra la consola de Operations Manager y haga clic en Supervisión.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="6fd7d-158">En la pestaña Supervisión, expanda **Mantenimiento de Microsoft Lync Server 2010**, expanda **Detección de topologías** y, a continuación, haga clic en **Vista de estado de detección**.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="6fd7d-159">Compruebe que una fila de la pantalla tiene una **Ruta** con el nombre de dominio completo del candidato de detección central.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="6fd7d-160">También debe comprobar que el estado del equipo es **Correcto**.</span><span class="sxs-lookup"><span data-stu-id="6fd7d-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

