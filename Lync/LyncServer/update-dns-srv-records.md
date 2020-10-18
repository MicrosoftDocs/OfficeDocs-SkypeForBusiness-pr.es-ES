---
title: Actualizar registros SRV de DNS
description: Actualizar los registros DNS SRV.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24161074e8f3bcf7e296a957588eeb59d5f2ad1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579596"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="6dcec-103">Actualizar registros SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="6dcec-103">Update DNS SRV records</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dcec-104">_**Última modificación del tema:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="6dcec-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="6dcec-105">Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="6dcec-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="6dcec-106">En este tema se describe cómo actualizar los registros del sistema de nombres de dominio (DNS) después de migrar a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dcec-106">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="6dcec-107">Una vez que se han movido todos los usuarios a Lync Server 2013, pero antes de que el director o grupo de servidores de Lync Server 2010 heredado se haya retirado, debe actualizar los registros DNS SRV en el DNS interno para cada dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="6dcec-107">After all users have been moved to Lync Server 2013, but before the legacy Lync Server 2010 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="6dcec-108">En este procedimiento, se presupone que el DNS interno tiene zonas para los dominios de usuarios SIP.</span><span class="sxs-lookup"><span data-stu-id="6dcec-108">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="6dcec-109">**Para configurar un registro DNS SRV**</span><span class="sxs-lookup"><span data-stu-id="6dcec-109">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="6dcec-110">En el servidor DNS, haga clic en **Inicio**, **Herramientas administrativas** y, a continuación, **DNS**.</span><span class="sxs-lookup"><span data-stu-id="6dcec-110">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="6dcec-111">En el árbol de la consola del dominio SIP, expanda **zonas de búsqueda directa**, expanda el dominio SIP en el que Lync Server 2013 está instalado y navegue hasta la configuración \*\* \_ TCP\*\* .</span><span class="sxs-lookup"><span data-stu-id="6dcec-111">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="6dcec-112">En el panel derecho, haga clic con el botón secundario en \*\* \_ sipinternaltls\*\* y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6dcec-112">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="6dcec-113">En **host que ofrece este servicio**, actualice el FQDN de host para que apunte al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6dcec-113">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="6dcec-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6dcec-114">Click **OK**.</span></span>

<span data-ttu-id="6dcec-115">**Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="6dcec-115">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="6dcec-116">Inicie sesión en un equipo cliente en el dominio.</span><span class="sxs-lookup"><span data-stu-id="6dcec-116">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="6dcec-117">Haga clic en **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6dcec-117">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="6dcec-118">En el cuadro **Abrir**, escriba **cmd** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6dcec-118">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="6dcec-119">En el símbolo del sistema, escriba **nslookup** \<FQDN of the Front End pool\> o \<FQDN of the Standard Edition server\> y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="6dcec-119">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="6dcec-120">Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.</span><span class="sxs-lookup"><span data-stu-id="6dcec-120">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

