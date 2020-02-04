---
title: Migrar la federación XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating XMPP federation
ms:assetid: 7368ee8f-a201-4d3a-b4e8-68396b156d4d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688093(v=OCS.15)
ms:contentKeyID: 49733692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 953b422527e095a6fef1e34cbf8b8fde2d494f42
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-xmpp-federation"></a><span data-ttu-id="cd7e3-102">Migrar la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="cd7e3-102">Migrating XMPP federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd7e3-103">_**Última modificación del tema:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="cd7e3-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="cd7e3-104">Las versiones anteriores de Office Communications Server proporcionaban una puerta de enlace de protocolo de presencia y mensajería extensible (XMPP) que se podía implementar como una función de servidor independiente para permitir la Federación con implementaciones de XMPP.</span><span class="sxs-lookup"><span data-stu-id="cd7e3-104">Previous versions of Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="cd7e3-105">En Lync Server 2013, la funcionalidad de XMPP puede implementarse como una característica.</span><span class="sxs-lookup"><span data-stu-id="cd7e3-105">In Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="cd7e3-106">La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral 2013 de Lync Server y la puerta de enlace XMPP que se ejecuta en el servidor front-end de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd7e3-106">XMPP functionality is installed in two parts: as an XMPP proxy that runs on the Lync Server 2013 Edge Server, and the XMPP Gateway that runs on the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="cd7e3-107">Desde el punto de vista de la migración, una cuenta de usuario de Office Communications Server 2007 R2 puede moverse a un grupo de servidores de Lync Server 2013 y seguir usando la puerta de enlace XMPP de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="cd7e3-107">From a migration perspective, a Office Communications Server 2007 R2 user account can be moved to a Lync Server 2013 pool and continue to use the Office Communications Server 2007 R2 XMPP gateway.</span></span> <span data-ttu-id="cd7e3-108">Esto solo es posible si el socio de XMPP federado no está configurado en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd7e3-108">This is possible only when the XMPP federated partner is not configured in Lync Server 2013.</span></span>

<span data-ttu-id="cd7e3-109">En Resumen, si Office Communications Server se ha implementado con la puerta de enlace XMPP de Office Communications Server 2007 R2 y se ha habilitado la Federación XMPP para los usuarios heredados de Office Communications Server 2007 R2, para migrar la Federación XMPP a Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="cd7e3-109">In summary, if Office Communications Server has been deployed with the Office Communications Server 2007 R2 XMPP Gateway and XMPP federation has been enabled for legacy Office Communications Server 2007 R2 users, to migrate the XMPP federation to Lync Server 2013:</span></span>

1.  <span data-ttu-id="cd7e3-110">Implementar un grupo de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cd7e3-110">Deploy a Lync Server 2013 pool.</span></span>

2.  <span data-ttu-id="cd7e3-111">Implementar un servidor perimetral 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cd7e3-111">Deploy a Lync Server 2013 Edge server.</span></span>

3.  <span data-ttu-id="cd7e3-112">Mueva todos los usuarios al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd7e3-112">Move all users to the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="cd7e3-113">Cree certificados y directivas de acceso XMPP para el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="cd7e3-113">Create XMPP access policies and certificates for the Edge Server.</span></span>

5.  <span data-ttu-id="cd7e3-114">Habilite la Federación XMPP en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd7e3-114">Enable XMPP federation in Lync Server 2013.</span></span> 

6.  <span data-ttu-id="cd7e3-115">Actualice las entradas DNS para que apunten a la puerta de enlace de Lync Server 2013 XMPP.</span><span class="sxs-lookup"><span data-stu-id="cd7e3-115">Update the DNS entries to point to the Lync Server 2013 XMPP Gateway.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

