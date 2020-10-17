---
title: Configurar las rutas de federación y el tráfico multimedia
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b07e0bfe62fe6d09521d1f9d5dc2d84aa975d5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503357"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="4aaf2-102">Configurar las rutas de federación y el tráfico multimedia</span><span class="sxs-lookup"><span data-stu-id="4aaf2-102">Configure federation routes and media traffic</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4aaf2-103">_**Última modificación del tema:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="4aaf2-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="4aaf2-104">La federación es una relación de confianza entre dos o más dominios SIP que permite a los usuarios de organizaciones independientes comunicarse a través de los límites de las redes.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-104">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="4aaf2-105">Después de migrar al grupo piloto de Lync Server 2013, debe realizar la transición de la ruta de Federación de sus servidores perimetrales de Lync Server 2010 a la ruta de Federación de sus servidores perimetrales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-105">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="4aaf2-106">Use los siguientes procedimientos para realizar la transición de la ruta de Federación y la ruta de tráfico de medios del servidor perimetral y el director de Lync Server 2010 a su servidor perimetral de Lync Server 2013 para una implementación en un solo sitio.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-106">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4aaf2-107">Para cambiar la ruta de Federación y la ruta de tráfico de medios es necesario programar el tiempo de inactividad de mantenimiento para los servidores perimetrales de Lync Server 2013 y Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-107">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="4aaf2-108">Este proceso de transición también implica que el acceso federado no estará disponible durante la interrupción.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-108">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="4aaf2-109">Debe programar el tiempo de inactividad para un período en el que se prevé una actividad mínima de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-109">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="4aaf2-110">También debe notificar esta acción a los usuarios finales con antelación suficiente.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-110">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="4aaf2-111">Planee esta interrupción como corresponda y defina las expectativas adecuadas en la organización.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-111">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4aaf2-112">Si el servidor perimetral de Lync Server 2010 heredado está configurado para usar el mismo FQDN para el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V, no se admiten los procedimientos de esta sección.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-112">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="4aaf2-113">Si los servicios perimetrales heredados están configurados para usar el mismo FQDN, primero debe migrar todos los usuarios de Lync Server 2010 a Lync Server 2013 y, después, retirar el servidor perimetral de Lync Server 2010 antes de habilitar la Federación en el servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-113">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4aaf2-114">Si la Federación de XMPP se enruta a través de un servidor perimetral de Lync Server 2013, los usuarios heredados de Lync Server 2010 no podrán comunicarse con el socio federado de XMPP hasta que todos los usuarios se hayan movido a Lync Server 2013, se hayan configurado las directivas y los certificados XMPP, se haya configurado el socio federado de XMPP en Lync Server 2013 y se hayan actualizado las entradas DNS.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-114">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="4aaf2-115">Para quitar la asociación de federación heredada de los sitios de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aaf2-115">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="4aaf2-116">En el servidor front-end de Lync Server 2013, abra la topología existente en Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-116">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="4aaf2-117">En el panel izquierdo, desplácese al nodo del sitio, que se encuentra justo debajo de **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-117">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="4aaf2-118">Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-118">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="4aaf2-119">En el panel izquierdo, seleccione **Ruta de federación**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-119">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="4aaf2-120">En **asignación de ruta de Federación del sitio**, desactive la casilla **Habilitar Federación SIP** para deshabilitar la ruta de Federación a través del entorno heredado de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-120">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="4aaf2-121">![Cuadro de diálogo Editar propiedades, página Ruta de Federación](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página Ruta de Federación")</span><span class="sxs-lookup"><span data-stu-id="4aaf2-121">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="4aaf2-122">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-122">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="4aaf2-123">En **Topology Builder**, seleccione el nodo en primera posición **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-123">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="4aaf2-124">En el menú **Acción**, haga clic en **Publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-124">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="4aaf2-125">Haga clic en **Siguiente** para completar el proceso de publicación y, después, haga clic en **Finalizar** cuando se haya completado el proceso de publicación.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-125">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="4aaf2-126">Para configurar el servidor perimetral heredado como servidor perimetral no federado</span><span class="sxs-lookup"><span data-stu-id="4aaf2-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="4aaf2-127">En el panel izquierdo, desplácese al nodo **Lync Server 2010** y, después, al nodo **Grupos de servidores perimetrales**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-127">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="4aaf2-128">Haga clic con el botón secundario en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="4aaf2-129">Seleccione **General** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-129">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="4aaf2-130">Desactive la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** y seleccione **Aceptar** para cerrar la página.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-130">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="4aaf2-131">![Editar propiedades, general, desactive habilitar Federación](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Editar propiedades, general, desactive habilitar Federación")</span><span class="sxs-lookup"><span data-stu-id="4aaf2-131">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="4aaf2-132">En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-132">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="4aaf2-133">Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-133">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="4aaf2-134">Compruebe que está deshabilitada la federación en el servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-134">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="4aaf2-135">![Generador de topologías, grupo de servidores perimetrales, Federación deshabilitada](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Generador de topologías, grupo de servidores perimetrales, Federación deshabilitada")</span><span class="sxs-lookup"><span data-stu-id="4aaf2-135">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="4aaf2-136">Para configurar certificados en el servidor perimetral de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="4aaf2-136">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="4aaf2-137">Exporte el certificado del proxy de acceso externo, con la clave privada, desde el servidor perimetral de Lync Server 2010 heredado.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-137">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="4aaf2-138">En el servidor perimetral de Lync Server 2013, importe el certificado externo del servidor proxy de acceso del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-138">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="4aaf2-139">Asigne el certificado externo del proxy de acceso a la interfaz externa de Lync Server 2013 del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-139">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="4aaf2-140">El certificado de interfaz interno del servidor perimetral de Lync Server 2013 debe solicitarse a una entidad de certificación de confianza y asignarse.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-140">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="4aaf2-141">Para cambiar la ruta de federación de Lync Server 2010 y usar el servidor perimetral de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aaf2-141">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="4aaf2-142">En Topology Builder, en el panel izquierdo, desplácese al nodo **Lync Server 2013** y, después, al nodo **Grupos de servidores perimetrales**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-142">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="4aaf2-143">Haga clic con el botón secundario en el servidor perimetral y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-143">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="4aaf2-144">Seleccione **General** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-144">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="4aaf2-145">Active la entrada de la casilla **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)** y, a continuación, seleccione **Aceptar** para cerrar la página.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-145">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="4aaf2-146">![Cuadro de diálogo Editar propiedades, página general](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página general")</span><span class="sxs-lookup"><span data-stu-id="4aaf2-146">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="4aaf2-147">En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-147">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="4aaf2-148">Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-148">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="4aaf2-149">Compruebe que **Federación (puerto 5061)** está **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-149">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="4aaf2-150">![Generador de topologías, grupo de servidores perimetrales, Federación habilitada](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Generador de topologías, grupo de servidores perimetrales, Federación habilitada")</span><span class="sxs-lookup"><span data-stu-id="4aaf2-150">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="4aaf2-151">Para actualizar al próximo salto de la federación del servidor perimetral de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aaf2-151">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="4aaf2-152">En Topology Builder, en el panel izquierdo, desplácese al nodo **Lync Server 2013** y, después, al nodo **Grupos de servidores perimetrales**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-152">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="4aaf2-153">Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que se muestra y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-153">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="4aaf2-154">En la página **General** , en **selección**de próximo salto, seleccione en la lista desplegable el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-154">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="4aaf2-155">![Cuadro de diálogo Editar propiedades, página de salto siguiente](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página de salto siguiente")</span><span class="sxs-lookup"><span data-stu-id="4aaf2-155">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="4aaf2-156">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-156">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="4aaf2-157">En **generador de topologías**, seleccione el nodo superior **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="4aaf2-157">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="4aaf2-158">En el menú **Acción**, haga clic en **Publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-158">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="4aaf2-159">Para configurar la ruta de medios de salida del servidor perimetral de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aaf2-159">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="4aaf2-160">En el generador de topologías, en el panel izquierdo, desplácese al nodo **Lync Server 2013** y, a continuación, al grupo de servidores que se encuentra debajo de **servidores front-end Standard Edition** o **grupos de servidores front-end Enterprise Edition**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-160">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="4aaf2-161">Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-161">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="4aaf2-162">En la sección **Asociaciones**, seleccione la casilla **Asociar grupo de servidores perimetrales (para componentes multimedia)**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-162">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="4aaf2-163">![Editar propiedades, general, asociar grupo de servidores perimetrales](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Editar propiedades, general, asociar grupo de servidores perimetrales")</span><span class="sxs-lookup"><span data-stu-id="4aaf2-163">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="4aaf2-164">En el cuadro desplegable, seleccione el servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-164">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="4aaf2-165">Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-165">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="4aaf2-166">Para activar la federación del servidor perimetral de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aaf2-166">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="4aaf2-167">En Topology Builder, en el panel izquierdo, desplácese al nodo **Lync Server 2013** y, después, al nodo **Grupos de servidores perimetrales**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-167">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="4aaf2-168">Expanda el nodo, haga clic con el botón secundario en el servidor perimetral que se muestra y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-168">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4aaf2-169">La Federación solo se puede habilitar para un único grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-169">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="4aaf2-170">Si tiene varios grupos de servidores perimetrales, seleccione uno para usarlo como grupo de servidores perimetrales en la federación.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-170">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="4aaf2-171">En la página **General**, compruebe que está activada la opción de configuración **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-171">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="4aaf2-172">![Cuadro de diálogo Editar propiedades, página general](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Cuadro de diálogo Editar propiedades, página general")</span><span class="sxs-lookup"><span data-stu-id="4aaf2-172">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="4aaf2-173">Haga clic en **Aceptar** para cerrar la página Editar propiedades.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-173">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="4aaf2-174">A continuación, navegue hasta el nodo del sitio.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-174">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="4aaf2-175">Haga clic con el botón secundario en el sitio y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-175">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="4aaf2-176">En el panel izquierdo, haga clic en **Ruta de federación**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-176">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="4aaf2-177">En **asignación de ruta de Federación del sitio**, seleccione **Habilitar Federación SIP**y, a continuación, en la lista, seleccione el servidor perimetral de Lync Server 2013 que aparece en la lista.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-177">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="4aaf2-178">![Editar propiedades, página Ruta de Federación](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Editar propiedades, página Ruta de Federación")</span><span class="sxs-lookup"><span data-stu-id="4aaf2-178">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="4aaf2-179">Haga clic en **Aceptar** para cerrar la página **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-179">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="4aaf2-180">Para las implementaciones en varios sitios, complete este procedimiento en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-180">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="4aaf2-181">Para publicar cambios de configuración en el servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="4aaf2-181">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="4aaf2-182">En **generador de topologías**, seleccione el nodo superior **Lync Server** .</span><span class="sxs-lookup"><span data-stu-id="4aaf2-182">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="4aaf2-183">En el menú **Acción**, seleccione **Publicar topología** y complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-183">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="4aaf2-184">Espere a que se produzca la replicación de Active Directory para todos los grupos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-184">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4aaf2-185">Es posible que aparezca el mensaje siguiente:</span><span class="sxs-lookup"><span data-stu-id="4aaf2-185">You may see the following message:</span></span><BR><span data-ttu-id="4aaf2-186"><STRONG>Advertencia: la topología contiene más de un servidor perimetral federado. Esta situación se puede producir durante la migración a una versión más reciente del producto. En ese caso, solo se usará activamente un servidor perimetral para la federación. Compruebe que el registro SRV de DNS externo apunta al servidor perimetral correcto. Si desea implementar varios servidores perimetrales de federación para que estén activos simultáneamente (no en un escenario de migración), asegúrese de que todos los socios federados usan Lync Server y compruebe que, en el registro SRV de DNS externo, se enumeran todos los servidores perimetrales habilitados para federación.</STRONG></span><span class="sxs-lookup"><span data-stu-id="4aaf2-186"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="4aaf2-187">Se espera que aparezca esta advertencia y se puede omitir con toda seguridad.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-187">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="4aaf2-188">Para configurar el servidor perimetral de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4aaf2-188">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="4aaf2-189">Conecte todos los servidores perimetrales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-189">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="4aaf2-190">Actualice las reglas de enrutamiento del firewall externo o la configuración del equilibrador de carga de hardware para enviar tráfico SIP para acceso externo (normalmente el puerto 443) y la Federación (normalmente, el puerto 5061) al servidor perimetral de Lync Server 2013, en lugar del servidor perimetral heredado.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-190">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4aaf2-p105">Si no tiene un equilibrador de carga de hardware, debe actualizar el registro DNS A para la federación, de modo que se resuelva en el nuevo servidor perimetral de acceso de Lync Server. La manera de lograrlo que produce menos interrupciones es reducir el valor de TTL del FQDN del servidor perimetral de acceso de Lync Server externo, de modo que, cuando DNS se actualice para apuntar al nuevo servidor perimetral de acceso de Lync Server, la federación y el acceso remoto se actualizarán rápidamente.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-p105">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server. To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="4aaf2-193">A continuación, detenga el **servidor perimetral de acceso de Lync Server** en cada equipo servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-193">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="4aaf2-194">Desde cada equipo servidor perimetral heredado, abra el applet **servicios** de las **herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-194">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="4aaf2-195">En la lista de servicios, busque **Servidor perimetral de acceso de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-195">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="4aaf2-196">Haga clic con el botón secundario en el nombre de los servicios y seleccione **Detener** para detener el servicio.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-196">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="4aaf2-197">Establezca el Tipo de inicio en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-197">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="4aaf2-198">Haga clic en **Aceptar** para cerrar la ventana **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4aaf2-198">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

