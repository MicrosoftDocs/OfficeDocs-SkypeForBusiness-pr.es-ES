---
title: 'Lync Server 2013: configurar la mensajería unificada en Microsoft Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57e48e0ee3e7ef2b9a755ecbd64afaa0f2ce3c2e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="c08e8-102">Configurar la mensajería unificada en Microsoft Exchange para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c08e8-102">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c08e8-103">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c08e8-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="c08e8-104">En este tema se describe cómo configurar la mensajería unificada (MU) de Exchange en un servidor de Microsoft Exchange para su uso con telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="c08e8-104">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c08e8-105">Los ejemplos de cmdlet de este tema proporcionan sintaxis para la versión Exchange 2007 del shell de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c08e8-105">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="c08e8-106">Si está ejecutando Exchange 2010 o Exchange 2013, consulte la documentación correspondiente a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="c08e8-106">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="c08e8-107">Para configurar un servidor que ejecuta la mensajería unificada de Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c08e8-107">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="c08e8-p102">Cree un plan de marcado del Identificador uniforme de recursos (URI) del Protocolo de inicio de sesión (SIP) para cada uno de sus perfiles de ubicación de Enterprise Voice. Si decide usar la Consola de administración de Exchange, cree un nuevo plan de marcado con la configuración de seguridad **Secured (preferiblemente)**.</span><span class="sxs-lookup"><span data-stu-id="c08e8-p102">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles. If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c08e8-110">Si establece el valor de configuración de seguridad en <STRONG>SIP Secured</STRONG> para requerir cifrado únicamente para el tráfico SIP, como se ha recomendado anteriormente, tenga en cuenta que esta configuración de seguridad del plan de marcado resulta insuficiente si el grupo de servidores front-end está configurado para requerir cifrado, lo que significa que el grupo de servidores requiere cifrado tanto para el tráfico SIP como para tráfico RTP.</span><span class="sxs-lookup"><span data-stu-id="c08e8-110">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="c08e8-111">Si el plan de marcado y la configuración de seguridad del grupo no son compatibles, se producirá un error en todas las llamadas a la mensajería unificada de Exchange del grupo de servidores front-end, lo que indicará que hay una "configuración de seguridad incompatible".</span><span class="sxs-lookup"><span data-stu-id="c08e8-111">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="c08e8-112">Si utiliza el Shell de administración de Exchange, escriba:</span><span class="sxs-lookup"><span data-stu-id="c08e8-112">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="c08e8-113">Para más información, vea:</span><span class="sxs-lookup"><span data-stu-id="c08e8-113">For details, see:</span></span>
    
      - <span data-ttu-id="c08e8-114">Para Office Communications Server 2007, consulte "cómo crear un plan de marcado de URI de SIP de mensajería [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) unificada" en y "New-UMDialplan: Exchange [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)2007 Help" en.</span><span class="sxs-lookup"><span data-stu-id="c08e8-114">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="c08e8-115">Para Exchange 2010, consulte "crear un plan de marcado de mensajería [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) unificada" en y "New-UMDialplan: Exchange [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)2010 Help" en.</span><span class="sxs-lookup"><span data-stu-id="c08e8-115">For Exchange 2010, see "Create a UM Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="c08e8-116">Para Exchange 2013, consulte "mensajería unificada" [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)en.</span><span class="sxs-lookup"><span data-stu-id="c08e8-116">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c08e8-117">El hecho de seleccionar un nivel de seguridad <STRONG>SIPSecured</STRONG> o <STRONG>Secured</STRONG> dependerá de si el Protocolo de transporte seguro en tiempo real (SRTP) está activado o desactivado para el cifrado de medios.</span><span class="sxs-lookup"><span data-stu-id="c08e8-117">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="c08e8-118">Para la integración de Lync Server 2010 con mensajería unificada de Exchange, debe corresponderse con el nivel de cifrado en la configuración de medios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c08e8-118">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="c08e8-119">Para ver la configuración de medios de Lync Server, ejecute el cmdlet <STRONG>Get-CsMediaConfiguration</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c08e8-119">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="c08e8-120">Para obtener más información, consulte Get-CsMediaConfiguration en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c08e8-120">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="c08e8-121">Para obtener información detallada sobre cómo seleccionar la configuración de seguridad de VoIP adecuada, vea <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">proceso de implementación para integrar la mensajería unificada local y Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c08e8-121">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="c08e8-122">Ejecute el siguiente cmdlet para obtener el nombre de dominio completo (FQDN) de cada plan de marcado de Mensajería unificada:</span><span class="sxs-lookup"><span data-stu-id="c08e8-122">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="c08e8-123">Para más información, vea:</span><span class="sxs-lookup"><span data-stu-id="c08e8-123">For details, see:</span></span>
    
      - <span data-ttu-id="c08e8-124">Para Exchange 2007, consulte "Get-UMDialplan: Exchange 2007 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678).</span><span class="sxs-lookup"><span data-stu-id="c08e8-124">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="c08e8-125">Para Exchange 2010, consulte "Get-UMDialplan: Exchange 2010 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679).</span><span class="sxs-lookup"><span data-stu-id="c08e8-125">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="c08e8-126">Para Exchange 2013, consulte "mensajería unificada" [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)en.</span><span class="sxs-lookup"><span data-stu-id="c08e8-126">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="c08e8-127">Registre el nombre de plan de marcado de cada uno de los planes de marcado de Mensajería unificada.</span><span class="sxs-lookup"><span data-stu-id="c08e8-127">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="c08e8-128">En función de la versión de Exchange Server, es posible que deba usar el FQDN de cada nombre de plan de marcado más adelante como nombre del plan de marcado de Lync Server correspondiente a cada plan de marcado de MU para que los nombres del plan de marcado sean coincidentes.</span><span class="sxs-lookup"><span data-stu-id="c08e8-128">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c08e8-129">Los nombres del plan de marcado de Lync Server deben coincidir con los nombres de plan de marcado de mensajería unificada solo si el plan de marcado de MU se está ejecutando en una versión de Exchange <EM>anterior</EM> a Exchange 2010 SP1.</span><span class="sxs-lookup"><span data-stu-id="c08e8-129">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="c08e8-130">Agregue el plan de marcado al servidor que ejecuta la mensajería unificada de Exchange de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c08e8-130">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="c08e8-p106">Si decide usar la Consola de administración de Exchange, puede agregar el plan de marcado desde la hoja de propiedades del servidor. Para obtener instrucciones específicas, consulte la documentación de producto de Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="c08e8-p106">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server. For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="c08e8-133">Para Exchange 2007, consulte "cómo agregar un servidor de mensajería unificada a un plan de [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)marcado" en.</span><span class="sxs-lookup"><span data-stu-id="c08e8-133">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="c08e8-134">Para Exchange 2010, consulte "ver o configurar las propiedades de un servidor de mensajería unificada" en [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span><span class="sxs-lookup"><span data-stu-id="c08e8-134">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="c08e8-135">Para Exchange 2013, consulte "mensajería unificada" [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)en.</span><span class="sxs-lookup"><span data-stu-id="c08e8-135">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="c08e8-136">Si usa el Shell de administración de Exchange, ejecute lo siguiente para cada uno de los servidores de mensajería unificada de Exchange:</span><span class="sxs-lookup"><span data-stu-id="c08e8-136">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c08e8-137">Antes de realizar el siguiente paso, asegúrese de que todos los usuarios de Enterprise Voice se hayan configurado con un buzón de correo de Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="c08e8-137">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="c08e8-138">Para Exchange 2007, consulte la biblioteca de TechNet de Exchange Server <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>2007 en.</span><span class="sxs-lookup"><span data-stu-id="c08e8-138">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="c08e8-139">Para Exchange 2010, consulte la biblioteca de TechNet de Exchange Server <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>2010 en.</span><span class="sxs-lookup"><span data-stu-id="c08e8-139">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="c08e8-140">A la hora de especificar una directiva de buzón de correo para cada plan de marcado creado en el paso 1, seleccione la directiva predeterminada o una que haya creado.</span><span class="sxs-lookup"><span data-stu-id="c08e8-140">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="c08e8-141">Vaya a \<los scripts\>\\del directorio de instalación de Exchange y, en caso de que Exchange se haya implementado en un único bosque, escriba:</span><span class="sxs-lookup"><span data-stu-id="c08e8-141">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="c08e8-142">Si Exchange se implementa en varios bosques, escriba:</span><span class="sxs-lookup"><span data-stu-id="c08e8-142">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="c08e8-143">donde FQDN del bosque especifica el bosque en el que se implementa Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c08e8-143">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="c08e8-p107">Si tiene uno o más planes de marcado de Mensajería unificada que estén asociados a varias puertas de enlace de IP, continúe en el paso 6. Si los planes de marcado están asociados a una única puerta de enlace de IP, omita el paso 6.</span><span class="sxs-lookup"><span data-stu-id="c08e8-p107">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6. If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c08e8-146">Asegúrese de reiniciar el servicio <STRONG>Front-end de Lync Server</STRONG> (rtcsrv.exe) <EM>después</EM> de ejecutar exchucutil.ps1.</span><span class="sxs-lookup"><span data-stu-id="c08e8-146">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="c08e8-147">De lo contrario, Lync Server no detectará la mensajería unificada en la topología.</span><span class="sxs-lookup"><span data-stu-id="c08e8-147">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="c08e8-148">Utilizando el Shell de administración de Exchange o bien la Consola de administración de Exchange, deshabilite las llamadas realizadas de todas las puertas de enlace IP asociadas a cada uno de los planes de marcado, excepto de una.</span><span class="sxs-lookup"><span data-stu-id="c08e8-148">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c08e8-149">Este paso es necesario para asegurarse de que las llamadas salientes realizadas por el servidor que ejecuta la mensajería unificada de Exchange Server a los usuarios externos (por ejemplo, como en el caso de los escenarios de reproducción en teléfono) atraviesen de forma confiable el Firewall corporativo.</span><span class="sxs-lookup"><span data-stu-id="c08e8-149">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c08e8-150">Cuando seleccione la puerta de enlace IP de mensajería unificada a través de la cual van a pasar las llamadas realizadas, elija la que probablemente vaya a administrar la mayor parte del tráfico.</span><span class="sxs-lookup"><span data-stu-id="c08e8-150">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="c08e8-151">No permita el tráfico saliente a través de una puerta de enlace IP que se conecte a un grupo de directores de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c08e8-151">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="c08e8-152">Evite también los grupos de servidores en otro sitio central o sucursal.</span><span class="sxs-lookup"><span data-stu-id="c08e8-152">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="c08e8-153">Puede usar alguno de los métodos siguientes para impedir que las llamadas realizadas pasen por una puerta de enlace IP:</span><span class="sxs-lookup"><span data-stu-id="c08e8-153">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="c08e8-154">Si utiliza el Shell de administración de Exchange, deshabilite cada puerta de enlace de IP ejecutando el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="c08e8-154">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="c08e8-155">Para Exchange 2007, consulte "Set-UMIPGateway: ayuda de Exchange 2007" [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)en.</span><span class="sxs-lookup"><span data-stu-id="c08e8-155">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="c08e8-156">Para Exchange 2010, consulte "Set-UMIPGateway: ayuda de Exchange 2010" [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)en.</span><span class="sxs-lookup"><span data-stu-id="c08e8-156">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="c08e8-157">Si utiliza la Consola de administración de Exchange, desactive la casilla **Permitir llamadas realizadas a través de esta puerta de enlace IP de MU**.</span><span class="sxs-lookup"><span data-stu-id="c08e8-157">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c08e8-158">Si su plan de marcado del URI del SIP de Mensajería unificada está asociado a una única puerta de enlace IP, no impida que las llamadas realizadas pasen a través de esta puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="c08e8-158">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="c08e8-159">Cree un operador automático de mensajería unificada para cada plan de marcado de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c08e8-159">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c08e8-160">No incluya espacios en el nombre del operador automático.</span><span class="sxs-lookup"><span data-stu-id="c08e8-160">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="c08e8-161">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="c08e8-161">For details, see:</span></span>
    
      - <span data-ttu-id="c08e8-162">Para Exchange 2007, consulte "New-UMAutoAttendant: Exchange 2007 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689).</span><span class="sxs-lookup"><span data-stu-id="c08e8-162">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="c08e8-163">Para Exchange 2010, consulte "New-UMAutoAttendant: Exchange 2010 Help" en [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690).</span><span class="sxs-lookup"><span data-stu-id="c08e8-163">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="c08e8-164">El siguiente paso debe realizarse para cada usuario después de haber habilitado a los usuarios de Lync Server para la telefonía IP empresarial y conocer sus URI de SIP.</span><span class="sxs-lookup"><span data-stu-id="c08e8-164">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="c08e8-165">Asocie los usuarios de Mensajería unificada de Exchange (cada uno de los cuales debe haberse configurado con un buzón de correo de Exchange) al plan de marcado de Mensajería unificada y cree un URI de SIP para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="c08e8-165">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c08e8-166">El <STRONG>SIPResourceIdentifier</STRONG> del siguiente ejemplo debe ser la dirección SIP del usuario de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c08e8-166">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="c08e8-167">Para más información, vea:</span><span class="sxs-lookup"><span data-stu-id="c08e8-167">For details, see:</span></span>
    
      - <span data-ttu-id="c08e8-168">Para Exchange 2007, consulte "Enable-UMMailbox: Exchange 2007 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)en.</span><span class="sxs-lookup"><span data-stu-id="c08e8-168">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="c08e8-169">Para Exchange 2010, consulte "Enable-UMMailbox: Exchange 2010 Help" [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)en.</span><span class="sxs-lookup"><span data-stu-id="c08e8-169">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

