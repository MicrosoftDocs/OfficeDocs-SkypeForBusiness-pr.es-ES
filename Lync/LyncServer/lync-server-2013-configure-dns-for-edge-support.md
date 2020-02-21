---
title: 'Lync Server 2013: configurar DNS para compatibilidad con servidores perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7b3dcb9693ed6ab58d2828570e81ef05709867e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="84f1c-102">Configurar DNS para admitir servidores perimetrales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84f1c-102">Configure DNS for edge support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84f1c-103">_**Última modificación del tema:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="84f1c-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="84f1c-104">Debe configurar registros DNS (Sistema de nombres de dominio) para las interfaces perimetrales interna y externa, incluidas las interfaces de proxy inverso y servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="84f1c-104">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="84f1c-105">De modo predeterminado, los servidores perimetrales no se unen a un dominio y no dispondrán de un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="84f1c-105">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="84f1c-106">Se menciona al servidor perimetral solo por el nombre corto (equipo), no por el nombre de dominio completo.</span><span class="sxs-lookup"><span data-stu-id="84f1c-106">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="84f1c-107">Sin embargo, el generador de topologías usa FQDN, no nombres cortos.</span><span class="sxs-lookup"><span data-stu-id="84f1c-107">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="84f1c-108">El nombre del servidor perimetral debe coincidir con el FQDN que usa el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="84f1c-108">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="84f1c-109">Para ello, debe definir un sufijo DNS que, combinado con el nombre del equipo, resulte en el FQDN esperado.</span><span class="sxs-lookup"><span data-stu-id="84f1c-109">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="84f1c-110">Utilice el procedimiento siguiente en "Añadir el sufijo DNS al nombre del equipo en un servidor perimetral que no se ha unido a un dominio" para añadir el sufijo DNS al nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="84f1c-110">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="84f1c-111">De forma predeterminada, DNS usa un algoritmo Round Robin para girar el orden de los datos de registros de recursos devueltos en las respuestas a consultas donde existen varios registros de recursos del mismo tipo para un nombre de dominio DNS consultado.</span><span class="sxs-lookup"><span data-stu-id="84f1c-111">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="84f1c-112">El equilibrio de carga de DNS de Lync Server 2013, depende de la Round-Robin de DNS como parte del mecanismo de equilibrio de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="84f1c-112">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="84f1c-113">Compruebe que no se haya deshabilitado la configuración de operación por turnos.</span><span class="sxs-lookup"><span data-stu-id="84f1c-113">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="84f1c-114">Si usa un servidor DNS que no ejecuta un sistema operativo Windows, compruebe que la ordenación de registros de recursos de Round-Robin está habilitada.</span><span class="sxs-lookup"><span data-stu-id="84f1c-114">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="84f1c-115">Utilice el procedimiento siguiente en “**Creación de un registro DNS SRV**” para crear y comprobar todos los registros SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="84f1c-115">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="84f1c-116">Utilice el procedimiento en “**Creación de un registro A de DNS**” para definir los registros A de DNS necesarios para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="84f1c-116">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="84f1c-117">Para confirmar que los registros están configurados y funcionan correctamente, consulte “**Verificación de un registro DNS**” en este tema.</span><span class="sxs-lookup"><span data-stu-id="84f1c-117">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="84f1c-118">Para obtener más información sobre cada registro necesario para admitir el acceso de usuarios externos, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84f1c-118">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="84f1c-119">Para agregar el sufijo DNS al nombre del equipo en un servidor perimetral que no se ha incorporado a un dominio</span><span class="sxs-lookup"><span data-stu-id="84f1c-119">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="84f1c-120">En el equipo, haga clic en **Inicio**, haga clic con el botón secundario en **Equipo** y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="84f1c-120">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="84f1c-121">En **Configuración del nombre del equipo, dominio y grupo de trabajo**, haga clic en **Cambiar configuración**.</span><span class="sxs-lookup"><span data-stu-id="84f1c-121">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="84f1c-122">En la pestaña **Nombre del equipo**, haga clic en **Cambiar**.</span><span class="sxs-lookup"><span data-stu-id="84f1c-122">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="84f1c-123">En **Cambios del nombre del equipo/dominio**, haga clic en **Más**.</span><span class="sxs-lookup"><span data-stu-id="84f1c-123">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="84f1c-124">En **Sufijo DNS y nombre NetBIOS del equipo**, en **Sufijo DNS principal de este equipo**, escriba el nombre de su dominio interno (por ejemplo, corp.contoso.com), y haga clic en **Aceptar** tres veces.</span><span class="sxs-lookup"><span data-stu-id="84f1c-124">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="84f1c-125">Reinicie el equipo.</span><span class="sxs-lookup"><span data-stu-id="84f1c-125">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="84f1c-126">Para crear un registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="84f1c-126">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="84f1c-127">En el servidor DNS pertinente, haga clic en **Inicio**, en **Panel de control**, en **Herramientas administrativas** y, a continuación, en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="84f1c-127">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="84f1c-128">Debe configurar DNS para que haya: 1) entradas de DNS externas para las búsquedas DNS externas de usuarios remotos y socios federados; 2) entradas para búsquedas DNS que usan los servidores perimetrales dentro de la red perimetral (también denominada DMZ, zona desmilitarizada y subred filtrada), incluidos los registros A para los servidores internos que ejecutan Lync Server 2013; y 3) entradas DNS internas para búsquedas por parte de los clientes internos y los servidores que ejecutan Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="84f1c-128">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="84f1c-129">En el árbol de la consola del dominio SIP, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio donde Lync Server 2013 está instalado.</span><span class="sxs-lookup"><span data-stu-id="84f1c-129">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="84f1c-130">Haga clic en **Registros nuevos**.</span><span class="sxs-lookup"><span data-stu-id="84f1c-130">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="84f1c-131">En **Seleccione el tipo de registro del recurso**, escriba **Ubicación de servicio (SRV)** y, a continuación, haga clic en **Crear registro**.</span><span class="sxs-lookup"><span data-stu-id="84f1c-131">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="84f1c-132">Suministre toda la información necesaria para el registro SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="84f1c-132">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="84f1c-133">Para crear un registro A de DNS</span><span class="sxs-lookup"><span data-stu-id="84f1c-133">To create a DNS A record</span></span>

1.  <span data-ttu-id="84f1c-134">En el servidor DNS, haga clic en **Inicio**, en **Panel de control**, en **Herramientas administrativas** y, a continuación, en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="84f1c-134">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="84f1c-135">En el árbol de la consola del dominio SIP, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio en el que Lync Server 2013 está instalado.</span><span class="sxs-lookup"><span data-stu-id="84f1c-135">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="84f1c-136">Haga clic en **Host nuevo (A)**.</span><span class="sxs-lookup"><span data-stu-id="84f1c-136">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="84f1c-137">Suministre toda la información necesaria para el registro SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="84f1c-137">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="84f1c-138">Para comprobar un registro DNS</span><span class="sxs-lookup"><span data-stu-id="84f1c-138">To verify a DNS record</span></span>

1.  <span data-ttu-id="84f1c-139">Inicie sesión en un equipo cliente en el dominio.</span><span class="sxs-lookup"><span data-stu-id="84f1c-139">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="84f1c-140">Haga clic en **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="84f1c-140">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="84f1c-141">En el símbolo del sistema, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="84f1c-141">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="84f1c-142">Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.</span><span class="sxs-lookup"><span data-stu-id="84f1c-142">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="84f1c-143">Consulta también</span><span class="sxs-lookup"><span data-stu-id="84f1c-143">See Also</span></span>


[<span data-ttu-id="84f1c-144">Crear un registro SRV de DNS para la integración con la mensajería unificada de Exchange hospedada</span><span class="sxs-lookup"><span data-stu-id="84f1c-144">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="84f1c-145">Determinación de los requisitos de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84f1c-145">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

