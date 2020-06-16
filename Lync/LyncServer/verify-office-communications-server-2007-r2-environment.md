---
title: Comprobar el entorno de Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14a7ba7e51e6dd1f6e42aeddfbbbd4ce7581d3fc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a><span data-ttu-id="2d830-102">Comprobar el entorno de Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2d830-102">Verify Office Communications Server 2007 R2 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d830-103">_**Última modificación del tema:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="2d830-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="2d830-104">Antes de implementar Lync Server 2013 en un estado de coexistencia con Office Communications Server 2007 R2, debe comprobar que los servicios de Office Communications Server 2007 R2 están configurados e iniciados.</span><span class="sxs-lookup"><span data-stu-id="2d830-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you need to verify the Office Communications Server 2007 R2 services are configured and started.</span></span>

<span data-ttu-id="2d830-105">**Comprobar que el grupo se ha iniciado mediante la herramienta administrativa de Office Communications Server 2007 R2**</span><span class="sxs-lookup"><span data-stu-id="2d830-105">**Verify the Pool is started using the Office Communications Server 2007 R2 Administrative Tool**</span></span>

1.  <span data-ttu-id="2d830-106">Abra la herramienta administrativa de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2d830-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="2d830-107">Expanda el nodo **Bosque**, después, el nodo **Servidores Standard Edition** o **Grupos de servidores Enterprise Edition** y, por último, expanda el nombre del servidor o grupo.</span><span class="sxs-lookup"><span data-stu-id="2d830-107">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="2d830-108">Compruebe que los servicios se ejecuten en el servidor Standard Edition o en el grupo de servidores Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2d830-108">Ensure that the services are running on the Standard Edition server or Enterprise pool.</span></span>
    
    <span data-ttu-id="2d830-109">![Consola de administración de Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Consola de administración de Office Communications Server 2007 R2")</span><span class="sxs-lookup"><span data-stu-id="2d830-109">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>

<span data-ttu-id="2d830-110">**Revise los usuarios configurados para Office Communications Server 2007 R2**</span><span class="sxs-lookup"><span data-stu-id="2d830-110">**Review Users configured for Office Communications Server 2007 R2**</span></span>

1.  <span data-ttu-id="2d830-111">Abra la herramienta administrativa de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2d830-111">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="2d830-112">Expanda sucesivamente el nodo **Bosque**, **Servidores Standard Edition** o **Grupos de servidores Enterprise Edition** y después expanda el grupo de servidores o el nombre de servidor.</span><span class="sxs-lookup"><span data-stu-id="2d830-112">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="2d830-113">Haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="2d830-113">Click **Users**.</span></span>

4.  <span data-ttu-id="2d830-114">Compruebe la lista de usuarios de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="2d830-114">Verify the list of Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="2d830-115">![Lista de usuarios en la herramienta de administración de OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Lista de usuarios en la herramienta de administración de OCS")</span><span class="sxs-lookup"><span data-stu-id="2d830-115">![List fo users in OCS Admin tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "List fo users in OCS Admin tool")</span></span>

<span data-ttu-id="2d830-116">**Compruebe la configuración del socio federado XMPP heredado**</span><span class="sxs-lookup"><span data-stu-id="2d830-116">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="2d830-117">Desde el servidor de XMPP heredado, vaya al \\ subprograma Servicios de herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="2d830-117">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="2d830-118">Compruebe que se haya iniciado el servicio de puerta de enlace XMPP de Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="2d830-118">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="2d830-119">![Servicio de puerta de enlace XMPP de Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Servicio de puerta de enlace XMPP de Office Communications Server")</span><span class="sxs-lookup"><span data-stu-id="2d830-119">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

