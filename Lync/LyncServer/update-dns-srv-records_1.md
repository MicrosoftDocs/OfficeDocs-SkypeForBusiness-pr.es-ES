---
title: Actualizar registros SRV de DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97ff3eed81a90960444b260bd0ca5b9c4c67022e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a><span data-ttu-id="b01fe-102">Actualizar registros SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="b01fe-102">Update DNS SRV records</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b01fe-103">_**Última modificación del tema:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="b01fe-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="b01fe-104">Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="b01fe-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="b01fe-105">En este tema se describe cómo actualizar los registros del sistema de nombres de dominio (DNS) después de migrar a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b01fe-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="b01fe-106">Después de que todos los usuarios se hayan movido a Lync Server 2013, pero antes de que el director o grupo heredado de Office Communications Server 2007 R2 se haya decomisado, debe actualizar los registros SRV de DNS en el DNS interno para cada dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="b01fe-106">After all users have been moved to Lync Server 2013, but before the legacy Office Communications Server 2007 R2 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="b01fe-107">En este procedimiento se supone que su DNS interno tiene zonas para sus dominios de usuario SIP.</span><span class="sxs-lookup"><span data-stu-id="b01fe-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="b01fe-108">**Para configurar un registro SRV de DNS**</span><span class="sxs-lookup"><span data-stu-id="b01fe-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="b01fe-109">En el servidor DNS, haga clic en **Inicio**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="b01fe-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="b01fe-110">En el árbol de consola de su dominio SIP, expanda **zonas de búsqueda directa**, expanda el dominio SIP en el que está instalado Lync Server 2013 \*\* \_\*\* y vaya a la configuración de TCP.</span><span class="sxs-lookup"><span data-stu-id="b01fe-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="b01fe-111">En el panel derecho, haga clic con el botón derecho en \*\* \_sipinternaltls\*\* y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b01fe-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="b01fe-112">En el **hospedaje que ofrece este servicio**, actualice el FQDN del host para que apunte al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b01fe-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="b01fe-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b01fe-113">Click **OK**.</span></span>

<span data-ttu-id="b01fe-114">**Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="b01fe-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="b01fe-115">Inicie sesión en un equipo cliente del dominio.</span><span class="sxs-lookup"><span data-stu-id="b01fe-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="b01fe-116">Haga clic en  \*\*Inicio \*\* y en  \*\*Ejecutar \*\*.</span><span class="sxs-lookup"><span data-stu-id="b01fe-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="b01fe-117">En el cuadro **abrir** , escriba **cmd**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b01fe-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="b01fe-118">En el símbolo del sistema, escriba **nslookup** \<FQDN del grupo\> de servidores Front \<-end o FQDN del servidor\>Standard Edition y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="b01fe-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="b01fe-119">Compruebe que recibe una respuesta que se resuelve en la dirección IP adecuada para el nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="b01fe-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

