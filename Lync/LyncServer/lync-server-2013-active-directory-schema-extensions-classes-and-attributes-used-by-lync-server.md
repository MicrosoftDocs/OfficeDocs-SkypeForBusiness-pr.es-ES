---
title: 'Lync Server 2013: extensiones de esquema, clases y atributos de Active Directory usados por Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory schema extensions, classes, and attributes used by Lync Server 2013
ms:assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398379(v=OCS.15)
ms:contentKeyID: 48184188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e393c5c65e77f22763380563e61c30bcdb69b23a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-schema-extensions-classes-and-attributes-used-by-lync-server-2013"></a><span data-ttu-id="e8677-102">Extensiones de esquema, clases y atributos de Active Directory usados por Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8677-102">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8677-103">_**Última modificación del tema:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="e8677-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="e8677-104">Esta sección de referencia incluye la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8677-104">This reference section includes the following information:</span></span>

  - <span data-ttu-id="e8677-105">Extensiones de esquema de Active Directory que son nuevas o modificadas para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8677-105">Active Directory schema extensions that are new or changed for Lync Server 2013</span></span>
    
    <span data-ttu-id="e8677-106">El esquema de Active Directory contiene las definiciones formales de todas las clases de objetos que se pueden crear en un bosque de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e8677-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="e8677-107">El esquema contiene también las definiciones formales de todos los atributos que puede haber en un objeto de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e8677-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="e8677-108">El catálogo global de Active Directory contiene replicaciones de todos los objetos del bosque, así como un subconjunto de los atributos de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="e8677-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="e8677-109">En esta sección se describen las clases y los atributos que son nuevos o han cambiado en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8677-109">This section describes the classes and attributes that are new or changed in Lync Server 2013.</span></span>

  - <span data-ttu-id="e8677-110">Todas las clases usadas por Lync Server, con una descripción de cada</span><span class="sxs-lookup"><span data-stu-id="e8677-110">All the classes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="e8677-111">Todos los atributos usados por Lync Server, con una descripción de cada</span><span class="sxs-lookup"><span data-stu-id="e8677-111">All the attributes used by Lync Server, with a description of each</span></span>

  - <span data-ttu-id="e8677-112">Una lista de las clases usadas por Lync Server, con los atributos que cada uno puede contener</span><span class="sxs-lookup"><span data-stu-id="e8677-112">A list of the classes used by Lync Server, with the attributes each may contain</span></span>

  - <span data-ttu-id="e8677-113">La configuración global y los objetos, así como los grupos universales de servicio y administración creados durante la preparación del bosque</span><span class="sxs-lookup"><span data-stu-id="e8677-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>

  - <span data-ttu-id="e8677-114">Las entradas de control de acceso (ACE) que se crean en la raíz del dominio y los contenedores integrados durante la preparación del dominio</span><span class="sxs-lookup"><span data-stu-id="e8677-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>

  - <span data-ttu-id="e8677-115">Cambios que se realizan en una unidad organizativa (OU) de Active Directory mediante el\_cmdlet Grant CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="e8677-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant\_CsSetupPermission cmdlet.</span></span>

  - <span data-ttu-id="e8677-116">Cambios que se realizan en una unidad organizativa de Active Directory mediante\_el cmdlet Grant CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="e8677-116">Changes that are made on an Active Directory OU by the Grant\_CsOUPermission cmdlet.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e8677-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e8677-117">In This Section</span></span>

  - [<span data-ttu-id="e8677-118">Cambios de esquema en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8677-118">Schema changes in Lync Server 2013</span></span>](lync-server-2013-schema-changes-in-lync-server-2013.md)

  - [<span data-ttu-id="e8677-119">Clases de esquema y descripciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8677-119">Schema classes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-classes-and-descriptions.md)

  - [<span data-ttu-id="e8677-120">Atributos y descripciones de esquema en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8677-120">Schema attributes and descriptions in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-and-descriptions.md)

  - [<span data-ttu-id="e8677-121">Atributos de esquema por clase en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8677-121">Schema attributes by class in Lync Server 2013</span></span>](lync-server-2013-schema-attributes-by-class.md)

  - [<span data-ttu-id="e8677-122">Cambios realizados por la preparación del bosque en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8677-122">Changes made by forest preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-forest-preparation.md)

  - [<span data-ttu-id="e8677-123">Cambios realizados por la preparación del dominio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8677-123">Changes made by domain preparation in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-domain-preparation.md)

  - [<span data-ttu-id="e8677-124">Cambios realizados por Grant-CsSetupPermission en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8677-124">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission)

  - [<span data-ttu-id="e8677-125">Cambios realizados por Grant-CsOUPermission en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8677-125">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>](lync-server-2013-changes-made-by-https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)

</div>

</div>

<span> </span>

</div>

</div>

</div>

