---
title: Actualizar registros DNS SRV
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef1440740e8fc25f5873dcb7bbdf5e8db953f6cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a><span data-ttu-id="052b7-102">Actualizar registros DNS SRV</span><span class="sxs-lookup"><span data-stu-id="052b7-102">Update DNS SRV records</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="052b7-103">_**Última modificación del tema:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="052b7-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="052b7-104">Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="052b7-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="052b7-105">En este tema se describe cómo actualizar los registros del sistema de nombres de dominio (DNS) después de migrar a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="052b7-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="052b7-106">Una vez que se han movido todos los usuarios a Lync Server 2013, pero antes de que el director o grupo de servidores de Lync Server 2010 heredado se haya retirado, debe actualizar los registros DNS SRV en el DNS interno para cada dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="052b7-106">After all users have been moved to Lync Server 2013, but before the legacy Lync Server 2010 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="052b7-107">En este procedimiento, se presupone que el DNS interno tiene zonas para los dominios de usuarios SIP.</span><span class="sxs-lookup"><span data-stu-id="052b7-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="052b7-108">**Para configurar un registro DNS SRV**</span><span class="sxs-lookup"><span data-stu-id="052b7-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="052b7-109">En el servidor DNS, haga clic en **Inicio**, **Herramientas administrativas** y, a continuación, **DNS**.</span><span class="sxs-lookup"><span data-stu-id="052b7-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="052b7-110">En el árbol de la consola del dominio SIP, expanda **zonas de búsqueda directa**, expanda el dominio SIP en el que Lync Server 2013 está instalado \*\* \_\*\* y navegue hasta la configuración TCP.</span><span class="sxs-lookup"><span data-stu-id="052b7-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="052b7-111">En el panel derecho, haga clic con el botón secundario en \*\* \_sipinternaltls\*\* y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="052b7-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="052b7-112">En **host que ofrece este servicio**, actualice el FQDN de host para que apunte al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="052b7-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="052b7-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="052b7-113">Click **OK**.</span></span>

<span data-ttu-id="052b7-114">**Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="052b7-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="052b7-115">Inicie sesión en un equipo cliente en el dominio.</span><span class="sxs-lookup"><span data-stu-id="052b7-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="052b7-116">Haga clic en **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="052b7-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="052b7-117">En el cuadro **Abrir**, escriba **cmd** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="052b7-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="052b7-118">En el símbolo del sistema, escriba **nslookup** \<FQDN del grupo\> de servidores Front \<-end o el FQDN del\>servidor Standard Edition y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="052b7-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="052b7-119">Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.</span><span class="sxs-lookup"><span data-stu-id="052b7-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

