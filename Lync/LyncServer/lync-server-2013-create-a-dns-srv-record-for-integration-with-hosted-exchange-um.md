---
title: Crear un registro SRV de DNS para la integración con la mensajería unificada de Exchange hospedada
description: Cree un registro SRV de DNS para la integración con la mensajería unificada de Exchange hospedada.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 694a595977abe33bebbb5fbcf2a508c9bb4e35a4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542146"
---
# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="79158-103">Crear un registro SRV de DNS para la integración con la mensajería unificada de Exchange hospedada</span><span class="sxs-lookup"><span data-stu-id="79158-103">Create a DNS SRV record for integration with hosted Exchange UM</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79158-104">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="79158-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="79158-105">En este tema se describe cómo configurar el registro SRV del sistema de nombres de dominio (DNS) necesario para que un servidor perimetral de Lync Server 2013 pueda enrutar a un servicio de Exchange hospedado como Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="79158-105">This topic describes how to configure the Domain Name System (DNS) SRV record that is required for a Lync Server 2013 Edge Server to route to a hosted Exchange service such as Microsoft Exchange Online.</span></span>

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a><span data-ttu-id="79158-106">Para crear un registro SRV de DNS externo para el servicio Exchange hospedado</span><span class="sxs-lookup"><span data-stu-id="79158-106">To create an external DNS SRV record for the hosted Exchange service</span></span>

1.  <span data-ttu-id="79158-107">Inicie sesión en el servidor DNS externo como miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="79158-107">Log on to the external DNS server as a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="79158-108">Haga clic en **Iniciar**, en **Herramientas administrativas** y en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="79158-108">Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="79158-109">En el árbol de la consola del dominio SIP, expanda **zonas de búsqueda directa**y seleccione el dominio SIP en el que se instalará Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79158-109">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and select the SIP domain in which Lync Server 2013 will be installed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="79158-p101">Debe crear el registro SRV de DNS en el dominio SIP en que se va a instalar Lync Server. Al crear el registro SRV, el FQDN usado para el host que ofrece este campo de servicio debe ser el FQDN externo del grupo de servidores perimetrales. Por ejemplo, si el FQDN externo de su grupo de servidores perimetrales es edge01.contoso.net, escriba ese valor. Este debe estar también en el mismo dominio que el registro de host (A) de DNS.</span><span class="sxs-lookup"><span data-stu-id="79158-p101">You must create the DNS SRV record in the SIP domain in which Lync Server is or will be installed. When you create the SRV record, the FQDN used for the Host offering this service field must be the external FQDN of the Edge pool. For example, if the external FQDN of your Edge pool is edge01.contoso.net, enter that value. This must also be in the same domain as the DNS Hosts (A) record.</span></span>

    
    </div>

4.  <span data-ttu-id="79158-114">Haga clic con el botón secundario en el dominio seleccionado y haga clic en **Registros nuevos**.</span><span class="sxs-lookup"><span data-stu-id="79158-114">Right-click the selected domain, and then click **Other New Records**.</span></span>

5.  <span data-ttu-id="79158-115">En **Tipo de registro del recurso**, haga clic en **Ubicación de servicio (SRV)** y en **Crear registro**.</span><span class="sxs-lookup"><span data-stu-id="79158-115">In **Resource Record Type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

6.  <span data-ttu-id="79158-116">En **nuevo registro de recursos**, haga clic en **servicio**y, a continuación, escriba \*\* \_ sipfederationtls\*\*.</span><span class="sxs-lookup"><span data-stu-id="79158-116">In **New Resource Record**, click **Service**, and then type **\_sipfederationtls**.</span></span>

7.  <span data-ttu-id="79158-117">Haga clic en **Protocolo**y, a continuación, escriba \*\* \_ TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="79158-117">Click **Protocol**, and then type **\_tcp**.</span></span>

8.  <span data-ttu-id="79158-118">Haga clic en **Número de puerto** y escriba **5061**.</span><span class="sxs-lookup"><span data-stu-id="79158-118">Click **Port Number**, and then type **5061**.</span></span>

9.  <span data-ttu-id="79158-119">Haga clic en **host que ofrece este servicio**y, a continuación, escriba el nombre de dominio completo (FQDN) del grupo de servidores perimetrales de lync Server 2013 que proporciona acceso al sistema de lync Server 2013 para clientes externos de confianza.</span><span class="sxs-lookup"><span data-stu-id="79158-119">Click **Host offering this service**, and then type the fully qualified domain name (FQDN) of the Lync Server 2013 Edge pool that provides access to your Lync Server 2013 system for trusted external clients.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="79158-120">El dominio también debe estar configurado como un dominio aceptado y autoritativo en la configuración de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="79158-120">The domain must also be set up as an authoritative, accepted domain in your Exchange Online settings.</span></span> <span data-ttu-id="79158-121">Para obtener más información, consulte crear dominios aceptados en <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A> .</span><span class="sxs-lookup"><span data-stu-id="79158-121">For details, see Create Accepted Domains at <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span></span>

    
    </div>

10. <span data-ttu-id="79158-122">Haga clic en **Aceptar** y en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="79158-122">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a><span data-ttu-id="79158-123">Para comprobar que el registro SRV de DNS se ha creado correctamente</span><span class="sxs-lookup"><span data-stu-id="79158-123">To verify that the DNS SRV record was created successfully</span></span>

1.  <span data-ttu-id="79158-124">Inicie sesión en un equipo cliente en el dominio.</span><span class="sxs-lookup"><span data-stu-id="79158-124">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="79158-125">Haga clic en **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="79158-125">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="79158-126">En el símbolo del sistema, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="79158-126">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN Lync Edge Pool>

4.  <span data-ttu-id="79158-127">Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.</span><span class="sxs-lookup"><span data-stu-id="79158-127">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="79158-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79158-128">See Also</span></span>


[<span data-ttu-id="79158-129">Crear registros DNS para servidores de proxy inverso en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79158-129">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

