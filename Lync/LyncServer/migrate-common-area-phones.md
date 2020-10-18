---
title: Migrar teléfonos de área común
description: Migrar teléfonos de área común.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b8df4d94a3db3274df7e4e82ed2185c3626de12
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579356"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="808d6-103">Migrar teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="808d6-103">Migrate Common Area Phones</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="808d6-104">_**Última modificación del tema:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="808d6-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="808d6-105">Los teléfonos de área común son teléfonos IP que a menudo se encuentran en un espacio de trabajo compartido o un área común, como una sala de espera, cocina o una fábrica.</span><span class="sxs-lookup"><span data-stu-id="808d6-105">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="808d6-106">No es necesario que los teléfonos de área común estén conectados a un equipo para proporcionar la funcionalidad de comunicaciones unificadas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="808d6-106">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="808d6-107">Después de migrar una implementación de Lync Server 2010 a Lync Server 2013, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado.</span><span class="sxs-lookup"><span data-stu-id="808d6-107">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="808d6-108">Mediante el shell de administración de Lync Server, primero se recuperarán todos los objetos de contacto asociados con los teléfonos de área común de Lync Server 2010 y, a continuación, se mueven dichos objetos al grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="808d6-108">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="808d6-109">**Migrar teléfonos de área común**</span><span class="sxs-lookup"><span data-stu-id="808d6-109">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="808d6-110">En el servidor front-end de Lync Server 2013, abra Shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="808d6-110">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="808d6-111">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="808d6-111">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="808d6-112">Para comprobar que todos los objetos de contacto se han movido al grupo de servidores de Lync Server 2013, desde el shell de administración de Lync Server, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="808d6-112">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="808d6-113">Compruebe que todos los objetos de contacto están ahora asociados con el grupo de servidores de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="808d6-113">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

