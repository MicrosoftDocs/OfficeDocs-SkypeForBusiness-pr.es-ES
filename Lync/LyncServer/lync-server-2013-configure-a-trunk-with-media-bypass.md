---
title: 'Lync Server 2013: configurar un tronco con desvío de medios'
description: 'Lync Server 2013: configurar un tronco con desvío de medios.'
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
ms.openlocfilehash: 51bd58a685e1f4c222a863c21022b3c9dc7c70d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566756"
---
# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="46637-103">Configurar un tronco con la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46637-103">Configure a trunk with media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46637-104">_**Última modificación del tema:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="46637-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="46637-105">Siga estos pasos para configurar un tronco con la omisión de medios habilitada.</span><span class="sxs-lookup"><span data-stu-id="46637-105">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="46637-106">Para configurar un tronco con la omisión de medios deshabilitada, consulte [configurar un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="46637-106">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="46637-107">El desvío de medios es útil para minimizar la cantidad de servidores de mediación implementados.</span><span class="sxs-lookup"><span data-stu-id="46637-107">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="46637-108">En general, un grupo de servidores de mediación se implementa en un sitio central y controla puertas de enlace en los sitios de sucursal.</span><span class="sxs-lookup"><span data-stu-id="46637-108">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="46637-109">Habilitar el desvío de medios permite que las llamadas de red telefónica conmutada (RTC) desde clientes en sitios de sucursal se dirijan directamente a través de las puertas de enlace a esos sitios.</span><span class="sxs-lookup"><span data-stu-id="46637-109">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="46637-110">Lync Server 2013 las rutas de llamadas salientes y las directivas de Enterprise Voice deben configurarse correctamente para que las llamadas RTC de clientes de un sitio de sucursal se enruten a la puerta de enlace adecuada.</span><span class="sxs-lookup"><span data-stu-id="46637-110">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="46637-111">Se recomienda habilitar la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="46637-111">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="46637-112">Sin embargo, antes de habilitar la omisión de medios en un tronco SIP, confirme que su proveedor de tronco SIP calificado admite la omisión de medios y puede acomodar los requisitos para habilitar correctamente el escenario.</span><span class="sxs-lookup"><span data-stu-id="46637-112">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="46637-113">Concretamente, el proveedor debe tener las direcciones IP de los servidores en la red interna de la organización.</span><span class="sxs-lookup"><span data-stu-id="46637-113">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="46637-114">Si el proveedor no es compatible con este escenario, el desvío de medios no se efectuará correctamente.</span><span class="sxs-lookup"><span data-stu-id="46637-114">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="46637-115">Para obtener más información, consulte [planeación de la omisión de medios en Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="46637-115">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46637-116">La omisión de medios no interactuará con todas las puertas de enlace de red telefónica conmutada (RTC), IP-PBX y el controlador de borde de sesión (SBC).</span><span class="sxs-lookup"><span data-stu-id="46637-116">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="46637-117">Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con la IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="46637-117">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="46637-118">La omisión de medios solo se admite con productos y versiones que se enumeran en el programa de interoperabilidad abierta de comunicaciones unificadas – Lync Server en <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="46637-118">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="46637-119">Una configuración de tronco tal como se describe a continuación agrupa un conjunto de parámetros que se aplican a los troncos asignados a esta configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="46637-119">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="46637-120">Una configuración de tronco puede tener ámbito global (se aplica a todos los troncos que no tienen sitios o configuración de grupo más específicos), ámbito de sitio o de grupo.</span><span class="sxs-lookup"><span data-stu-id="46637-120">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="46637-121">La configuración del tronco de nivel de grupo se utiliza para adaptar una configuración de tronco específica a un único tronco.</span><span class="sxs-lookup"><span data-stu-id="46637-121">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="46637-122">Para configurar un tronco con desvío de medios</span><span class="sxs-lookup"><span data-stu-id="46637-122">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="46637-123">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="46637-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="46637-124">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="46637-124">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="46637-125">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46637-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="46637-126">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="46637-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="46637-127">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.</span><span class="sxs-lookup"><span data-stu-id="46637-127">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="46637-128">En la página **Configuración del tronco**, utilice uno de los métodos siguientes para configurar un tronco:</span><span class="sxs-lookup"><span data-stu-id="46637-128">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="46637-129">Haga doble clic en un tronco existente (por ejemplo, el tronco **Global**) para que aparezca el cuadro de diálogo **Editar configuración del tronco**.</span><span class="sxs-lookup"><span data-stu-id="46637-129">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="46637-130">Haga clic en **Nuevo** y, a continuación, seleccione un ámbito para la nueva configuración de tronco:</span><span class="sxs-lookup"><span data-stu-id="46637-130">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="46637-131">**Tronco del sitio:** Elija el sitio para esta configuración de tronco en **seleccionar un sitio**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46637-131">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="46637-132">Tenga en cuenta que si ya se ha creado una configuración de tronco para un sitio, el sitio no aparece en **Seleccionar un sitio**.</span><span class="sxs-lookup"><span data-stu-id="46637-132">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="46637-133">Esta configuración de tronco se aplicará a todos los troncos del sitio.</span><span class="sxs-lookup"><span data-stu-id="46637-133">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="46637-134">**Tronco de Grupo:** Elija el nombre del tronco al que se aplica esta configuración de tronco.</span><span class="sxs-lookup"><span data-stu-id="46637-134">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="46637-135">Este tronco puede ser el tronco raíz o los troncos adicionales definidos en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="46637-135">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="46637-136">En **seleccionar un servicio**, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46637-136">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="46637-137">Tenga en cuenta que si ya se ha creado una configuración de tronco para un tronco específico, el tronco no se mostrará en **Seleccionar un servicio**.</span><span class="sxs-lookup"><span data-stu-id="46637-137">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46637-138">Una vez seleccionado el ámbito de la configuración de tronco, no se podrá cambiar.</span><span class="sxs-lookup"><span data-stu-id="46637-138">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="46637-139">El campo <STRONG>Nombre</STRONG> está rellenado previamente con el nombre del sitio o servicio asociado a la configuración del tronco y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="46637-139">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="46637-140">Especifique un valor en **número máximo de diálogos iniciales admitidos**.</span><span class="sxs-lookup"><span data-stu-id="46637-140">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="46637-141">Número máximo de respuestas bifurcadas que puede recibir una puerta de enlace de red telefónica conmutada (RTC), IP-PBX o un controlador de borde de sesión (SBC) ITSP a una invitación enviada al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="46637-141">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="46637-142">El valor predeterminado es 20.</span><span class="sxs-lookup"><span data-stu-id="46637-142">The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46637-143">Antes de cambiar este valor, póngase en contacto con su proveedor de servicios o fabricante de equipos para obtener información detallada sobre las capacidades de su sistema.</span><span class="sxs-lookup"><span data-stu-id="46637-143">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="46637-144">Seleccione una de las opciones de **Nivel admitido de cifrado** siguientes:</span><span class="sxs-lookup"><span data-stu-id="46637-144">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="46637-145">**Obligatorio:** Se debe usar el cifrado de protocolo de transporte seguro en tiempo real (SRTP) para ayudar a proteger el tráfico entre el servidor de mediación y la puerta de enlace o central de conmutación (PBX).</span><span class="sxs-lookup"><span data-stu-id="46637-145">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="46637-146">**Opcional:** Se usará el cifrado SRTP si el proveedor de servicios o el fabricante del equipo lo admiten.</span><span class="sxs-lookup"><span data-stu-id="46637-146">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="46637-147">**No se admite:** El cifrado de SRTP no es compatible con el proveedor de servicios o el fabricante del equipo y, por lo tanto, no se usará.</span><span class="sxs-lookup"><span data-stu-id="46637-147">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="46637-148">Active la casilla **Habilitar desvío de medios** si desea que los medios omitan el servidor de mediación para que sea la entidad del mismo nivel que el tronco la que realice el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="46637-148">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="46637-149">Para que el desvío de medios funcione correctamente, es preciso que la puerta de enlace de RTC, el sistema PBX IP o el controlador de borde de sesión del proveedor de servicios sean compatibles con ciertas capacidades.</span><span class="sxs-lookup"><span data-stu-id="46637-149">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="46637-150">Para obtener más información, consulte <A href="lync-server-2013-planning-for-media-bypass.md">planeación de la omisión de medios en Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="46637-150">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="46637-p111">Active la casilla **Procesamiento de medios centralizado** si existe un punto de finalización de medios bien conocido (por ejemplo, una puerta de enlace RTC donde la finalización de medios tenga la misma IP que la finalización de señalización). Si el tronco no tiene un punto de terminación de medios conocido, desactive esta casilla.</span><span class="sxs-lookup"><span data-stu-id="46637-p111">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="46637-153">Si el tronco del mismo nivel admite la recepción de solicitudes SIP REFER del servidor de mediación, active la casilla de verificación **Habilitar la referencia de envío a la puerta de enlace** .</span><span class="sxs-lookup"><span data-stu-id="46637-153">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46637-154">Si deshabilita esta opción mientras la opción <STRONG>Habilitar desvío de medios</STRONG> está seleccionada, se requerirá una configuración adicional.</span><span class="sxs-lookup"><span data-stu-id="46637-154">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="46637-155">Si la entidad del mismo nivel del tronco no es compatible con la recepción de solicitudes SIP REFER del servidor de mediación y se ha habilitado el desvío de medios, es preciso que ejecute el cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> para deshabilitar el RTCP para las llamadas activas y en espera con el fin de admitir las condiciones adecuadas para el desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="46637-155">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="46637-156">Para obtener más información, consulte la documentación del <A href="lync-server-2013-lync-server-management-shell.md">Shell de administración de Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="46637-156">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="46637-157">Como alternativa, puede seleccionar <STRONG>Habilitar referencia mediante el control de llamadas de terceros</STRONG> si desea que se omitan los medios de las llamadas transferidas, y la puerta de enlace no admite solicitudes de referencia SIP.</span><span class="sxs-lookup"><span data-stu-id="46637-157">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="46637-p113">(Opcional) Para habilitar el enrutamiento entre troncos, asocie y configure los registros de uso de RTC a esta configuración de tronco. Los usos de RTC asociados a esta configuración de tronco se aplicarán a todas las llamadas entrantes al tronco que no tenga su origen en un extremo de Lync. Para administrar los registros de uso de RTC asociados a una configuración de tronco, use uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="46637-p113">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="46637-161">Para seleccionar uno o más registros de una lista de todos los registros de uso de RTC disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="46637-161">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="46637-162">Resalte los registros que desee asociar a esta configuración de tronco y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46637-162">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="46637-163">Para quitar un registro de uso de RTC de esta configuración de tronco, resalte el registro y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="46637-163">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="46637-164">Para definir un nuevo registro de uso de RTC y asociarlo a esta configuración de tronco:</span><span class="sxs-lookup"><span data-stu-id="46637-164">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="46637-165">Haga clic en  \*\*Nuevo \*\*.</span><span class="sxs-lookup"><span data-stu-id="46637-165">Click **New**.</span></span>
        
        2.  <span data-ttu-id="46637-166">En el campo **Nombre**, especifique un nombre descriptivo único para el registro.</span><span class="sxs-lookup"><span data-stu-id="46637-166">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="46637-p115">El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="46637-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="46637-169">Use uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="46637-169">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="46637-170">Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de la telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="46637-170">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="46637-171">Resalte las rutas que desea asociar a este registro de uso de RTC y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46637-171">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="46637-172">Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="46637-172">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="46637-173">Para definir una ruta nueva y asociarla a este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="46637-173">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="46637-174">Para obtener más información, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="46637-174">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="46637-175">Para editar una ruta ya asociada a este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="46637-175">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="46637-176">Para obtener más información, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="46637-176">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="46637-177">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46637-177">Click **OK**.</span></span>
    
      - <span data-ttu-id="46637-178">Para editar un registro de uso de RTC ya asociado a esta configuración de tronco, lleve a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="46637-178">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="46637-179">Seleccione el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="46637-179">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="46637-180">Use uno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="46637-180">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="46637-181">Para seleccionar una o más rutas de la lista de todas las rutas disponibles en la implementación de la telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="46637-181">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="46637-182">Resalte las rutas que desea asociar a este registro de uso de RTC y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46637-182">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="46637-183">Para quitar una ruta del registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="46637-183">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="46637-184">Para definir una ruta nueva y asociarla a este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="46637-184">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="46637-185">Para obtener más información, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="46637-185">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="46637-186">Para editar una ruta ya asociada a este registro de uso de RTC, seleccione la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="46637-186">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="46637-187">Para obtener más información, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="46637-187">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="46637-188">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46637-188">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="46637-189">Es importante asociar los registros de uso de RTC de acuerdo con el servidor de mediación del mismo nivel que está asociado al tronco que se está configurando.</span><span class="sxs-lookup"><span data-stu-id="46637-189">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="46637-190">Si el servidor de mediación del mismo nivel es una puerta de enlace RTC o un controlador de borde de sesión (SBC), se recomienda encarecidamente que la configuración del tronco no esté asociada a un registro de uso de RTC que se enrute a un destino de RTC o a cualquier otro sistema descendente conectado a través de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46637-190">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="46637-p123">Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, seleccione el registro de uso de RTC y haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="46637-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="46637-193">Es importante el orden en el que aparecen en la lista de la configuración de tronco los registros de uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="46637-193">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="46637-194">Lync Server recorre la lista de arriba a abajo.</span><span class="sxs-lookup"><span data-stu-id="46637-194">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="46637-195">**Habilite el cierre de RTP** para habilitar los medios de omisión para los clientes que se encuentren detrás de un firewall o una traducción de direcciones de red (NAT) y un SBC que admita pestillos.</span><span class="sxs-lookup"><span data-stu-id="46637-195">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="46637-196">**Habilite el historial de llamadas reenviadas** para habilitar el envío de información de historial de llamadas a la puerta de enlace del servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="46637-196">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="46637-197">**Habilitar reenvío de datos p-Asserted-Identity** debe seleccionarse para permitir que la información del autor de la llamada p-asserted-Identity (PAI) se reenvíe entre el lado del servidor de mediación y la puerta de enlace (y viceversa), cuando esté presente.</span><span class="sxs-lookup"><span data-stu-id="46637-197">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="46637-198">**Habilitar temporizador de conmutación por error de enrutamiento saliente** debe seleccionarse para habilitar la conmutación por error rápida.</span><span class="sxs-lookup"><span data-stu-id="46637-198">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="46637-199">La puerta de enlace asociada a este tronco puede proporcionar información cada 10 segundos durante el procesamiento de una llamada saliente.</span><span class="sxs-lookup"><span data-stu-id="46637-199">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="46637-200">Si el servidor de mediación no recibe esta notificación, se producirá el redireccionamiento a otro tronco.</span><span class="sxs-lookup"><span data-stu-id="46637-200">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="46637-201">Es necesario deshabilitar la conmutación por error rápida en las redes en las que la latencia puede retrasar el tiempo de respuesta o si la puerta de enlace tarda más de 10 segundos en responder.</span><span class="sxs-lookup"><span data-stu-id="46637-201">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="46637-202">(Opcional) Asocie y configure las **Reglas de traducción de números de llamada** para el tronco.</span><span class="sxs-lookup"><span data-stu-id="46637-202">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="46637-203">Estas reglas de traducción se aplican a los números de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="46637-203">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="46637-204">Para elegir una o más reglas de una lista de todas las reglas de conversión que están disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="46637-204">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="46637-205">En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46637-205">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="46637-206">Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="46637-206">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="46637-207">Para obtener más información sobre cómo definir una regla nueva, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="46637-207">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="46637-208">Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="46637-208">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="46637-209">Para obtener más información, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="46637-209">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="46637-210">Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar**y, a continuación, en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="46637-210">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="46637-211">Para obtener más información, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="46637-211">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="46637-212">Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="46637-212">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="46637-213">No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="46637-213">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="46637-p131">(Opcional) Asocie y configure las **Reglas de traducción de números llamados** para el tronco. Estas reglas de traducción se aplican a los números de llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="46637-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="46637-216">Para elegir una o más reglas de una lista de todas las reglas de conversión que están disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="46637-216">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="46637-217">En **Seleccionar reglas de conversión**, haga clic en las reglas que desee asociar con el tronco y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46637-217">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="46637-218">Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="46637-218">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="46637-219">Para obtener más información sobre cómo definir una regla nueva, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="46637-219">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="46637-220">Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="46637-220">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="46637-221">Para obtener más información, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="46637-221">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="46637-222">Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar**y, a continuación, en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="46637-222">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="46637-223">Para obtener más información, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="46637-223">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="46637-224">Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="46637-224">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="46637-225">No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas pudieran entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="46637-225">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="46637-226">Asegúrese de que las reglas de conversión del tronco estén organizadas en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="46637-226">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="46637-227">Para cambiar la posición de una regla en la lista, resalte el nombre de la regla y, a continuación, haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="46637-227">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="46637-228">Lync Server 2013 recorre la lista de reglas de conversión de arriba abajo y usa la primera regla que coincide con el número marcado.</span><span class="sxs-lookup"><span data-stu-id="46637-228">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="46637-229">Si configura un tronco de forma que un número marcado puede coincidir con más de una regla de conversión, asegúrese de que las reglas más restrictivas estén dispuestas encima de las reglas menos restrictivas.</span><span class="sxs-lookup"><span data-stu-id="46637-229">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="46637-230">Por ejemplo, si ha incluido una regla de conversión que coincida con cualquier número de 11 dígitos y una regla de conversión que coincida solamente con números de 11 dígitos que comiencen por -1425, asegúrese de que la regla que coincida con cualquier número de 11 dígitos se haya colocado <EM>debajo</EM> de la regla más restrictiva.</span><span class="sxs-lookup"><span data-stu-id="46637-230">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="46637-231">Cuando haya terminado de configurar el tronco, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46637-231">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="46637-232">En la página **Configuración del tronco**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="46637-232">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46637-233">Siempre que cree o modifique una configuración de tronco, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="46637-233">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="46637-234">Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="46637-234">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="46637-235">Una vez configurado el tronco, siga configurando la omisión de medios seleccionando Opciones de omisión de medios globales, como se describe en [opciones globales de omisión de medios en Lync Server 2013](lync-server-2013-global-media-bypass-options.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="46637-235">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46637-236">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46637-236">See Also</span></span>


[<span data-ttu-id="46637-237">Configurar un tronco sin omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46637-237">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="46637-238">Configurar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46637-238">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="46637-239">Opciones de omisión de medios globales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46637-239">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="46637-240">Definición de reglas de conversión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46637-240">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

