---
title: Extensiones de esquema, clases y atributos de Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Esta sección de referencia incluye la siguiente información:'
ms.openlocfilehash: 5934c9ffab8055de86cdaf3bcf507fa9c806f245
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296745"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="0660a-103">Extensiones de esquema, clases y atributos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="0660a-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="0660a-104">Esta sección de referencia incluye la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="0660a-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="0660a-105">Extensiones de esquema de Active Directory nuevas o modificadas en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0660a-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="0660a-106">El esquema de Active Directory contiene definiciones formales de todas las clases de objetos que se pueden crear en un bosque de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0660a-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="0660a-107">El esquema también contiene definiciones formales de todos los atributos que pueden existir en un objeto de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0660a-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="0660a-108">El catálogo global de Active Directory contiene réplicas de todos los objetos del bosque, junto con un subconjunto de los atributos para cada objeto.</span><span class="sxs-lookup"><span data-stu-id="0660a-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="0660a-109">En esta sección se describen las clases y los atributos que son nuevos o que han cambiado en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="0660a-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="0660a-110">Todas las clases usadas por Skype empresarial Server, con una descripción de cada una</span><span class="sxs-lookup"><span data-stu-id="0660a-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="0660a-111">Todos los atributos usados por Skype empresarial Server, con una descripción de cada uno</span><span class="sxs-lookup"><span data-stu-id="0660a-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="0660a-112">Una lista de las clases usadas por Skype empresarial Server, con los atributos que cada uno puede contener</span><span class="sxs-lookup"><span data-stu-id="0660a-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="0660a-113">Configuración global y objetos, además del servicio universal y los grupos de administración creados durante la preparación del bosque</span><span class="sxs-lookup"><span data-stu-id="0660a-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="0660a-114">Entradas de control de acceso (ACE) creadas en la raíz del dominio y en los contenedores integrados durante la preparación del dominio</span><span class="sxs-lookup"><span data-stu-id="0660a-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="0660a-115">Cambios que se realizan en una unidad organizativa (OU) de Active Directory mediante el cmdlet Grant_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="0660a-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="0660a-116">Cambios que se realizan en una unidad organizativa de Active Directory mediante el cmdlet Grant_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="0660a-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="0660a-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0660a-117">In This Section</span></span>

- [<span data-ttu-id="0660a-118">Cambios de esquema en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0660a-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="0660a-119">Clases y descripciones de esquema en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0660a-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="0660a-120">Atributos y descripciones de esquema en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0660a-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="0660a-121">Atributos de esquema por clase en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0660a-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="0660a-122">Cambios realizados por la preparación del bosque en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0660a-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="0660a-123">Cambios realizados por la preparación del dominio en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0660a-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="0660a-124">Cambios realizados por Grant-CsSetupPermission en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0660a-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="0660a-125">Cambios realizados por Grant-CsOUPermission en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="0660a-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

