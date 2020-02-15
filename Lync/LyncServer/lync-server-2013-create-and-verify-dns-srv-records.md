---
title: 'Lync Server 2013: crear y comprobar registros DNS SRV'
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
ms.openlocfilehash: e6f56b2c406a14a6a1781705017d13d8b823472c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="0bfaa-102">Crear y comprobar registros DNS SRV en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0bfaa-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bfaa-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0bfaa-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0bfaa-104">Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o dominio, al menos, como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="0bfaa-105">En este tema se describe cómo configurar los registros del sistema de nombres de dominio (DNS) que se deben crear en las implementaciones de Lync Server 2013 y los que se requieren para el inicio de sesión automático de los clientes.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="0bfaa-106">Cuando se crea un grupo de servidores front-end, el programa de instalación crea los objetos y la configuración de Active Directory para el grupo, incluido el nombre de dominio completo (FQDN) del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="0bfaa-107">Se crean objetos y configuraciones similares para un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="0bfaa-108">Para que los clientes puedan conectar con el servidor Standard Edition o el grupo de servidores, el FQDN del grupo de servidores o del servidor Standard Edition debe estar registrado en DNS.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="0bfaa-109">Debe crear registros DNS SRV en su DNS interno para cada dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="0bfaa-110">En este procedimiento, se presupone que el DNS interno tiene zonas para los dominios de usuarios SIP.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="0bfaa-111">Para configurar un registro DNS SRV</span><span class="sxs-lookup"><span data-stu-id="0bfaa-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="0bfaa-112">En el servidor DNS, haga clic en **Inicio**, **Herramientas administrativas** y, a continuación, **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="0bfaa-113">En el árbol de la consola del dominio SIP, expanda **zonas de búsqueda directa**y, a continuación, haga clic con el botón secundario en el dominio SIP en el que se instalará Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="0bfaa-114">Haga clic en **Registros nuevos**.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="0bfaa-115">En **Seleccione el tipo de registro del recurso**, haga clic en **Ubicación de servicio (SRV)** y, a continuación, haga clic en **Crear registro**.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="0bfaa-116">Haga clic en **servicio**y, a continuación, escriba \*\* \_sipinternaltls\*\*.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="0bfaa-117">Haga clic en **Protocolo**y, a continuación, escriba \*\* \_TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="0bfaa-118">Haga clic en **Número de puerto** y escriba **5061**.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="0bfaa-119">Haga clic en **host que ofrece este servicio**y, a continuación, escriba el FQDN del grupo de servidores o del servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="0bfaa-120">Haga clic en **Aceptar** y, a continuación, haga clic en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="0bfaa-121">Para comprobar la creación de un registro DNS SRV</span><span class="sxs-lookup"><span data-stu-id="0bfaa-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="0bfaa-122">Inicie sesión en un equipo cliente del dominio con una cuenta que sea miembro del grupo Usuarios autenticados o que tenga permisos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="0bfaa-123">Haga clic en **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="0bfaa-124">En el cuadro **Abrir**, escriba **cmd** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="0bfaa-125">En el símbolo del sistema, escriba **nslookup** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="0bfaa-126">Escriba **set type=srv** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="0bfaa-127">Escriba \*\* \_sipinternaltls.\_ tcp.contoso.com\*\*y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="0bfaa-128">El resultado que se muestra para el registro de Seguridad de la capa de transporte (TLS) es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="0bfaa-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="0bfaa-129">Servidor: \<servidor\>DNS. contoso.com</span><span class="sxs-lookup"><span data-stu-id="0bfaa-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="0bfaa-130">Dirección: \<dirección IP del servidor DNS\></span><span class="sxs-lookup"><span data-stu-id="0bfaa-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="0bfaa-131">Respuesta no autoritativa:</span><span class="sxs-lookup"><span data-stu-id="0bfaa-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="0bfaa-132">\_sipinternaltls. \_Ubicación del servicio SRV de TCP.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="0bfaa-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="0bfaa-133">prioridad = 0</span><span class="sxs-lookup"><span data-stu-id="0bfaa-133">priority = 0</span></span>
    
    <span data-ttu-id="0bfaa-134">Weight = 0</span><span class="sxs-lookup"><span data-stu-id="0bfaa-134">weight = 0</span></span>
    
    <span data-ttu-id="0bfaa-135">Port = 5061</span><span class="sxs-lookup"><span data-stu-id="0bfaa-135">port = 5061</span></span>
    
    <span data-ttu-id="0bfaa-136">SVR hostname = poolname.contoso.com (o registro A de servidor Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="0bfaa-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="0bfaa-137">poolname.contoso.com internet address = \<dirección IP virtual del equilibrador de carga\> o \<dirección IP de un servidor Enterprise Edition único para grupos con un solo servidor\> Enterprise Edition o \<dirección IP del servidor Standard Edition\></span><span class="sxs-lookup"><span data-stu-id="0bfaa-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="0bfaa-138">Cuando termine, en el símbolo del sistema, escriba **exit** y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="0bfaa-139">Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="0bfaa-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="0bfaa-140">Inicie sesión en un equipo cliente en el dominio.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="0bfaa-141">Haga clic en **Iniciar** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="0bfaa-142">En el cuadro **Abrir**, escriba **cmd** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="0bfaa-143">En el símbolo del sistema, escriba **nslookup** \<FQDN del grupo\> de servidores Front \<-end o el FQDN del\>servidor Standard Edition y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="0bfaa-144">Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.</span><span class="sxs-lookup"><span data-stu-id="0bfaa-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

