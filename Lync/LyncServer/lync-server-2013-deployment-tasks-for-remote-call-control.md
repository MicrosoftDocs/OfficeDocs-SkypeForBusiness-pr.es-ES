---
title: 'Lync Server 2013: tareas de implementación para el control remoto de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b81da85fb7aff98728d0a79478164436cce5194a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="3d8ae-102">Tareas de implementación para el control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d8ae-102">Deployment tasks for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d8ae-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="3d8ae-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="3d8ae-104">En este tema se describen las tareas de implementación que debe realizar para habilitar el control remoto de llamadas para los usuarios de su entorno de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-104">This topic describes the deployment tasks that you must perform to enable remote call control for users in your Lync Server environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3d8ae-105">Si va a migrar usuarios habilitados previamente para control remoto de llamadas en Microsoft Office Communicator 2007 R2, debe realizar una tarea de implementación adicional antes de comenzar a realizar las tareas de implementación del control remoto de llamadas descritas en este tema.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-105">If you are migrating users previously enabled for remote call control in Microsoft Office Communicator 2007 R2, you must perform an additional deployment task before you begin performing the remote call control deployment tasks described in this topic.</span></span> <span data-ttu-id="3d8ae-106">Durante el proceso de migración a Lync Server, las entradas de las aplicaciones de confianza (antes conocidas como <EM>entradas de host autorizadas</EM>) deben quitarse con las herramientas administrativas de Office Communications Server 2007 R2, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-106">During the migration process to Lync Server, trusted application entries (previously known as <EM>authorized host entries</EM>) must be removed by using the Office Communications Server 2007 R2 administrative tools, as appropriate.</span></span><BR><span data-ttu-id="3d8ae-107">Para obtener información detallada sobre cómo quitar hosts autorizados, consulte <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a Legacy host Authorized host in Lync Server 2013 (optional)</A>.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-107">For details about removing authorized hosts, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span>



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a><span data-ttu-id="3d8ae-108">Paso 1: Instalar y configurar la puerta de enlace SIP/CSTA para comunicarse con la central de conmutación</span><span class="sxs-lookup"><span data-stu-id="3d8ae-108">Step 1: Install and Configure the SIP/CSTA Gateway to Communicate with Your PBX</span></span>

<span data-ttu-id="3d8ae-109">Debe instalar al menos una puerta de enlace SIP/CSTA que pueda conectarse a Lync Server y a la central de conmutación (PBX) existente en su entorno para proporcionar características de control remoto de llamadas a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-109">You need to install at least one SIP/CSTA gateway that can connect to both Lync Server and the existing private branch exchange (PBX) in your environment in order to provide remote call control features to your users.</span></span> <span data-ttu-id="3d8ae-110">Una puerta de enlace SIP/CSTA es una puerta de enlace entre SIP y la CSTA (aplicación de telecomunicaciones para equipo).</span><span class="sxs-lookup"><span data-stu-id="3d8ae-110">A SIP/CSTA gateway is a gateway between SIP and a computer-supported telecommunications application (CSTA).</span></span> <span data-ttu-id="3d8ae-111">Independientemente del número de puertas de enlace que se hayan instalado, todos los usuarios se pueden configurar con tan solo una puerta de enlace o PBX.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-111">Whether you install multiple gateways or just one, each user can be configured with only one gateway or PBX.</span></span> <span data-ttu-id="3d8ae-112">En caso de que la PBX existente carezca de una interfaz de SIP/CSTA, asegúrese de que implementa una puerta de enlace SIP/CSTA que admita la PBX, así como los protocolos de señalización específicos del proveedor de la PBX en cuestión.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-112">If your existing PBX does not have a SIP/CSTA interface, ensure you deploy a SIP/CSTA gateway that can support the PBX, including support for proprietary PBX vendor-specific signaling protocols.</span></span> <span data-ttu-id="3d8ae-113">Para obtener información detallada sobre estas funciones, acuda directamente al proveedor.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-113">For details about capabilities, consult each vendor directly.</span></span>

<span data-ttu-id="3d8ae-114">Cuando esté listo para implementar una puerta de enlace SIP/CSTA que pueda integrarse con Lync Server para el control remoto de llamadas, consulte también con el proveedor de la puerta de enlace o con la documentación de la puerta de enlace del proveedor para conocer la sintaxis requerida por la puerta de enlace para obtener la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="3d8ae-114">When you are ready to deploy a SIP/CSTA gateway that can integrate with Lync Server for remote call control, also consult with your gateway vendor or the vendor’s gateway documentation regarding the syntax required by the gateway for the following information:</span></span>

  - <span data-ttu-id="3d8ae-115">URI del servidor de línea de la puerta de enlace</span><span class="sxs-lookup"><span data-stu-id="3d8ae-115">Line server URI of the gateway</span></span>

  - <span data-ttu-id="3d8ae-116">URI de línea de los usuarios que se van a asignar a la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-116">Line URI for users that will be assigned to the gateway</span></span>

<span data-ttu-id="3d8ae-117">La configuración anterior es necesaria durante la configuración de usuario y se debe especificar tal y como la puerta de enlace espera encontrarla para enrutar y conectarse a la PBX sin problemas.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-117">The preceding settings are required during user configuration and must be specified as expected by the gateway to route and connect to the PBX properly.</span></span>

<span data-ttu-id="3d8ae-118">Puede consultar a los proveedores en el sitio web del programa de interoperabilidad abierta [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309)de comunicaciones unificadas de Microsoft en.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-118">You can refer to vendors on the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a><span data-ttu-id="3d8ae-119">Paso 2: configurar Lync Server para enrutar las solicitudes CSTA a la puerta de enlace SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="3d8ae-119">Step 2: Configure Lync Server to Route CSTA Requests to the SIP/CSTA Gateway</span></span>

<span data-ttu-id="3d8ae-120">Debe crear rutas estáticas en los grupos de Lync Server a la dirección de destino (URI de servidor) de todas las puertas de enlace SIP/CSTA de la implementación a la que desea enrutar las solicitudes de control de llamadas remotas.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-120">You must create static routes on Lync Server pools to the destination address (server URI) of all SIP/CSTA gateways in your deployment to which you intend to route remote call control requests.</span></span> <span data-ttu-id="3d8ae-121">Asimismo, deberá crear una entrada de aplicación de confianza que se corresponda con cada dirección de destino.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-121">You must also create a trusted application entry that corresponds to each destination address.</span></span> <span data-ttu-id="3d8ae-122">Al designar la puerta de enlace como una aplicación de confianza, se le concede el estado de confianza para que se ejecute como parte del entorno de Lync Server, aunque la haya desarrollado un tercero (y ejecute lo que se conoce como *servicio externo* porque es un servicio que no es una parte integrada del producto).</span><span class="sxs-lookup"><span data-stu-id="3d8ae-122">When you designate the gateway as a trusted application, it is given trusted status to run as part of the Lync Server environment even though it is developed by a third party (and runs what is referred to as an *external service* because it is a service that is not a built-in part of the product).</span></span> <span data-ttu-id="3d8ae-123">Por último, si Lync Server se conectará a la puerta de enlace SIP/CSTA con una conexión de protocolo de control de transmisión (TCP) en lugar de con una conexión de seguridad de la capa de transporte (TLS), también debe definir la dirección IP de la puerta de enlace mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-123">Finally, if Lync Server will connect to the SIP/CSTA gateway using a Transmission Control Protocol (TCP) connection instead of a Transport Layer Security (TLS) connection, you must also define the gateway IP address by using Topology Builder.</span></span>

<span data-ttu-id="3d8ae-124">Para obtener más información sobre cómo configurar rutas estáticas, vea [configurar una ruta estática para el control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="3d8ae-124">For details about configuring static routes, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span></span>

<span data-ttu-id="3d8ae-125">Para obtener más información sobre cómo configurar entradas de aplicaciones de confianza, consulte [configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="3d8ae-125">For details about configuring trusted application entries, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span></span>

<span data-ttu-id="3d8ae-126">Para obtener más información sobre cómo definir una dirección IP de puerta de enlace SIP/CSTA en el generador de topologías, consulte [definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span><span class="sxs-lookup"><span data-stu-id="3d8ae-126">For details about defining a SIP/CSTA gateway IP address in Topology Builder, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span></span>

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a><span data-ttu-id="3d8ae-127">Paso 3: configurar los usuarios de Lync para el control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="3d8ae-127">Step 3: Configure Lync Users for Remote Call Control</span></span>

<span data-ttu-id="3d8ae-128">Una vez que se hayan habilitado los usuarios en Lync Server, puede usar el panel de control de Lync Server o el shell de administración de Lync Server para habilitarlos para el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-128">After users have been enabled for Lync Server, you can use Lync Server Control Panel or Lync Server Management Shell to enable them for remote call control.</span></span> <span data-ttu-id="3d8ae-129">Durante este paso de implementación, se asigna a cada usuario un URI de línea de servidor y un URI de línea.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-129">It is during this deployment step that you assign each user a line server URI and a line URI.</span></span> <span data-ttu-id="3d8ae-130">El URI del servidor de línea es el URI del SIP de la puerta de enlace SIP/CSTA que va a asignar al usuario.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-130">The line server URI is the SIP URI of the SIP/CSTA gateway that you plan to assign to the user.</span></span> <span data-ttu-id="3d8ae-131">El URI de línea es el número de teléfono único asignado al usuario.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-131">The line URI is the unique phone number assigned to the user.</span></span>

<span data-ttu-id="3d8ae-132">Para más información sobre cómo configurar usuarios para el control remoto de llamadas, consulte [Habilitar usuarios de Lync para el control remoto de llamadas en Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="3d8ae-132">For details about configuring users for remote call control, see [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a><span data-ttu-id="3d8ae-133">Paso 4: Definir las reglas de normalización de números de teléfono de Lync Server</span><span class="sxs-lookup"><span data-stu-id="3d8ae-133">Step 4: Define the Lync Server Phone Number Normalization Rules</span></span>

<span data-ttu-id="3d8ae-134">En los escenarios de control remoto de llamadas, Lync Server usa reglas de normalización de números de teléfono para convertir los números de teléfono que recibe de la puerta de enlace SIP/CSTA al formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-134">In remote call control scenarios, Lync Server uses phone number normalization rules to convert phone numbers it receives from the SIP/CSTA gateway to E.164 format.</span></span> <span data-ttu-id="3d8ae-135">Los números de teléfono deben estar en este formato estandarizado para que determinadas características de control remoto de llamadas funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-135">Phone numbers must be in this standardized format for certain remote call control features to function properly.</span></span> <span data-ttu-id="3d8ae-136">El control remoto de llamadas usa las mismas reglas de normalización de números de teléfono que se configuran para la normalización de números de teléfono del servicio de libreta de direcciones, que son diferentes de las reglas de normalización de números de teléfono usadas para Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="3d8ae-136">Remote call control uses the same phone number normalization rules that you configure for Address Book Service phone number normalization, which are different from the phone number normalization rules used for Enterprise Voice.</span></span>

<span data-ttu-id="3d8ae-137">Para obtener más información sobre cómo el control remoto de llamadas usa reglas de normalización de números de teléfono, consulte [control remoto de llamadas y normalización de números de teléfono en Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span><span class="sxs-lookup"><span data-stu-id="3d8ae-137">For details about how remote call control uses phone number normalization rules, see [Remote call control and phone number normalization in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span></span> <span data-ttu-id="3d8ae-138">Para obtener más información sobre las reglas de normalización de números de teléfono para el servicio de libreta de direcciones, consulte el tema [Administración del servicio de libreta de direcciones en Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="3d8ae-138">For details about phone number normalization rules for Address Book Service, see [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

