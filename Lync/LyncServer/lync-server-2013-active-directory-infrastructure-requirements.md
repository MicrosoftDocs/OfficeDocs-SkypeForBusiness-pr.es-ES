---
title: 'Lync Server 2013: Requisitos de infraestructura de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c583fd751bf70814f9aa2fae5f6cfe08bec0202
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="ef392-102">Requisitos de infraestructura de Active Directory para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef392-102">Active Directory infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef392-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ef392-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ef392-104">Antes de empezar el proceso de preparación de los servicios de dominio de Active Directory para Lync Server 2013, asegúrese de que la infraestructura de Active Directory cumple los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="ef392-104">Before you start the process of preparing Active Directory Domain Services for Lync Server 2013, make sure that your Active Directory infrastructure meets the following prerequisites:</span></span>

  - <span data-ttu-id="ef392-105">Todos los controladores de dominio (que incluyen todos los servidores de catálogo global) del bosque donde se implementa Lync Server ejecutan uno de los siguientes sistemas operativos:</span><span class="sxs-lookup"><span data-stu-id="ef392-105">All domain controllers (which include all global catalog servers) in the forest where you deploy Lync Server run one of the following operating systems:</span></span>
    
      - <span data-ttu-id="ef392-106">Sistema operativo Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ef392-106">Windows Server 2012 R2 operating system</span></span>
    
      - <span data-ttu-id="ef392-107">Sistema operativo Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ef392-107">Windows Server 2012 operating system</span></span>
    
      - <span data-ttu-id="ef392-108">Sistema operativo Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ef392-108">Windows Server 2008 R2 operating system</span></span>
    
      - <span data-ttu-id="ef392-109">Sistema operativo Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="ef392-109">Windows Server 2008 operating system</span></span>
    
      - <span data-ttu-id="ef392-110">Windows Server 2008 Enterprise 32 bits</span><span class="sxs-lookup"><span data-stu-id="ef392-110">Windows Server 2008 Enterprise 32-Bit</span></span>
    
      - <span data-ttu-id="ef392-111">versiones de 32 o 64 bits del sistema operativo Windows Server 2003 R2</span><span class="sxs-lookup"><span data-stu-id="ef392-111">32-bit or 64-bit versions of the Windows Server 2003 R2 operating system</span></span>
    
      - <span data-ttu-id="ef392-112">versiones de 32 o 64 bits del sistema operativo Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="ef392-112">32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

  - <span data-ttu-id="ef392-113">Todos los dominios en los que implementa Lync Server se elevan al nivel funcional de dominio de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o, como mínimo, Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="ef392-113">All domains in which you deploy Lync Server are raised to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

  - <span data-ttu-id="ef392-114">El bosque en el que implementa Lync Server se eleva al nivel funcional de bosque de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o, como mínimo, Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="ef392-114">The forest in which you deploy Lync Server is raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ef392-115">Para cambiar el nivel funcional de bosque o de dominio, consulte "elevar niveles funcionales de dominios y bosques" en la <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>biblioteca de TechNet en.</span><span class="sxs-lookup"><span data-stu-id="ef392-115">To change your domain or forest functional level, see "Raising domain and forest functional levels" in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>.</span></span>

    
    </div>

  - <span data-ttu-id="ef392-116">Un catálogo global se implementa en cada dominio en el que se implementan equipos o usuarios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ef392-116">A global catalog is deployed in every domain where you deploy Lync Server computers or users.</span></span>

<span data-ttu-id="ef392-117">Lync Server 2013 admite los grupos universales de los sistemas operativos Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 y Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="ef392-117">Lync Server 2013 supports the universal groups in the Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 operating systems.</span></span> <span data-ttu-id="ef392-118">Los miembros de grupos universales pueden incluir otros grupos y cuentas de cualquier dominio en el árbol de dominio o bosque, y se les pueden asignar permisos en cualquier dominio en el árbol de dominio o bosque.</span><span class="sxs-lookup"><span data-stu-id="ef392-118">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="ef392-119">La compatibilidad con los grupos universales, junto con la delegación de administrador, simplifica la administración de una implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ef392-119">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="ef392-120">Por ejemplo, no es necesario agregar un dominio a otro para que un administrador pueda administrar ambos.</span><span class="sxs-lookup"><span data-stu-id="ef392-120">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

