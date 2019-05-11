---
title: Extensiones de esquema, clases y atributos de Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Esta sección de referencia incluye la siguiente información:'
ms.openlocfilehash: dc2d147791317134ee9abd3de723f1c53f8f625b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907120"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="14809-103">Extensiones de esquema, clases y atributos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="14809-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="14809-104">Esta sección de referencia incluye la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="14809-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="14809-105">Extensiones de esquema de Active Directory que son nuevas o modificadas para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="14809-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="14809-106">El esquema de Active Directory contiene las definiciones formales de cada clase de objeto que se pueden crear en un bosque de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="14809-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="14809-107">El esquema contiene también las definiciones formales de todos los atributos que pueden existir en un objeto de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="14809-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="14809-108">El catálogo global de Active Directory contiene réplicas de todos los objetos del bosque, junto con un subconjunto de los atributos de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="14809-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="14809-109">En esta sección se describe las clases y los atributos que son nuevas o modificadas en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="14809-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="14809-110">Todas las clases que usa Skype para Business Server, con una descripción de cada uno</span><span class="sxs-lookup"><span data-stu-id="14809-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="14809-111">Todos los atributos utilizados por Skype para Business Server, con una descripción de cada uno</span><span class="sxs-lookup"><span data-stu-id="14809-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="14809-112">Puede contener una lista de las clases que usa Skype para Business Server, con los atributos</span><span class="sxs-lookup"><span data-stu-id="14809-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="14809-113">La configuración global y objetos, así como los grupos universales de servicio y administración que se crean durante la preparación del bosque</span><span class="sxs-lookup"><span data-stu-id="14809-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="14809-114">Entradas de control de acceso (ACE) que se crean en el dominio raíz y los contenedores integrados durante la preparación del dominio</span><span class="sxs-lookup"><span data-stu-id="14809-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="14809-115">Cambios que se realizan en una unidad organizativa (OU) de Active Directory por el cmdlet Grant_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="14809-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="14809-116">Cambios que se realizan en la OU de Active Directory por el cmdlet Grant_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="14809-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="14809-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="14809-117">In This Section</span></span>

- [<span data-ttu-id="14809-118">Cambios de esquema en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="14809-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="14809-119">Las clases de esquema y descripciones de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="14809-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="14809-120">Atributos de esquema y descripciones de Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="14809-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="14809-121">Atributos de esquema por clase en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="14809-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="14809-122">Cambios realizados por la preparación del bosque en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="14809-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="14809-123">Cambios realizados por la preparación del dominio en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="14809-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="14809-124">Cambios realizados por Grant-CsSetupPermission en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="14809-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="14809-125">Cambios realizados por Grant-CsOUPermission en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="14809-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

