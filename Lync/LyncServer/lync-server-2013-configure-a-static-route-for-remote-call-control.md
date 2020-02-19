---
title: 'Lync Server 2013: configurar una ruta estática para el control remoto de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46fe499cdf622315ae0d0d789f0a3ed4283d78c1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="da5e6-102">Configurar una ruta estática para el control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da5e6-102">Configure a static route for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da5e6-103">_**Última modificación del tema:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="da5e6-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="da5e6-104">El control remoto de llamadas requiere que cada grupo de Lync Server esté configurado con una ruta de acceso desde ese grupo a la puerta de enlace SIP/CSTA que se conecta a la central de conmutación (PBX).</span><span class="sxs-lookup"><span data-stu-id="da5e6-104">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="da5e6-105">Esta ruta necesita que cada grupo de servidores tenga una ruta estática para cada puerta de enlace a la que el grupo de servidores delegará mensajes de control de llamadas SIP asociados con llamadas a la central de conmutación.</span><span class="sxs-lookup"><span data-stu-id="da5e6-105">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="da5e6-106">Si configura una ruta estática global para el control remoto de llamadas, cada grupo de servidores no configurado con una ruta estática en el nivel del grupo empleará la ruta estática global.</span><span class="sxs-lookup"><span data-stu-id="da5e6-106">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="da5e6-107">Para configurar una ruta estática para control remoto de llamadas</span><span class="sxs-lookup"><span data-stu-id="da5e6-107">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="da5e6-108">Inicie sesión en un equipo en el que esté instalado shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o en un rol de control de acceso basado en roles (RBAC) al que haya asignado el cmdlet **New-CsStaticRoute** .</span><span class="sxs-lookup"><span data-stu-id="da5e6-108">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="da5e6-109">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="da5e6-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="da5e6-110">Para crear una ruta estática y ponerla en la variable $TLSRoute o $TCPRoute, efectúe una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="da5e6-110">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="da5e6-p102">Para establecer una coincidencia con los dominios secundarios de un dominio, use un valor de comodín en el parámetro MatchUri. Por ejemplo, <STRONG>\*.contoso.net</STRONG>. Ese valor coincide con todos los dominios que tienen el sufijo <STRONG>contoso.net</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="da5e6-p102">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter. For example, <STRONG>\*.contoso.net</STRONG>. That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="da5e6-114">Para una conexión de Seguridad de la capa de transporte (TLS), escriba el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="da5e6-114">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        <span data-ttu-id="da5e6-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="da5e6-115">For example:</span></span>
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        <span data-ttu-id="da5e6-116">Si UseDefaultCertificate se define en False, debe especificar los parámetros TLSCertIssuer y TLSCertSerialNumber.</span><span class="sxs-lookup"><span data-stu-id="da5e6-116">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="da5e6-117">Dichos parámetros indican, respectivamente, el nombre de la entidad de certificación que ha emitido el certificado empleado en la ruta estática y el número de serie de este certificado TLS.</span><span class="sxs-lookup"><span data-stu-id="da5e6-117">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="da5e6-118">Para obtener más información acerca de estos parámetros, consulte Lync Server Management Shell Help escribiendo lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="da5e6-118">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - <span data-ttu-id="da5e6-119">Para una conexión de Protocolo de control de transmisión (TCP), escriba el siguiente comando en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="da5e6-119">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="da5e6-120">Si se especifica un nombre de dominio completo, primero debe configurar un registro A del Sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="da5e6-120">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        <span data-ttu-id="da5e6-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="da5e6-121">For example:</span></span>
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        <span data-ttu-id="da5e6-122">Después se muestran los valores predeterminados de los parámetros opcionales de rutas estáticas:</span><span class="sxs-lookup"><span data-stu-id="da5e6-122">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="da5e6-123">Enabled = True</span><span class="sxs-lookup"><span data-stu-id="da5e6-123">Enabled = True</span></span>
        
          - <span data-ttu-id="da5e6-124">MatchOnlyPhoneUri = False</span><span class="sxs-lookup"><span data-stu-id="da5e6-124">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="da5e6-125">ReplaceHostInRequestUri = False</span><span class="sxs-lookup"><span data-stu-id="da5e6-125">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="da5e6-126">Recomendamos encarecidamente no cambiar estos valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="da5e6-126">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="da5e6-127">Sin embargo, si debe cambiar cualquiera de estos parámetros, vea la ayuda del shell de administración de Lync Server escribiendo lo siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="da5e6-127">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  <span data-ttu-id="da5e6-128">Para conservar una ruta estática recién creada en el almacén de administración central, ejecute una de las opciones siguientes, según corresponda:</span><span class="sxs-lookup"><span data-stu-id="da5e6-128">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="da5e6-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="da5e6-129">See Also</span></span>


[<span data-ttu-id="da5e6-130">Configurar una entrada de aplicación de confianza para el control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da5e6-130">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="da5e6-131">Definir una dirección IP de puerta de enlace SIP/CSTA en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="da5e6-131">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

