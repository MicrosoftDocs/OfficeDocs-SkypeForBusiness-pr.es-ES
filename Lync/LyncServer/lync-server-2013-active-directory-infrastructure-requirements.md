---
title: 'Lync Server 2013: requisitos de infraestructura de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de375bd11a0cf515745b0a64fb4aef7aa32113d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a><span data-ttu-id="69648-102">Requisitos de infraestructura de Active Directory para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69648-102">Active Directory infrastructure requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69648-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="69648-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="69648-104">Antes de iniciar el proceso de preparación de los servicios de dominio de Active Directory para Lync Server 2013, asegúrese de que la infraestructura de Active Directory cumple los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="69648-104">Before you start the process of preparing Active Directory Domain Services for Lync Server 2013, make sure that your Active Directory infrastructure meets the following prerequisites:</span></span>

  - <span data-ttu-id="69648-105">Todos los controladores de dominio (que incluyen todos los servidores de catálogo global) del bosque en el que se implementa Lync Server ejecutan uno de los siguientes sistemas operativos:</span><span class="sxs-lookup"><span data-stu-id="69648-105">All domain controllers (which include all global catalog servers) in the forest where you deploy Lync Server run one of the following operating systems:</span></span>
    
      - <span data-ttu-id="69648-106">Sistema operativo Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="69648-106">Windows Server 2012 R2 operating system</span></span>
    
      - <span data-ttu-id="69648-107">Sistema operativo Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="69648-107">Windows Server 2012 operating system</span></span>
    
      - <span data-ttu-id="69648-108">Sistema operativo Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="69648-108">Windows Server 2008 R2 operating system</span></span>
    
      - <span data-ttu-id="69648-109">Sistema operativo Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="69648-109">Windows Server 2008 operating system</span></span>
    
      - <span data-ttu-id="69648-110">Windows Server 2008 Enterprise 32 bits</span><span class="sxs-lookup"><span data-stu-id="69648-110">Windows Server 2008 Enterprise 32-Bit</span></span>
    
      - <span data-ttu-id="69648-111">Las versiones de 32 y 64 bits del sistema operativo Windows Server 2003 R2</span><span class="sxs-lookup"><span data-stu-id="69648-111">32-bit or 64-bit versions of the Windows Server 2003 R2 operating system</span></span>
    
      - <span data-ttu-id="69648-112">versiones de 32 bits o de 64 bits del sistema operativo Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="69648-112">32-bit or 64-bit versions of the Windows Server 2003 operating system</span></span>

  - <span data-ttu-id="69648-113">Todos los dominios en los que se implementa Lync Server se elevan a un nivel funcional de dominio de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o, como mínimo, Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="69648-113">All domains in which you deploy Lync Server are raised to a domain functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>

  - <span data-ttu-id="69648-114">El bosque en el que se implementa Lync Server se eleva a un nivel funcional del bosque de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 o, como mínimo, Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="69648-114">The forest in which you deploy Lync Server is raised to a forest functional level of Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, or at least Windows Server 2003.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69648-115">Para cambiar el nivel funcional del bosque o del dominio, vea "elevar los niveles funcionales de dominio y bosque" en <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A>la biblioteca de TechNet en.</span><span class="sxs-lookup"><span data-stu-id="69648-115">To change your domain or forest functional level, see "Raising domain and forest functional levels" in the TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A>.</span></span>

    
    </div>

  - <span data-ttu-id="69648-116">Se implementa un catálogo global en cada dominio en el que se implementan equipos o usuarios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69648-116">A global catalog is deployed in every domain where you deploy Lync Server computers or users.</span></span>

<span data-ttu-id="69648-117">Lync Server 2013 admite los grupos universales de los sistemas operativos Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 y Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="69648-117">Lync Server 2013 supports the universal groups in the Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 operating systems.</span></span> <span data-ttu-id="69648-118">Los miembros de grupos universales pueden incluir otros grupos y cuentas de cualquier dominio en el árbol de dominio o bosque y se les pueden asignar permisos en cualquier dominio en el árbol de dominio o bosque.</span><span class="sxs-lookup"><span data-stu-id="69648-118">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="69648-119">La compatibilidad con grupos universales, combinada con la delegación de administrador, simplifica la administración de una implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69648-119">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="69648-120">Por ejemplo, no es necesario agregar un dominio a otro para que un administrador pueda administrar ambos.</span><span class="sxs-lookup"><span data-stu-id="69648-120">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

