---
title: 'Lync Server 2013: configuración de mensajería unificada en Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcbdbfbca5f532b1ca192cc0e9d89e93e3c8acb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="74822-102">Configurar la mensajería unificada en Microsoft Exchange para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74822-102">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74822-103">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="74822-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="74822-104">En este tema se describe cómo configurar la mensajería unificada de Exchange en un servidor de Microsoft Exchange para su uso con telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="74822-104">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74822-105">Los ejemplos de cmdlet de este tema proporcionan la sintaxis de la versión de Exchange 2007 del shell de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="74822-105">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="74822-106">Si está ejecutando Exchange 2010 o Exchange 2013, consulte la documentación correspondiente a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="74822-106">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="74822-107">Para configurar un servidor que ejecute mensajería unificada de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="74822-107">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="74822-108">Crear un plan de marcado identificador uniforme de recursos (URI) de protocolo de inicio de sesión (SIP) de UM para cada uno de los perfiles de ubicación de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="74822-108">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="74822-109">Si elige usar la consola de administración de Exchange, cree un nuevo plan de marcado con la configuración de seguridad **segura (preferida)**.</span><span class="sxs-lookup"><span data-stu-id="74822-109">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="74822-110">Si establece el valor de configuración de seguridad en <STRONG>SIP protegido</STRONG> para requerir el cifrado solo para el tráfico SIP, como se recomienda anteriormente, tenga en cuenta que esta configuración de seguridad en un plan de marcado es insuficiente si el grupo de servidores Front-End está configurado para requerir cifrado, lo que significa el grupo requiere cifrado para el tráfico de SIP y de RTP.</span><span class="sxs-lookup"><span data-stu-id="74822-110">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="74822-111">Cuando el plan de marcado y la configuración de seguridad del grupo no son compatibles, todas las llamadas a la mensajería unificada de Exchange desde el grupo de servidores front-end producirán un error que indica que tiene una "configuración de seguridad incompatible".</span><span class="sxs-lookup"><span data-stu-id="74822-111">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="74822-112">Si usa el shell de administración de Exchange, escriba:</span><span class="sxs-lookup"><span data-stu-id="74822-112">If you use the Exchange Management Shell, type:</span></span>
    
        New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    
    <span data-ttu-id="74822-113">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="74822-113">For details, see:</span></span>
    
      - <span data-ttu-id="74822-114">Para Office Communications Server 2007, consulte "cómo crear un plan de marcado URI del SIP de mensajería unificada" en [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) y "New-UMDialplan: Exchange 2007 [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)Help" en.</span><span class="sxs-lookup"><span data-stu-id="74822-114">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="74822-115">Para Exchange 2010, consulte "crear un plan de marcado de MU [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) " en y "New-UMDialplan: Exchange 2010 Help [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)" en.</span><span class="sxs-lookup"><span data-stu-id="74822-115">For Exchange 2010, see "Create a UM Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="74822-116">Para Exchange 2013, consulte "mensajería unificada" [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)en.</span><span class="sxs-lookup"><span data-stu-id="74822-116">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74822-117">Si selecciona un nivel de seguridad de <STRONG>SIPSecured</STRONG> o <STRONG>Secure</STRONG> , dependerá de si el protocolo de transporte seguro en tiempo real (SRTP) está activado o desactivado para el cifrado de multimedia.</span><span class="sxs-lookup"><span data-stu-id="74822-117">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="74822-118">Para la integración de Lync Server 2010 con la mensajería unificada de Exchange, debe coincidir con el nivel de cifrado en la configuración de multimedia de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74822-118">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="74822-119">Para ver la configuración de multimedia de Lync Server, ejecute el cmdlet <STRONG>Get-CsMediaConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="74822-119">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="74822-120">Para obtener más información, vea Get-CsMediaConfiguration en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74822-120">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="74822-121">Para más información sobre cómo seleccionar la configuración de seguridad de VoIP adecuada, vea <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">proceso de implementación para la integración de mensajería unificada local y Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="74822-121">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="74822-122">Ejecute el siguiente cmdlet para obtener el nombre de dominio completo (FQDN) de cada plan de marcado de MU:</span><span class="sxs-lookup"><span data-stu-id="74822-122">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ``` 
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="74822-123">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="74822-123">For details, see:</span></span>
    
      - <span data-ttu-id="74822-124">Para Exchange 2007, consulte "Get-UMDialplan: Exchange 2007 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678).</span><span class="sxs-lookup"><span data-stu-id="74822-124">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="74822-125">Para Exchange 2010, consulte "Get-UMDialplan: Exchange 2010 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679).</span><span class="sxs-lookup"><span data-stu-id="74822-125">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="74822-126">Para Exchange 2013, consulte "mensajería unificada" [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)en.</span><span class="sxs-lookup"><span data-stu-id="74822-126">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="74822-127">Grabe el nombre del plan de marcado de cada plan de marcado de MU.</span><span class="sxs-lookup"><span data-stu-id="74822-127">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="74822-128">Dependiendo de su versión de Exchange Server, es posible que tenga que usar el FQDN de cada nombre de plan de marcado más tarde como el nombre de cada plan de marcado de mensajería unificada de Lync Server correspondiente para que coincidan los nombres del plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="74822-128">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74822-129">Los nombres de los planes de marcado de Lync Server deben coincidir con los nombres de plan de marcado de MU solo si el plan de marcado de MU se está ejecutando en una versión de Exchange <EM>anterior</EM> a Exchange 2010 SP1.</span><span class="sxs-lookup"><span data-stu-id="74822-129">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="74822-130">Agregue el plan de marcado al servidor que ejecuta la mensajería unificada de Exchange de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="74822-130">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="74822-131">Si decide usar la consola de administración de Exchange, puede Agregar el plan de marcado desde la hoja de propiedades del servidor.</span><span class="sxs-lookup"><span data-stu-id="74822-131">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="74822-132">Para obtener instrucciones específicas, consulte la documentación del producto Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="74822-132">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="74822-133">Para Exchange 2007, consulte "cómo agregar un servidor de mensajería unificada a un plan de [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)marcado" en.</span><span class="sxs-lookup"><span data-stu-id="74822-133">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="74822-134">Para Exchange 2010, consulte "ver o configurar las propiedades de un servidor de mensajería unificada" en [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span><span class="sxs-lookup"><span data-stu-id="74822-134">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="74822-135">Para Exchange 2013, consulte "mensajería unificada" [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)en.</span><span class="sxs-lookup"><span data-stu-id="74822-135">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="74822-136">Si usa el shell de administración de Exchange, ejecute lo siguiente para cada uno de los servidores de mensajería unificada de Exchange:</span><span class="sxs-lookup"><span data-stu-id="74822-136">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        
            $ums=get-umserver; 
            $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
            $ums[0].DialPlans +=$dp.Identity; 
            set-umservice -instance $ums[0]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74822-137">Antes de realizar el siguiente paso, asegúrese de que todos los usuarios de Enterprise Voice se han configurado con un buzón de Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="74822-137">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="74822-138">Para Exchange 2007, consulte la biblioteca de TechNet de Exchange Server <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>2007 en.</span><span class="sxs-lookup"><span data-stu-id="74822-138">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="74822-139">Para Exchange 2010, consulte la biblioteca de TechNet de Exchange Server <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>2010 en.</span><span class="sxs-lookup"><span data-stu-id="74822-139">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="74822-140">Cuando especifique una directiva de buzón para cada plan de marcado que creó en el paso 1, seleccione la directiva predeterminada o la que ha creado.</span><span class="sxs-lookup"><span data-stu-id="74822-140">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="74822-141">Vaya a \<las secuencias de\>\\comandos del directorio de instalación de Exchange y, si Exchange se implementa en un único bosque, escriba:</span><span class="sxs-lookup"><span data-stu-id="74822-141">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    
        exchucutil.ps1
    
    <span data-ttu-id="74822-142">O bien, si Exchange se implementa en varios bosques, escriba:</span><span class="sxs-lookup"><span data-stu-id="74822-142">Or, if Exchange is deployed in multiple forests, type:</span></span>
    
        exchucutil.ps1 -Forest:"<forest FQDN>"
    
    <span data-ttu-id="74822-143">donde FQDN de bosque especifica el bosque en el que se implementa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74822-143">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="74822-144">Si tiene uno o varios planes de marcado de MU asociados con varias puertas de enlace IP, continúe con el paso 6.</span><span class="sxs-lookup"><span data-stu-id="74822-144">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="74822-145">Si los planes de marcado están asociados a una sola puerta de enlace IP, omita el paso 6.</span><span class="sxs-lookup"><span data-stu-id="74822-145">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="74822-146">Asegúrese de reiniciar el servicio <STRONG>front-end de Lync Server</STRONG> (RtcSrv. exe) <EM>después</EM> de ejecutar ExchUCUtil. ps1.</span><span class="sxs-lookup"><span data-stu-id="74822-146">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="74822-147">De lo contrario, Lync Server no detectará la mensajería unificada en la topología.</span><span class="sxs-lookup"><span data-stu-id="74822-147">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="74822-148">Con el shell de administración de Exchange o la consola de administración de Exchange, deshabilite las llamadas salientes para todas las puertas de enlace IP asociadas a cada uno de los planes de marcado, excepto una.</span><span class="sxs-lookup"><span data-stu-id="74822-148">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74822-149">Este paso es necesario para asegurarse de que las llamadas salientes realizadas por el servidor que ejecuta la mensajería unificada de Exchange Server a usuarios externos (por ejemplo, como sucede con los escenarios de reproducción en teléfono) atraviesen el Firewall de la empresa de manera confiable.</span><span class="sxs-lookup"><span data-stu-id="74822-149">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="74822-150">Al seleccionar la puerta de enlace IP de MU a través de la cual permitir llamadas salientes, elige la que es probable que gestione la mayor parte del tráfico.</span><span class="sxs-lookup"><span data-stu-id="74822-150">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="74822-151">No permita el tráfico saliente a través de una puerta de enlace IP que se conecte a un grupo de directores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74822-151">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="74822-152">Además, evite grupos en otro sitio central o en un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="74822-152">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="74822-153">Puede usar cualquiera de los métodos siguientes para bloquear las llamadas salientes para que no pasen por una puerta de enlace IP:</span><span class="sxs-lookup"><span data-stu-id="74822-153">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="74822-154">Si usa el shell de administración de Exchange, deshabilite cada puerta de enlace IP ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="74822-154">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        
            Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        
        <span data-ttu-id="74822-155">Para Exchange 2007, consulte "Set-UMIPGateway: Exchange 2007 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687).</span><span class="sxs-lookup"><span data-stu-id="74822-155">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="74822-156">Para Exchange 2010, consulte "Set-UMIPGateway: Exchange 2010 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688).</span><span class="sxs-lookup"><span data-stu-id="74822-156">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="74822-157">Si usa la consola de administración de Exchange, desactive la casilla **permitir llamadas salientes a través de esta puerta de enlace IP** .</span><span class="sxs-lookup"><span data-stu-id="74822-157">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="74822-158">Si el plan de marcado de URI del SIP de MU está asociado con una sola puerta de enlace IP, no devuelva las llamadas salientes a través de esta puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="74822-158">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="74822-159">Crear un operador automático de mensajería unificada para cada plan de marcado de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74822-159">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="74822-160">No incluya espacios en el nombre del operador automático.</span><span class="sxs-lookup"><span data-stu-id="74822-160">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
        New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    
    <span data-ttu-id="74822-161">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="74822-161">For details, see:</span></span>
    
      - <span data-ttu-id="74822-162">Para Exchange 2007, consulte "New-UMAutoAttendant: Exchange 2007 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689).</span><span class="sxs-lookup"><span data-stu-id="74822-162">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="74822-163">Para Exchange 2010, consulte "New-UMAutoAttendant: Exchange 2010 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690).</span><span class="sxs-lookup"><span data-stu-id="74822-163">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="74822-164">El paso siguiente debe realizarse para cada usuario después de haber habilitado a los usuarios de Lync Server para Enterprise Voice y conocer sus URI de SIP.</span><span class="sxs-lookup"><span data-stu-id="74822-164">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="74822-165">Asocie los usuarios de mensajería unificada de Exchange (cada uno de los cuales se debe configurar con un buzón de correo de Exchange) con el plan de marcado de MU y cree un URI de SIP para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="74822-165">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="74822-166">El <STRONG>SIPResourceIdentifier</STRONG> de la siguiente muestra debe ser la dirección SIP del usuario de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74822-166">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
        enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    
    <span data-ttu-id="74822-167">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="74822-167">For details, see:</span></span>
    
      - <span data-ttu-id="74822-168">Para Exchange 2007, consulte "Enable-UMMailbox: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)en.</span><span class="sxs-lookup"><span data-stu-id="74822-168">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="74822-169">Para Exchange 2010, consulte "Enable-UMMailbox: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)en.</span><span class="sxs-lookup"><span data-stu-id="74822-169">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

