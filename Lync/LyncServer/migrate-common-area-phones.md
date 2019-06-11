---
title: Migrar teléfonos de área común
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94be64fea569a898e35c0519c0d1b081431c7f38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-common-area-phones"></a><span data-ttu-id="801cc-102">Migrar teléfonos de área común</span><span class="sxs-lookup"><span data-stu-id="801cc-102">Migrate Common Area Phones</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="801cc-103">_**Última modificación del tema:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="801cc-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="801cc-104">Los teléfonos de área común son teléfonos IP que suelen residir en un área de trabajo compartida o en un área común, como un vestíbulo, una cocina o una fábrica.</span><span class="sxs-lookup"><span data-stu-id="801cc-104">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="801cc-105">No es necesario que los teléfonos de área común estén conectados a un equipo para proporcionar la funcionalidad de UC de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="801cc-105">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="801cc-106">Después de migrar una implementación de Lync Server 2010 a Lync Server 2013, también debe migrar los objetos de contacto asociados con el teléfono de área común heredado.</span><span class="sxs-lookup"><span data-stu-id="801cc-106">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="801cc-107">Usar el shell de administración de Lync Server primero se recuperarán todos los objetos de contacto asociados a los teléfonos de área común de Lync Server 2010 y, a continuación, se moverán esos objetos al grupo de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="801cc-107">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="801cc-108">**Migrar teléfonos de área común**</span><span class="sxs-lookup"><span data-stu-id="801cc-108">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="801cc-109">En el servidor front-end de Lync Server 2013, abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="801cc-109">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="801cc-110">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="801cc-110">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="801cc-111">Para comprobar que todos los objetos de contacto se han movido al grupo de 2013 de Lync Server, escriba lo siguiente en el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="801cc-111">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="801cc-112">Compruebe que todos los objetos de contacto estén ahora asociados con el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="801cc-112">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

