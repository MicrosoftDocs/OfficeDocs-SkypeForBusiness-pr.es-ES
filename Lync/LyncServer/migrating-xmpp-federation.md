---
title: Migrar la federación XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49733794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b72dabd60ea42a84fcf9b15d1d739bc063ddf1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="b8c8a-102">Migrar la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="b8c8a-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8c8a-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b8c8a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b8c8a-104">Las versiones anteriores de Lync Server y Office Communications Server proporcionaban una puerta de enlace de protocolo de presencia y mensajería extensible (XMPP) que se podría implementar como una función de servidor independiente para permitir la Federación con implementaciones de XMPP.</span><span class="sxs-lookup"><span data-stu-id="b8c8a-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="b8c8a-105">En Lync Server 2013, la funcionalidad de XMPP puede implementarse como una característica.</span><span class="sxs-lookup"><span data-stu-id="b8c8a-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="b8c8a-106">La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral 2013 de Lync Server y la puerta de enlace XMPP que se ejecuta en el servidor front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b8c8a-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="b8c8a-107">Desde el punto de vista de la migración, una cuenta de usuario de Lync Server se puede mover a un grupo de 2013 de Lync Server y seguir usando la puerta de enlace XMPP heredada.</span><span class="sxs-lookup"><span data-stu-id="b8c8a-107">From a migration perspective, a Lync Server user account can be moved to a Lync Server 2013 pool and continue to use the legacy XMPP gateway.</span></span> <span data-ttu-id="b8c8a-108">Esto solo es posible si el socio de XMPP federado no está configurado en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b8c8a-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="b8c8a-109">En Resumen, si se ha implementado Lync Server 2010 con la puerta de enlace XMPP de Office Communications Server 2007 R2 y se ha habilitado la Federación XMPP para los usuarios heredados de Lync Server 2010, para migrar la Federación XMPP a Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="b8c8a-109">In summary, if Lync Server 2010 has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Lync Server 2010 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="b8c8a-110">Implementar un grupo de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8c8a-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="b8c8a-111">Implementar un servidor perimetral 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b8c8a-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="b8c8a-112">Mover todos los usuarios al grupo de servidores de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b8c8a-112">Move all users to the Lync Server 2013 pool</span></span>

4.  <span data-ttu-id="b8c8a-113">Cree certificados y directivas de acceso XMPP para el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="b8c8a-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="b8c8a-114">Habilite la Federación XMPP en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b8c8a-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="b8c8a-115">Actualice las entradas DNS para que apunten a la puerta de enlace de Lync Server 2013 XMPP.</span><span class="sxs-lookup"><span data-stu-id="b8c8a-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

