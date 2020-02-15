---
title: 'Lync Server 2013: configurar un tronco sin desvío de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd810c64f546c907f0fd00d2dc2fea43e09fa1bf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a><span data-ttu-id="73012-102">Configurar un tronco sin omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73012-102">Configure a trunk without media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73012-103">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="73012-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="73012-104">Si desea configurar un enlace troncal con el desvío de medios deshabilitado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="73012-104">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="73012-105">Si desea configurar un tronco con la omisión de medios habilitada, consulte [configurar un tronco con la omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="73012-105">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="73012-p102">Tal como se describe a continuación, una configuración de tronco agrupa un conjunto de parámetros que se aplican a los troncos asignados a esta configuración de tronco. Una configuración de tronco puede tener ámbito global (se aplica a todos los troncos que no tienen sitios o configuración de grupo más específicos), ámbito de sitio o de grupo. La configuración del tronco de nivel de grupo se utiliza para adaptar una configuración de tronco específica a un único tronco.</span><span class="sxs-lookup"><span data-stu-id="73012-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="73012-109">Para configurar un enlace troncal sin desvío de medios</span><span class="sxs-lookup"><span data-stu-id="73012-109">To configure a trunk without media bypass</span></span>

1.  <span data-ttu-id="73012-110">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="73012-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="73012-111">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="73012-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="73012-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73012-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="73012-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="73012-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="73012-114">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.</span><span class="sxs-lookup"><span data-stu-id="73012-114">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="73012-115">En la página **Configuración del tronco**, utilice uno de los métodos siguientes para configurar un tronco:</span><span class="sxs-lookup"><span data-stu-id="73012-115">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="73012-116">Haga doble clic en un tronco existente (por ejemplo, el tronco **Global**) para que aparezca el cuadro de diálogo **Editar configuración del tronco**.</span><span class="sxs-lookup"><span data-stu-id="73012-116">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="73012-117">Haga clic en **Nuevo** y, a continuación, seleccione un ámbito para la nueva configuración de tronco:</span><span class="sxs-lookup"><span data-stu-id="73012-117">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="73012-118">**Tronco del sitio:** Elija el sitio para esta configuración de tronco en **seleccionar un sitio** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="73012-118">**Site trunk:** Choose the site for this trunk configuration in **Select a Site** , and then click **OK**.</span></span> <span data-ttu-id="73012-119">Tenga en cuenta que si ya se ha creado una configuración de tronco para un sitio, el sitio no aparece en **Seleccionar un sitio**.</span><span class="sxs-lookup"><span data-stu-id="73012-119">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="73012-120">Esta configuración de tronco se aplicará a todos los troncos del sitio.</span><span class="sxs-lookup"><span data-stu-id="73012-120">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="73012-121">**Tronco de Grupo:** Elija el nombre del tronco al que se aplica esta configuración de tronco en **Seleccione un servicio** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="73012-121">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="73012-122">Este tronco puede ser el tronco raíz o los troncos adicionales definidos en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="73012-122">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="73012-123">Tenga en cuenta que si ya se ha creado una configuración de tronco para un tronco específico, el tronco no se mostrará en **Seleccionar un servicio**.</span><span class="sxs-lookup"><span data-stu-id="73012-123">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73012-124">Una vez seleccionado el ámbito de la configuración de tronco, no se podrá cambiar.</span><span class="sxs-lookup"><span data-stu-id="73012-124">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="73012-125">El campo <STRONG>Nombre</STRONG> está rellenado previamente con el nombre del sitio o servicio asociado a la configuración del tronco y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="73012-125">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="73012-126">Seleccione una de las opciones de **Nivel admitido de cifrado** siguientes:</span><span class="sxs-lookup"><span data-stu-id="73012-126">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="73012-127">**Obligatorio:** Se debe usar el cifrado de protocolo de transporte seguro en tiempo real (SRTP) para ayudar a proteger el tráfico entre el servidor de mediación y la puerta de enlace o central de conmutación (PBX).</span><span class="sxs-lookup"><span data-stu-id="73012-127">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="73012-128">**Opcional:** Se usará el cifrado SRTP si el proveedor de servicios o el fabricante del equipo lo admiten.</span><span class="sxs-lookup"><span data-stu-id="73012-128">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="73012-129">**No se admite:** El cifrado de SRTP no es compatible con el proveedor de servicios o el fabricante del equipo y, por lo tanto, no se usará.</span><span class="sxs-lookup"><span data-stu-id="73012-129">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6.  <span data-ttu-id="73012-130">Asegúrese de que esté desactivada la casilla **Habilitar desvío de medios**.</span><span class="sxs-lookup"><span data-stu-id="73012-130">Be sure that the **Enable media bypass** check box is cleared.</span></span>

7.  <span data-ttu-id="73012-p107">Active la casilla de verificación **Procesamiento de medios centralizado** si existe un punto de finalización de medios bien conocido (por ejemplo, una puerta de enlace de red telefónica conmutada [RTC] donde la finalización de medios tenga la misma IP que la finalización de señalización). Si el tronco no tiene un punto de terminación de medios conocido, desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="73012-p107">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a public switched telephone network (PSTN) gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8.  <span data-ttu-id="73012-133">Si el tronco del mismo nivel admite la recepción de solicitudes SIP REFER del servidor de mediación, active la casilla de verificación **Habilitar la referencia de envío a la puerta de enlace** .</span><span class="sxs-lookup"><span data-stu-id="73012-133">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

9.  <span data-ttu-id="73012-p108">(Opcional) Para habilitar el enrutamiento entre troncos, asocie y configure los registros de uso de RTC a esta configuración de tronco. Los usos de RTC asociados a esta configuración de tronco se aplicarán a todas las llamadas entrantes al tronco que no tenga su origen en un extremo de Lync. Para administrar los registros de uso de RTC asociados a una configuración de tronco, use uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="73012-p108">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="73012-137">Para seleccionar uno o más registros de una lista de todos los registros de uso de RTC disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="73012-137">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="73012-138">Resalte los registros que desee asociar a esta configuración de tronco y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="73012-138">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="73012-139">Para quitar un registro de uso de RTC de esta configuración de tronco, resalte el registro y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="73012-139">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="73012-140">Para definir un nuevo registro de uso de RTC y asociarlo a esta configuración de tronco:</span><span class="sxs-lookup"><span data-stu-id="73012-140">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="73012-141">Haga clic en  \*\*Nuevo \*\*.</span><span class="sxs-lookup"><span data-stu-id="73012-141">Click **New**.</span></span>
        
        2.  <span data-ttu-id="73012-142">En el campo **Nombre**, especifique un nombre descriptivo único para el registro.</span><span class="sxs-lookup"><span data-stu-id="73012-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="73012-p110">El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="73012-p110">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="73012-145">Use uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="73012-145">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="73012-146">Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de la telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="73012-146">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="73012-147">Resalte las rutas que desea asociar a este registro de uso de RTC y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="73012-147">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="73012-148">Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="73012-148">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="73012-149">Para definir una ruta nueva y asociarla a este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="73012-149">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="73012-150">Para obtener más información, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="73012-150">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="73012-151">Para editar una ruta ya asociada a este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="73012-151">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="73012-152">Para obtener más información, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="73012-152">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="73012-153">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="73012-153">Click **OK**.</span></span>
    
      - <span data-ttu-id="73012-154">Para editar un registro de uso de RTC ya asociado a esta configuración de tronco, lleve a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="73012-154">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="73012-155">Seleccione el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="73012-155">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="73012-156">Use uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="73012-156">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="73012-157">Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de la telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="73012-157">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="73012-158">Resalte las rutas que desea asociar a este registro de uso de RTC y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="73012-158">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="73012-159">Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="73012-159">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="73012-160">Para definir una ruta nueva y asociarla a este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="73012-160">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="73012-161">Para obtener más información, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="73012-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="73012-162">Para editar una ruta ya asociada a este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="73012-162">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="73012-163">Para obtener más información, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="73012-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="73012-164">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="73012-164">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="73012-165">Es importante asociar los registros de uso de RTC de acuerdo con el servidor de mediación del mismo nivel que está asociado al tronco que se está configurando.</span><span class="sxs-lookup"><span data-stu-id="73012-165">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="73012-166">Si el servidor de mediación del mismo nivel es una puerta de enlace RTC o un controlador de borde de sesión (SBC), se recomienda encarecidamente que la configuración del tronco no esté asociada a un registro de uso de RTC que se enrute a un destino de RTC o a cualquier otro sistema descendente conectado a través de Lync. Server.</span><span class="sxs-lookup"><span data-stu-id="73012-166">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

10. <span data-ttu-id="73012-p118">Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, seleccione el registro de uso de RTC y haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="73012-p118">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="73012-169">Es importante el orden en el que aparecen en la lista de la configuración de tronco los registros de uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="73012-169">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="73012-170">Lync Server recorre la lista de arriba a abajo.</span><span class="sxs-lookup"><span data-stu-id="73012-170">Lync Server traverses the list from top to down.</span></span>

    
    </div>

11. <span data-ttu-id="73012-171">**Habilitar cierre de RTP** debe seleccionarse para habilitar el desvío de medios para los clientes que se encuentren detrás de un firewall o NAT y para los SBC que admitan el cierre.</span><span class="sxs-lookup"><span data-stu-id="73012-171">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="73012-172">**Habilite el historial de llamadas reenviadas** para habilitar el envío de información de historial de llamadas a la puerta de enlace del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="73012-172">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="73012-173">**Habilitar reenvío de datos P-Asserted-Identity** debe seleccionarse para habilitar el reenvío de la información del autor de la llamada de PAI entre el lado del servidor de mediación y la puerta de enlace (y viceversa), cuando esté presente.</span><span class="sxs-lookup"><span data-stu-id="73012-173">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="73012-174">**Habilitar temporizador de conmutación por error de enrutamiento saliente** debe seleccionarse para habilitar la conmutación por error rápida.</span><span class="sxs-lookup"><span data-stu-id="73012-174">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="73012-175">La puerta de enlace asociada a este tronco puede proporcionar información cada 10 segundos durante el procesamiento de una llamada saliente.</span><span class="sxs-lookup"><span data-stu-id="73012-175">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="73012-176">Si el servidor de mediación no recibe esta notificación, se producirá el redireccionamiento a otro tronco.</span><span class="sxs-lookup"><span data-stu-id="73012-176">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="73012-177">Es necesario deshabilitar la conmutación por error rápida en las redes en las que la latencia puede retrasar el tiempo de respuesta o si la puerta de enlace tarda más de 10 segundos en responder.</span><span class="sxs-lookup"><span data-stu-id="73012-177">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="73012-178">(Opcional) Asocie y configure las **Reglas de traducción de números de llamada** para el tronco.</span><span class="sxs-lookup"><span data-stu-id="73012-178">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="73012-179">Estas reglas de traducción se aplican a los números de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="73012-179">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="73012-180">Para elegir una o más reglas de una lista de todas las reglas de conversión que están disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="73012-180">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="73012-181">En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="73012-181">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="73012-182">Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="73012-182">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="73012-183">Para obtener más información sobre cómo definir una regla nueva, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="73012-183">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="73012-184">Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="73012-184">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="73012-185">Para obtener más información, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="73012-185">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="73012-186">Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar**y, a continuación, en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="73012-186">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="73012-187">Para obtener más información, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="73012-187">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="73012-188">Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="73012-188">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="seguridad" alt="security" /><span data-ttu-id="73012-190">Nota de seguridad:</span><span class="sxs-lookup"><span data-stu-id="73012-190">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="73012-191">No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="73012-191">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. <span data-ttu-id="73012-p126">(Opcional) Asocie y configure las **Reglas de traducción de números llamados** para el tronco. Estas reglas de traducción se aplican a los números de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="73012-p126">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="73012-194">Para elegir una o más reglas de una lista de todas las reglas de conversión que están disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="73012-194">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="73012-195">En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="73012-195">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="73012-196">Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="73012-196">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="73012-197">Para obtener más información sobre cómo definir una regla nueva, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="73012-197">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="73012-198">Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="73012-198">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="73012-199">Para obtener más información, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="73012-199">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="73012-200">Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar**y, a continuación, en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="73012-200">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="73012-201">Para obtener más información, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="73012-201">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="73012-202">Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="73012-202">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="73012-203">No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="73012-203">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="73012-204">Asegúrese de que las reglas de conversión del tronco estén organizadas en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="73012-204">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="73012-205">Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="73012-205">To change a rule’s position in the list, highlight the rule name, and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="73012-206">Lync Server recorre la lista de reglas de conversión de arriba abajo y usa la primera regla que coincide con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="73012-206">Lync Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="73012-207">Si configura un tronco de forma que un número marcado puede coincidir con más de una regla de conversión, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas.</span><span class="sxs-lookup"><span data-stu-id="73012-207">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="73012-208">Por ejemplo, si ha incluido una regla de conversión que coincida con cualquier número de 11 dígitos y una regla de conversión que coincida solamente con números de 11 dígitos que comiencen por -1425, asegúrese de que la regla que coincida con cualquier número de 11 dígitos se haya colocado <EM>debajo</EM> de la regla más restrictiva.</span><span class="sxs-lookup"><span data-stu-id="73012-208">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

18. <span data-ttu-id="73012-209">Cuando haya terminado de configurar el tronco, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="73012-209">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="73012-210">En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="73012-210">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73012-211">Siempre que cree o modifique una configuración de tronco, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="73012-211">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="73012-212">Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="73012-212">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="73012-213">Vea también</span><span class="sxs-lookup"><span data-stu-id="73012-213">See Also</span></span>


[<span data-ttu-id="73012-214">Configurar un tronco con la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73012-214">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="73012-215">Definición de reglas de conversión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73012-215">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

