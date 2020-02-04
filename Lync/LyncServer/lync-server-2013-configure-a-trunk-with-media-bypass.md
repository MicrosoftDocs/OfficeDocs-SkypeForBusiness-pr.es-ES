---
title: 'Lync Server 2013: configurar un tronco con omisión de medios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16c12a5d8cff03f8d5755b5a2b54a6ff4dcf8399
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="d1ffa-102">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1ffa-102">Configure a trunk with media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1ffa-103">_**Última modificación del tema:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="d1ffa-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="d1ffa-104">Siga estos pasos para configurar un tronco con la omisión de medios habilitada.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-104">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="d1ffa-105">Para configurar un tronco con la omisión de medios deshabilitada, vea [configurar un tronco sin omitir medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="d1ffa-105">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="d1ffa-106">La omisión de elementos multimedia es útil cuando desea minimizar el número de servidores de mediación implementados.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-106">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="d1ffa-107">Normalmente, un grupo de servidores de mediación se implementará en un sitio central y controlará las puertas de enlace en los sitios de sucursales.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-107">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="d1ffa-108">Habilitar la omisión de medios permite que las llamadas de la red telefónica conmutada (RTC) desde clientes en sitios de sucursal se dirijan directamente a través de las puertas de enlace a esos sitios.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-108">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="d1ffa-109">Las directivas de llamadas salientes de Lync Server 2013 y de Enterprise Voice deben configurarse correctamente para que las llamadas RTC de clientes de un sitio de sucursal se enruten a la puerta de enlace adecuada.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-109">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="d1ffa-110">Se recomienda habilitar la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-110">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="d1ffa-111">Ahora bien, antes de hacerlo en un tronco SIP, asegúrese de que su proveedor de troncos SIP cualificado es compatible con la omisión de medios y puede aceptar los requisitos para habilitar correctamente el escenario.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-111">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="d1ffa-112">Concretamente, el proveedor debe disponer de las direcciones IP de los servidores en la red interna de la organización.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-112">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="d1ffa-113">Si el proveedor no admite este escenario, la omisión de elementos multimedia no se realizará correctamente.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-113">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="d1ffa-114">Para obtener más información, consulte [planificación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-114">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d1ffa-115">La omisión de medios no funcionará con todas las puertas de enlace de red de telefonía pública conmutada (RTC), IP-PBX ni el controlador de borde de sesión (SBC).</span><span class="sxs-lookup"><span data-stu-id="d1ffa-115">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="d1ffa-116">Microsoft ha probado una serie de puertas de enlace RTC y SBC con asociados certificados y ha realizado algunas pruebas con los IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-116">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="d1ffa-117">La omisión de contenido multimedia solo se admite con productos y versiones que se enumeran en el programa de interoperabilidad <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>abierta de comunicaciones unificadas: Lync Server en.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-117">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="d1ffa-p104">Una configuración de tronco tal como se describe más abajo agrupa un conjunto de parámetros que se aplican a los troncos a los que se ha asignado esta configuración de tronco. Una configuración de tronco concreta puede tener ámbito global (todos los troncos que no tengan una configuración de sitio o grupo de servidores más concreta), de sitio o de grupo de servidores. La configuración de tronco de nivel de grupo de servidores se utiliza para limitar el ámbito de una configuración de tronco concreta a un único tronco.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-p104">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="d1ffa-121">Para configurar un tronco con omisión de medios</span><span class="sxs-lookup"><span data-stu-id="d1ffa-121">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="d1ffa-122">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="d1ffa-123">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="d1ffa-123">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="d1ffa-124">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d1ffa-125">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d1ffa-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d1ffa-126">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración de tronco**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-126">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="d1ffa-127">En la página **Configuración de tronco**, use uno de los métodos siguientes para configurar un tronco:</span><span class="sxs-lookup"><span data-stu-id="d1ffa-127">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="d1ffa-128">Haga doble clic en un tronco existente (por ejemplo, el tronco **Global**) para que aparezca el cuadro de diálogo **Editar configuración de tronco**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-128">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="d1ffa-129">Haga clic en **Nuevo** y, a continuación, seleccione un ámbito para la nueva configuración de tronco:</span><span class="sxs-lookup"><span data-stu-id="d1ffa-129">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="d1ffa-130">**Tronco del sitio:** Elija el sitio para esta configuración de tronco en **Seleccione un sitio**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-130">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="d1ffa-131">Tenga en cuenta que si ya se ha creado una configuración de tronco para un sitio, el sitio no aparece en **Seleccionar un sitio**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-131">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="d1ffa-132">Esta configuración de tronco se aplicará a todos los troncos del sitio.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-132">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="d1ffa-133">**Tronco de la piscina:** Elija el nombre del tronco al que se aplica esta configuración troncal.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-133">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="d1ffa-134">Este tronco puede ser el tronco raíz o cualquier otro tipo de troncos definidos en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-134">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="d1ffa-135">En **Seleccionar un servicio**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-135">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="d1ffa-136">Tenga en cuenta que si ya se ha creado una configuración para un tronco específico, dicho tronco no aparecerá en **Seleccionar un servicio**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-136">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1ffa-137">Una vez seleccionado el ámbito de la configuración del tronco, no se podrá cambiar.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-137">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="d1ffa-138">El campo <STRONG>Nombre</STRONG> está rellenado previamente con el nombre del sitio o servicio asociado a la configuración del tronco y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-138">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="d1ffa-p109">Especifique un valor en **Número máximo de diálogos iniciales admitidos**. Es el número máximo de respuestas bifurcadas que una puerta de enlace de red telefónica conmutada (RTC), un sistema PBX IP o el controlador de borde de sesión (SBC) del proveedor de servicios puede recibir para una invitación (INVITE) enviada al servidor de mediación. El valor predeterminado es 20.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-p109">Specify a value in **Maximum early dialogs supported**. This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server. The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1ffa-142">Antes de cambiar este valor, póngase en contacto con su proveedor de servicios o fabricante de equipos para obtener información detallada sobre las capacidades de su sistema.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-142">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="d1ffa-143">Seleccione una de las opciones de  **Nivel admitido de cifrado** siguientes:</span><span class="sxs-lookup"><span data-stu-id="d1ffa-143">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="d1ffa-144">**Requerido:** El protocolo de transporte seguro (SRTP) debe usarse para ayudar a proteger el tráfico entre el servidor de mediación y la puerta de enlace o la central de conmutación (PBX).</span><span class="sxs-lookup"><span data-stu-id="d1ffa-144">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="d1ffa-145">**Opcional:** El cifrado SRTP se usará si el proveedor de servicios o el fabricante de equipos lo admiten.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-145">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="d1ffa-146">**No es compatible:** El cifrado de SRTP no es compatible con el proveedor de servicios o el fabricante del equipo y, por lo tanto, no se usará.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-146">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="d1ffa-147">Active la casilla **Habilitar omisión de medios** si desea que los medios omitan el servidor de mediación para que sea la entidad del mismo nivel que el tronco la que realice el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-147">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d1ffa-148">Para que la omisión de medios funcione correctamente, es preciso que la puerta de enlace de RTC, el sistema PBX IP o el controlador de borde de sesión del proveedor de servicios sean compatibles con ciertas capacidades.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-148">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="d1ffa-149">Para obtener más información, consulte <A href="lync-server-2013-planning-for-media-bypass.md">planificación de la omisión de medios en Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-149">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="d1ffa-p111">Active la casilla **Procesamiento de medios centralizado** si existe un punto de finalización de medios bien conocido (por ejemplo, una puerta de enlace RTC donde la finalización de medios tenga la misma IP que la finalización de señalización). Si el tronco no tiene un punto de terminación de medios conocido, desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-p111">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="d1ffa-152">Si el tronco del mismo nivel admite la recepción de solicitudes SIP de referencia del servidor de mediación, seleccione la casilla de verificación **Habilitar envío consulte la puerta de enlace** .</span><span class="sxs-lookup"><span data-stu-id="d1ffa-152">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1ffa-153">Si deshabilita esta opción mientras la opción <STRONG>Habilitar omisión de medios</STRONG> está seleccionada, se requerirá una configuración adicional.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-153">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="d1ffa-154">Si la entidad del mismo nivel del tronco no es compatible con la recepción de solicitudes SIP REFER del servidor de mediación y se ha habilitado el desvío de medios, es preciso que ejecute el cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> para deshabilitar el RTCP para las llamadas activas y en espera con el fin de admitir las condiciones adecuadas para la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-154">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="d1ffa-155">Para obtener más información, consulte la documentación del <A href="lync-server-2013-lync-server-management-shell.md">Shell de administración de Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="d1ffa-155">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="d1ffa-156">También puede seleccionar <STRONG>Habilitar referencia mediante el control de llamadas a terceros</STRONG> si desea que los medios omitan las llamadas transferidas y la puerta de enlace no admita solicitudes SIP REFER.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-156">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="d1ffa-157">(Opcional) Para habilitar el enrutamiento entre troncos, asocie y configure registros de uso de la RTC a esta configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-157">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="d1ffa-158">Los usos de RTC asociados a esta configuración de tronco se aplicarán para todas las llamadas entrantes a través del tronco que no se originen desde un punto de conexión de Lync.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-158">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint.</span></span> <span data-ttu-id="d1ffa-159">Para administrar registros de uso de la RTC asociados a una configuración de tronco, use uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d1ffa-159">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="d1ffa-160">Para seleccionar uno o varios registros de una lista de todos los registros de uso de RTC disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-160">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d1ffa-161">Resalte los registros que desee asociar a esta configuración de tronco y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-161">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="d1ffa-162">Para quitar un registro de uso de RTC de esta configuración de tronco, seleccione el registro y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-162">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="d1ffa-163">Para definir un nuevo registro de uso de RTC y asociarlo a esta configuración de tronco, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d1ffa-163">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="d1ffa-164">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-164">Click **New**.</span></span>
        
        2.  <span data-ttu-id="d1ffa-165">En el campo **Nombre**, escriba un nombre descriptivo único para el registro.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-165">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="d1ffa-p115">El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="d1ffa-168">Utilice uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="d1ffa-168">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="d1ffa-169">Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-169">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d1ffa-170">Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-170">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="d1ffa-171">Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-171">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="d1ffa-172">Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-172">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="d1ffa-173">Para obtener más información, vea [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="d1ffa-173">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="d1ffa-174">Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-174">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="d1ffa-175">Para obtener más información, vea [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="d1ffa-175">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="d1ffa-176">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-176">Click **OK**.</span></span>
    
      - <span data-ttu-id="d1ffa-177">Para editar un registro de uso de RTC ya asociado a esta configuración de tronco:</span><span class="sxs-lookup"><span data-stu-id="d1ffa-177">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="d1ffa-178">Seleccione el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-178">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="d1ffa-179">Utilice uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="d1ffa-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="d1ffa-180">Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d1ffa-181">Resalte las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="d1ffa-182">Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="d1ffa-183">Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="d1ffa-184">Para obtener más información, vea [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="d1ffa-184">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="d1ffa-185">Para editar una ruta que esté asociada con este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="d1ffa-186">Para obtener más información, vea [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="d1ffa-186">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="d1ffa-187">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-187">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d1ffa-188">Es importante asociar los registros de uso de RTC según el servidor de mediación del mismo nivel que esté asociado al tronco que se configure.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-188">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="d1ffa-189">Si el servidor de mediación del mismo nivel es una puerta de enlace RTC o un controlador de borde de sesión (SBC), se recomienda enfáticamente que la configuración de troncal no esté asociada a un registro de uso de RTC que se enrute a un destino RTC o a cualquier otro sistema indirecto conectado a través de Lync. Servidores.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="d1ffa-p123">Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, seleccione el registro de uso de RTC y haga clic en las flechas arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d1ffa-192">El orden en el que aparecen en la lista de configuración del tronco los registros de uso de RTC es importante.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="d1ffa-193">Lync Server recorre la lista de arriba a abajo.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-193">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="d1ffa-194">Debe seleccionarse **Habilitar cierre RTP** si se desea habilitar la omisión de medios para clientes situados detrás de una traducción de direcciones de red (NAT) o firewall y un SBC que admita cierre.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="d1ffa-195">**Habilitar el historial de llamadas hacia adelante** debe seleccionarse para habilitar el envío de información del historial de llamadas a la puerta de enlace del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="d1ffa-196">**Habilitar Forward-Asserted: los datos de identidad** deben seleccionarse para habilitar la identidad de firma de p-asserted-Identity (PAI) la información del originador de llamadas se desviará entre el lado del servidor de mediación y la puerta de enlace (y viceversa) cuando estén presentes.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="d1ffa-197">Debe seleccionar la opción **Habilitar temporizador de conmutación por error del enrutamiento de salida** para que la conmutación por error sea más rápida.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="d1ffa-198">La puerta de enlace asociada con este tronco puede notificar en un plazo de 10 segundos que se está procesando una llamada saliente.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="d1ffa-199">El redireccionamiento a otro tronco se producirá si el servidor de mediación no recibe esta notificación.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="d1ffa-200">En las redes en las que la latencia pueda retrasar el tiempo de respuesta o si la puerta de enlace se demora más de 10 segundos en responder, deberá deshabilitarse la conmutación por error rápida.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="d1ffa-201">(Opcional) Asocie y configure **Reglas de traducción de números de llamada** para el tronco.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="d1ffa-202">Estas reglas de conversión se aplican al número desde donde se realizó la llamada (para las llamadas salientes).</span><span class="sxs-lookup"><span data-stu-id="d1ffa-202">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="d1ffa-203">Para elegir una o más reglas de una lista de todas las reglas de traducción disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d1ffa-204">En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="d1ffa-205">Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="d1ffa-206">Para obtener más información sobre cómo definir una nueva regla, vea [definir reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-206">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="d1ffa-207">Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="d1ffa-208">Para obtener información detallada, consulte [definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-208">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="d1ffa-209">Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-209">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="d1ffa-210">Para obtener más información, consulte [definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="d1ffa-210">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="d1ffa-211">Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-211">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d1ffa-212">No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-212">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="d1ffa-p131">(Opcional) Asocie y configure **Reglas de traducción de números llamados** para el tronco. Estas reglas de conversión se aplican al número llamado en una llamada saliente.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="d1ffa-215">Para elegir una o más reglas de una lista de todas las reglas de traducción disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-215">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="d1ffa-216">En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-216">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="d1ffa-217">Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-217">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="d1ffa-218">Para obtener más información sobre cómo definir una nueva regla, vea [definir reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-218">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="d1ffa-219">Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-219">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="d1ffa-220">Para obtener información detallada, consulte [definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-220">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="d1ffa-221">Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-221">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="d1ffa-222">Para obtener más información, consulte [definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="d1ffa-222">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="d1ffa-223">Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-223">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d1ffa-224">No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas pudieran entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-224">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="d1ffa-p136">Asegúrese de que las reglas de conversión del tronco se dispongan en el orden correcto. Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-p136">Make sure that the trunk’s translation rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d1ffa-227">Lync Server 2013 recorre la lista de reglas de traducción de la parte superior abajo y usa la primera regla que coincida con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-227">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="d1ffa-228">Si configura un tronco de forma que un número marcado puede coincidir con más de una regla de conversión, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-228">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="d1ffa-229">Por ejemplo, si ha incluido una regla de conversión que coincida con cualquier número de 11 dígitos y una regla de conversión que coincida solamente con números de 11 dígitos que comiencen por +1425, asegúrese de que la regla que coincida con cualquier número de 11 dígitos se haya colocado <EM>por debajo</EM> de la regla más restrictiva.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-229">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="d1ffa-230">Cuando haya terminado de configurar el tronco, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-230">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="d1ffa-231">En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-231">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1ffa-232">Al crear o modificar la configuración de un tronco, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-232">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="d1ffa-233">Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-233">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="d1ffa-234">Una vez que haya configurado el tronco, continúe con la configuración de la omisión de medios seleccionando las opciones de omisión de multimedia global, como se describe en [Opciones de omisión de multimedia en Lync Server 2013](lync-server-2013-global-media-bypass-options.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="d1ffa-234">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1ffa-235">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1ffa-235">See Also</span></span>


[<span data-ttu-id="d1ffa-236">Configurar un tronco sin omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1ffa-236">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="d1ffa-237">Configurar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1ffa-237">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="d1ffa-238">Opciones de omisión de multimedia global en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1ffa-238">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="d1ffa-239">Definición de reglas de traducción en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1ffa-239">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

