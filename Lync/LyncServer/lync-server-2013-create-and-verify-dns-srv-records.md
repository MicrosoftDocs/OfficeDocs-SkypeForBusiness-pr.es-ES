---
title: 'Lync Server 2013: crear y comprobar registros DNS SRV'
description: 'Lync Server 2013: crear y comprobar registros DNS SRV.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a71c876d0b26b9305feed7146fa6321a3983588d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562386"
---
# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="ee87d-103">Crear y comprobar registros DNS SRV en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee87d-103">Create and verify DNS SRV records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee87d-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ee87d-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ee87d-105">Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o dominio, al menos, como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="ee87d-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="ee87d-106">En este tema se describe cómo configurar los registros del sistema de nombres de dominio (DNS) que se deben crear en las implementaciones de Lync Server 2013 y los que se requieren para el inicio de sesión automático de los clientes.</span><span class="sxs-lookup"><span data-stu-id="ee87d-106">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="ee87d-107">Cuando se crea un grupo de servidores front-end, el programa de instalación crea los objetos y la configuración de Active Directory para el grupo, incluido el nombre de dominio completo (FQDN) del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="ee87d-107">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="ee87d-108">Se crean objetos y configuraciones similares para un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ee87d-108">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="ee87d-109">Para que los clientes puedan conectar con el servidor Standard Edition o el grupo de servidores, el FQDN del grupo de servidores o del servidor Standard Edition debe estar registrado en DNS.</span><span class="sxs-lookup"><span data-stu-id="ee87d-109">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="ee87d-110">Debe crear registros DNS SRV en su DNS interno para cada dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="ee87d-110">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="ee87d-111">En este procedimiento, se presupone que el DNS interno tiene zonas para los dominios de usuarios SIP.</span><span class="sxs-lookup"><span data-stu-id="ee87d-111">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="ee87d-112">Para configurar un registro DNS SRV</span><span class="sxs-lookup"><span data-stu-id="ee87d-112">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="ee87d-113">En el servidor DNS, haga clic en **Inicio**, **Herramientas administrativas** y, a continuación, **DNS**.</span><span class="sxs-lookup"><span data-stu-id="ee87d-113">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="ee87d-114">En el árbol de la consola del dominio SIP, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio SIP en el que se instalará Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ee87d-114">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="ee87d-115">Haga clic en **Registros nuevos**.</span><span class="sxs-lookup"><span data-stu-id="ee87d-115">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="ee87d-116">En **Seleccione el tipo de registro del recurso**, haga clic en **Ubicación de servicio (SRV)** y, a continuación, haga clic en **Crear registro**.</span><span class="sxs-lookup"><span data-stu-id="ee87d-116">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="ee87d-117">Haga clic en **servicio**y, a continuación, escriba \*\* \_ sipinternaltls\*\*.</span><span class="sxs-lookup"><span data-stu-id="ee87d-117">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="ee87d-118">Haga clic en **Protocolo**y, a continuación, escriba \*\* \_ TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="ee87d-118">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="ee87d-119">Haga clic en **Número de puerto** y escriba **5061**.</span><span class="sxs-lookup"><span data-stu-id="ee87d-119">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="ee87d-120">Haga clic en **host que ofrece este servicio**y, a continuación, escriba el FQDN del grupo de servidores o del servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ee87d-120">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="ee87d-121">Haga clic en **Aceptar** y, a continuación, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="ee87d-121">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="ee87d-122">Para comprobar la creación de un registro DNS SRV</span><span class="sxs-lookup"><span data-stu-id="ee87d-122">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="ee87d-123">Inicie sesión en un equipo cliente del dominio con una cuenta que sea miembro del grupo Usuarios autenticados o que tenga permisos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="ee87d-123">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="ee87d-124">Haga clic en **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ee87d-124">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="ee87d-125">En el cuadro **Abrir**, escriba **cmd** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ee87d-125">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="ee87d-126">En el símbolo del sistema, escriba **nslookup** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ee87d-126">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="ee87d-127">Escriba **set type=srv** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ee87d-127">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="ee87d-128">Escriba \*\* \_ sipinternaltls. \_ tcp.contoso.com\*\*y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="ee87d-128">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="ee87d-129">El resultado que se muestra para el registro de Seguridad de la capa de transporte (TLS) es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="ee87d-129">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="ee87d-130">Servidor: \<dns server\> . contoso.com</span><span class="sxs-lookup"><span data-stu-id="ee87d-130">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="ee87d-131">Visita \<IP address of DNS server\></span><span class="sxs-lookup"><span data-stu-id="ee87d-131">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="ee87d-132">Respuesta no autoritativa:</span><span class="sxs-lookup"><span data-stu-id="ee87d-132">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="ee87d-133">\_sipinternaltls. \_ Ubicación del servicio SRV de tcp.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="ee87d-133">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="ee87d-134">prioridad = 0</span><span class="sxs-lookup"><span data-stu-id="ee87d-134">priority = 0</span></span>
    
    <span data-ttu-id="ee87d-135">Weight = 0</span><span class="sxs-lookup"><span data-stu-id="ee87d-135">weight = 0</span></span>
    
    <span data-ttu-id="ee87d-136">Port = 5061</span><span class="sxs-lookup"><span data-stu-id="ee87d-136">port = 5061</span></span>
    
    <span data-ttu-id="ee87d-137">SVR hostname = poolname.contoso.com (o registro A de servidor Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="ee87d-137">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="ee87d-138">poolname.contoso.com Dirección de Internet = \<virtual IP Address of the load balancer\> o \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> o \<IP address of the Standard Edition server\></span><span class="sxs-lookup"><span data-stu-id="ee87d-138">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="ee87d-139">Cuando termine, en el símbolo del sistema, escriba **exit** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="ee87d-139">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="ee87d-140">Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ee87d-140">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="ee87d-141">Inicie sesión en un equipo cliente en el dominio.</span><span class="sxs-lookup"><span data-stu-id="ee87d-141">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="ee87d-142">Haga clic en **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ee87d-142">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="ee87d-143">En el cuadro **Abrir**, escriba **cmd** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ee87d-143">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="ee87d-144">En el símbolo del sistema, escriba **nslookup** \<FQDN of the Front End pool\> o \<FQDN of the Standard Edition server\> y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="ee87d-144">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="ee87d-145">Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.</span><span class="sxs-lookup"><span data-stu-id="ee87d-145">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

