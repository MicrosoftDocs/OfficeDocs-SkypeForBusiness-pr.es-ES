---
title: 'Lync Server 2013: Configurar una ruta estática para el control remoto de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6a388c602d30e6f60eac0c575d7640f63993f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="b74f2-102">Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b74f2-102">Configure a static route for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b74f2-103">_**Última modificación del tema:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="b74f2-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="b74f2-104">El control remoto de llamadas requiere que cada grupo de servidores Lync esté configurado con una ruta de acceso de ese grupo a la puerta de enlace SIP/CSTA que se conecta a la central de conmutación (PBX).</span><span class="sxs-lookup"><span data-stu-id="b74f2-104">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="b74f2-105">Esta ruta requiere que cada grupo tenga una ruta estática para cada una de las puertas de enlace a las que el grupo se dirigirá por proxy los mensajes de control de llamada SIP asociados con llamadas a la PBX.</span><span class="sxs-lookup"><span data-stu-id="b74f2-105">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="b74f2-106">Si configura una ruta estática global para el control remoto de llamadas, cada grupo de servidores que no esté configurado con una ruta estática en el nivel del grupo usará la ruta estática global.</span><span class="sxs-lookup"><span data-stu-id="b74f2-106">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="b74f2-107">Para configurar una ruta estática para el control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="b74f2-107">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="b74f2-108">Inicie sesión en un equipo en el que esté instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o en un rol de control de acceso basado en roles (RBAC) al que haya asignado el cmdlet **New-CsStaticRoute** .</span><span class="sxs-lookup"><span data-stu-id="b74f2-108">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="b74f2-109">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b74f2-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b74f2-110">Para crear una ruta estática y colocarla en la variable $TLSRoute o $TCPRoute, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b74f2-110">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="b74f2-111">Para que coincidan los dominios secundarios de un dominio, puede especificar un valor comodín en el parámetro MatchUri.</span><span class="sxs-lookup"><span data-stu-id="b74f2-111">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter.</span></span> <span data-ttu-id="b74f2-112">Por ejemplo, <STRONG>\*. contoso.net</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b74f2-112">For example, <STRONG>\*.contoso.net</STRONG>.</span></span> <span data-ttu-id="b74f2-113">Ese valor coincide con cualquier dominio que termine con el sufijo <STRONG>contoso.net</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b74f2-113">That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="b74f2-114">Para una conexión de seguridad de nivel de transporte (TLS), escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="b74f2-114">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        
        <span data-ttu-id="b74f2-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b74f2-115">For example:</span></span>
        
            $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        
        <span data-ttu-id="b74f2-116">Si UseDefaultCertificate se establece en false, debe especificar parámetros TLSCertIssuer y TLSCertSerialNumber.</span><span class="sxs-lookup"><span data-stu-id="b74f2-116">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="b74f2-117">Estos parámetros indican el nombre de la entidad de certificación (CA) que emitió el certificado que se usó en la ruta estática y el número de serie de ese certificado TLS, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b74f2-117">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="b74f2-118">Para obtener más información sobre estos parámetros, consulte la ayuda del shell de administración de Lync Server escribiendo lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="b74f2-118">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        
            Get-Help New-CsStaticRoute -Full
    
      - <span data-ttu-id="b74f2-119">Para una conexión de protocolo de control de transmisión (TCP), escriba lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="b74f2-119">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="b74f2-120">Si especifica un nombre de dominio completo (FQDN), primero debe configurar un registro DNS (sistema de nombres de dominio).</span><span class="sxs-lookup"><span data-stu-id="b74f2-120">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        
        <span data-ttu-id="b74f2-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b74f2-121">For example:</span></span>
        
            $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        
        <span data-ttu-id="b74f2-122">A continuación se muestran los valores predeterminados de parámetros opcionales para rutas estáticas:</span><span class="sxs-lookup"><span data-stu-id="b74f2-122">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="b74f2-123">Enabled = true</span><span class="sxs-lookup"><span data-stu-id="b74f2-123">Enabled = True</span></span>
        
          - <span data-ttu-id="b74f2-124">MatchOnlyPhoneUri = false</span><span class="sxs-lookup"><span data-stu-id="b74f2-124">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="b74f2-125">ReplaceHostInRequestUri = false</span><span class="sxs-lookup"><span data-stu-id="b74f2-125">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="b74f2-126">Le recomendamos encarecidamente que no cambie estos valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="b74f2-126">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="b74f2-127">Sin embargo, si tiene que cambiar alguno de estos parámetros, consulte la ayuda del shell de administración de Lync Server escribiendo lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="b74f2-127">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        
            Get-Help New-CsStaticRoute -Full

4.  <span data-ttu-id="b74f2-128">Para conservar una ruta estática recién creada en el almacén de administración central, ejecute una de las siguientes opciones, según corresponda:</span><span class="sxs-lookup"><span data-stu-id="b74f2-128">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b74f2-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="b74f2-129">See Also</span></span>


[<span data-ttu-id="b74f2-130">Configurar una entrada de aplicación de confianza para control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b74f2-130">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="b74f2-131">Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b74f2-131">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

