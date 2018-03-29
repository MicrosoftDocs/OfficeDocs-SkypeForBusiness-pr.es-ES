---
title: Atributos, clases y extensiones de esquema de active Directory
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Esta sección de referencia incluye la siguiente información:'
ms.openlocfilehash: f185a11bdc5d3700839be2f1306e266d9ab6af26
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="43234-103">Atributos, clases y extensiones de esquema de active Directory</span><span class="sxs-lookup"><span data-stu-id="43234-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="43234-104">Esta sección de referencia incluye la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="43234-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="43234-105">Extensiones de esquema de Active Directory que son nuevas o modificadas de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="43234-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="43234-106">El esquema de Active Directory contiene las definiciones formales de cada clase de objeto que pueden crearse en un bosque de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="43234-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="43234-107">El esquema también contiene definiciones formales de cada atributo que puede existir en un objeto de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="43234-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="43234-108">El catálogo global de Active Directory contiene réplicas de todos los objetos del bosque, junto con un subconjunto de los atributos de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="43234-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="43234-109">Esta sección describe las clases y atributos que son nuevos o modificados en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="43234-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="43234-110">Todas las clases utilizadas por Skype para Business Server, con una descripción de cada uno</span><span class="sxs-lookup"><span data-stu-id="43234-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="43234-111">Todos los atributos utilizados por Skype para Business Server, con una descripción de cada uno</span><span class="sxs-lookup"><span data-stu-id="43234-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="43234-112">Puede contener una lista de las clases utilizadas por Skype para Business Server, con los atributos</span><span class="sxs-lookup"><span data-stu-id="43234-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="43234-113">Configuración global y los objetos, además de los grupos de administración y servicio universales que se crean durante la preparación del bosque</span><span class="sxs-lookup"><span data-stu-id="43234-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="43234-114">Entradas de control de acceso (ACE) que se crean en los contenedores de dominio raíz e integrados durante la preparación del dominio</span><span class="sxs-lookup"><span data-stu-id="43234-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="43234-115">Cambios que se realizan en una unidad organizativa (OU) de Active Directory mediante el cmdlet Grant_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="43234-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="43234-116">Cambios que se realizan en una OU de Active Directory mediante el cmdlet Grant_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="43234-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="43234-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="43234-117">In This Section</span></span>

- [<span data-ttu-id="43234-118">Cambios de esquema en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="43234-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="43234-119">Clases de esquema y descripciones en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="43234-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="43234-120">Descripciones de Skype para Business Server y atributos de esquema</span><span class="sxs-lookup"><span data-stu-id="43234-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="43234-121">Atributos del esquema de clase en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="43234-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="43234-122">Cambios realizados por la preparación del bosque en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="43234-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="43234-123">Cambios realizados por la preparación del dominio en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="43234-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="43234-124">Cambios realizados por Grant CsSetupPermission en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="43234-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="43234-125">Cambios realizados por Grant CsOUPermission en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="43234-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

