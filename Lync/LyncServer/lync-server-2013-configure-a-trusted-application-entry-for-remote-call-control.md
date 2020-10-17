---
title: Configurar una entrada de aplicación de confianza para control remoto de llamadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f8175a351d13675c048efce7a2f831af7ab2c31
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523067"
---
# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="cc9e4-102">Configurar una entrada de aplicación de confianza para el control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc9e4-102">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc9e4-103">_**Última modificación del tema:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="cc9e4-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="cc9e4-104">La puerta de enlace SIP/CSTA debe estar configurada como aplicación de confianza para que Lync Server aplique una ruta estática para enrutar las llamadas a la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="cc9e4-104">The SIP/CSTA gateway must be configured as a trusted application in order for Lync Server to apply a static route to route calls to the gateway.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="cc9e4-105">Si va a migrar usuarios de una versión anterior de la implementación de Lync Server, asegúrese de que ha quitado todas las entradas de aplicaciones de confianza existentes (anteriormente conocidas como entradas de host autorizadas) que creó para la puerta de enlace SIP/CSTA antes de seguir los procedimientos de este tema.</span><span class="sxs-lookup"><span data-stu-id="cc9e4-105">If you're migrating users from a previous version of Lync Server deployment, be sure that you removed all existing trusted application entries (previously known as authorized host entries) you created for the SIP/CSTA gateway before following the procedures in this topic.</span></span> <span data-ttu-id="cc9e4-106">Para obtener más información, consulte <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">quitar un host autorizado heredado en Lync Server 2013 (opcional)</A>.</span><span class="sxs-lookup"><span data-stu-id="cc9e4-106">For details, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span><BR><span data-ttu-id="cc9e4-107">Si tiene previsto implementar un nuevo control remoto de llamadas mediante una conexión de protocolo de control de transmisión (TCP), debe comprobar que el <STRONG>uso del servicio límite para las direcciones IP seleccionadas</STRONG> se establezca en las aplicaciones y grupos de confianza existentes, si desea usar el mismo puerto TCP para la nueva aplicación de confianza.</span><span class="sxs-lookup"><span data-stu-id="cc9e4-107">If you plan to deploy new remote call control by using a Transmission Control Protocol (TCP) connection, you need to verify that <STRONG>Limit service usage to selected IP addresses</STRONG> should be set on existing trusted applications and pools, if you want to use the same TCP port for the new trusted application.</span></span>



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a><span data-ttu-id="cc9e4-108">Para configurar una entrada de aplicación de confianza para la puerta de enlace SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="cc9e4-108">To configure a trusted application entry for the SIP/CSTA gateway</span></span>

1.  <span data-ttu-id="cc9e4-109">Inicie sesión en el equipo donde esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o un rol de control de acceso basado en roles (RBAC) al que haya asignado el cmdlet **New-CsTrustedApplicationPool** .</span><span class="sxs-lookup"><span data-stu-id="cc9e4-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsTrustedApplicationPool** cmdlet.</span></span>

2.  <span data-ttu-id="cc9e4-110">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="cc9e4-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cc9e4-111">Para crear una entrada de aplicación de confianza, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cc9e4-111">To create a trusted application entry, do one of the following:</span></span>
    
      - <span data-ttu-id="cc9e4-112">Para una conexión de Seguridad de la capa de transporte (TLS), escriba el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="cc9e4-112">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="cc9e4-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cc9e4-113">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - <span data-ttu-id="cc9e4-114">Para una conexión de Protocolo de control de transmisión (TCP), escriba el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="cc9e4-114">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="cc9e4-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cc9e4-115">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  <span data-ttu-id="cc9e4-116">Para agregar la aplicación de confianza al grupo, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cc9e4-116">To add the trusted application to the pool, do one of the following:</span></span>
    
      - <span data-ttu-id="cc9e4-117">Para una conexión TLS, escriba el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="cc9e4-117">For a TLS connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        <span data-ttu-id="cc9e4-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cc9e4-118">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - <span data-ttu-id="cc9e4-119">Para una conexión TCP, escriba el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="cc9e4-119">For a TCP connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        <span data-ttu-id="cc9e4-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cc9e4-120">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  <span data-ttu-id="cc9e4-121">Para implementar los cambios publicados que haya efectuado a la topología, escriba el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="cc9e4-121">To implement the published changes you have made to the topology, type the following at the command prompt:</span></span>
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc9e4-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cc9e4-122">See Also</span></span>


[<span data-ttu-id="cc9e4-123">Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc9e4-123">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="cc9e4-124">Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc9e4-124">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

