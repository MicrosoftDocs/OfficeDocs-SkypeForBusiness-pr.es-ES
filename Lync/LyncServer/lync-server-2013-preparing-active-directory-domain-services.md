---
title: 'Lync Server 2013: Preparar Servicios de dominio de Active Directory en Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing Active Directory Domain Services for Lync Server 2013
ms:assetid: 7e126464-5d29-4013-9c44-0ccc2fbdea0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398630(v=OCS.15)
ms:contentKeyID: 48184620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99e1d7285d743da2270121389bbb5a510fe3b12d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="94638-102">Preparar Servicios de dominio de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94638-102">Preparing Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94638-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="94638-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="94638-104">Antes de implementar y ejecutar Lync Server 2013, debe preparar los servicios de dominio de Active Directory extendiendo el esquema y creando y configurando objetos.</span><span class="sxs-lookup"><span data-stu-id="94638-104">Before you deploy and operate Lync Server 2013, you must prepare Active Directory Domain Services by extending the schema and then creating and configuring objects.</span></span> <span data-ttu-id="94638-105">Las extensiones de esquema agregan las clases y atributos de Active Directory que necesita Lync Server.</span><span class="sxs-lookup"><span data-stu-id="94638-105">The schema extensions add the Active Directory classes and attributes that are required by Lync Server.</span></span>

<span data-ttu-id="94638-106">En los temas de esta sección se describe cómo preparar AD DS para implementar Lync Server y cómo asignar los permisos de configuración y unidad organizativa (OU).</span><span class="sxs-lookup"><span data-stu-id="94638-106">The topics in this section describe how to prepare AD DS for deploying Lync Server and how to assign setup and organizational unit (OU) permissions.</span></span> <span data-ttu-id="94638-107">Para más información sobre los cambios de esquema necesarios para Lync Server, vea [extensiones de esquema de Active Directory, clases y atributos usados por Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="94638-107">For details about the schema changes required for Lync Server, see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="94638-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="94638-108">In This Section</span></span>

  - [<span data-ttu-id="94638-109">Requisitos de infraestructura de Active Directory para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94638-109">Active Directory infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-active-directory-infrastructure-requirements.md)

  - [<span data-ttu-id="94638-110">Información general sobre la preparación de los Servicios de dominio de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94638-110">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>](lync-server-2013-overview-of-active-directory-domain-services-preparation.md)

  - [<span data-ttu-id="94638-111">Preparar Servicios de dominio de Active Directory en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94638-111">Preparing Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services_1.md)

  - [<span data-ttu-id="94638-112">Preparar Servicios de dominio de Active Directory bloqueados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94638-112">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)

  - [<span data-ttu-id="94638-113">Conceder permisos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94638-113">Granting permissions in Lync Server 2013</span></span>](lync-server-2013-granting-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

