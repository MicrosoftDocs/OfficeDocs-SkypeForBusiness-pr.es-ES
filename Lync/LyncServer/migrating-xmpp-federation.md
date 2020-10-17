---
title: Migrar la federación XMPP
description: Migrar la Federación XMPP.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e63c9f6fd3f1c1d45de77c27417987505678f74b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543216"
---
# <a name="migrating-xmpp-federation"></a><span data-ttu-id="0054f-103">Migrar la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="0054f-103">Migrating XMPP federation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0054f-104">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="0054f-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="0054f-105">Las versiones anteriores de Lync Server y Office Communications Server proporcionaban una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP) que se podía implementar como una función de servidor independiente para permitir la Federación con las implementaciones de XMPP.</span><span class="sxs-lookup"><span data-stu-id="0054f-105">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="0054f-106">En Lync Server 2013, la funcionalidad de XMPP puede implementarse como una característica.</span><span class="sxs-lookup"><span data-stu-id="0054f-106">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="0054f-107">La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral de Lync Server 2013 y la puerta de enlace XMPP que se ejecuta en el servidor front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0054f-107">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="0054f-108">Desde el punto de vista de la migración, una cuenta de usuario de Lync Server se puede mover a un grupo de servidores de Lync Server 2013 y seguir usando la puerta de enlace XMPP heredada.</span><span class="sxs-lookup"><span data-stu-id="0054f-108">From a migration perspective, a Lync Server user account can be moved to a Lync Server 2013 pool and continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="0054f-109">Esto solo es posible si el socio federado XMPP no está configurado en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0054f-109">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="0054f-110">En Resumen, si se ha implementado Lync Server 2010 con la puerta de enlace XMPP Office Communications Server 2007 R2 y la Federación XMPP se ha habilitado para los usuarios de Lync Server 2010 heredados, migrar la Federación XMPP a Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="0054f-110">In summary, if Lync Server 2010 has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Lync Server 2010 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="0054f-111">Implementar un grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0054f-111">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="0054f-112">Implementar un servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0054f-112">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="0054f-113">Mover todos los usuarios al grupo de servidores de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="0054f-113">Move all users to the Lync Server 2013 pool</span></span>

4.  <span data-ttu-id="0054f-114">Cree certificados y directivas de acceso de XMPP para el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="0054f-114">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="0054f-115">Habilite la Federación XMPP en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0054f-115">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="0054f-116">Actualice las entradas DNS para que apunten a la puerta de enlace XMPP de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0054f-116">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

