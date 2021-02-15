---
title: Extensiones de esquema, clases y atributos de Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 579bfa5a-9443-46dd-9a8e-07d00ba2824d
description: 'Esta sección de referencia incluye la información siguiente:'
ms.openlocfilehash: 5c8a1ceb6b623466219cbd3df46ff2b39ccceb2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831940"
---
# <a name="active-directory-schema-extensions-classes-and-attributes"></a><span data-ttu-id="659bb-103">Extensiones de esquema, clases y atributos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="659bb-103">Active Directory schema extensions, classes, and attributes</span></span>
 
<span data-ttu-id="659bb-104">Esta sección de referencia incluye la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="659bb-104">This reference section includes the following information:</span></span> 
  
- <span data-ttu-id="659bb-105">Extensiones de esquema de Active Directory nuevas o modificadas para Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="659bb-105">Active Directory schema extensions that are new or changed for Skype for Business Server</span></span>
    
    <span data-ttu-id="659bb-106">El esquema de Active Directory contiene las definiciones formales de todas las clases de objetos que se pueden crear en un bosque de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="659bb-106">The Active Directory schema contains formal definitions of every object class that can be created in an Active Directory forest.</span></span> <span data-ttu-id="659bb-107">El esquema contiene también las definiciones formales de todos los atributos que puede haber en un objeto de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="659bb-107">The schema also contains formal definitions of every attribute that can exist on an Active Directory object.</span></span> <span data-ttu-id="659bb-108">El catálogo global de Active Directory contiene replicaciones de todos los objetos del bosque, así como un subconjunto de los atributos de cada objeto.</span><span class="sxs-lookup"><span data-stu-id="659bb-108">The Active Directory global catalog contains replicas of all the objects for the forest, along with a subset of the attributes for each object.</span></span> <span data-ttu-id="659bb-109">En esta sección se describen las clases y atributos nuevos o modificados en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="659bb-109">This section describes the classes and attributes that are new or changed in Skype for Business Server.</span></span>
    
- <span data-ttu-id="659bb-110">Todas las clases usadas por Skype Empresarial Server, con una descripción de cada una</span><span class="sxs-lookup"><span data-stu-id="659bb-110">All the classes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="659bb-111">Todos los atributos usados por Skype Empresarial Server, con una descripción de cada uno</span><span class="sxs-lookup"><span data-stu-id="659bb-111">All the attributes used by Skype for Business Server, with a description of each</span></span>
    
- <span data-ttu-id="659bb-112">Una lista de las clases usadas por Skype Empresarial Server, con los atributos que cada una puede contener</span><span class="sxs-lookup"><span data-stu-id="659bb-112">A list of the classes used by Skype for Business Server, with the attributes each may contain</span></span>
    
- <span data-ttu-id="659bb-113">La configuración global y los objetos, así como los grupos universales de servicio y administración creados durante la preparación del bosque</span><span class="sxs-lookup"><span data-stu-id="659bb-113">Global settings and objects, in addition to the universal service and administration groups that are created during forest preparation</span></span>
    
- <span data-ttu-id="659bb-114">Las entradas de control de acceso (ACE) que se crean en la raíz del dominio y los contenedores integrados durante la preparación del dominio</span><span class="sxs-lookup"><span data-stu-id="659bb-114">Access control entries (ACEs) that are created on the domain root and built-in containers during domain preparation</span></span>
    
- <span data-ttu-id="659bb-115">Cambios que realiza en la unidad organizativa (OU) de Active Directory el cmdlet Grant_CsSetupPermission.</span><span class="sxs-lookup"><span data-stu-id="659bb-115">Changes that are made on an Active Directory organizational unit (OU) by the Grant_CsSetupPermission cmdlet.</span></span>
    
- <span data-ttu-id="659bb-116">Cambios que realiza en la OU de Active Directory el cmdlet Grant_CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="659bb-116">Changes that are made on an Active Directory OU by the Grant_CsOUPermission cmdlet.</span></span>
    
## <a name="in-this-section"></a><span data-ttu-id="659bb-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="659bb-117">In This Section</span></span>

- [<span data-ttu-id="659bb-118">Cambios de esquema en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="659bb-118">Schema changes in Skype for Business Server</span></span>](schema-changes.md)
    
- [<span data-ttu-id="659bb-119">Clases de esquema y descripciones en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="659bb-119">Schema classes and descriptions in Skype for Business Server</span></span>](schema-classes-and-descriptions.md)
    
- [<span data-ttu-id="659bb-120">Atributos de esquema y descripciones en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="659bb-120">Schema attributes and descriptions in Skype for Business Server</span></span>](schema-attributes-and-descriptions.md)
    
- [<span data-ttu-id="659bb-121">Atributos de esquema por clase en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="659bb-121">Schema attributes by class in Skype for Business Server</span></span>](schema-attributes-by-class.md)
    
- [<span data-ttu-id="659bb-122">Cambios realizados por la preparación del bosque en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="659bb-122">Changes made by forest preparation in Skype for Business Server</span></span>](changes-made-by-forest-preparation.md)
    
- [<span data-ttu-id="659bb-123">Cambios realizados por la preparación del dominio en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="659bb-123">Changes made by domain preparation in Skype for Business Server</span></span>](changes-made-by-domain-preparation.md)
    
- [<span data-ttu-id="659bb-124">Cambios realizados por Grant-CsSetupPermission en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="659bb-124">Changes made by Grant-CsSetupPermission in Skype for Business Server</span></span>](changes-made-by-grant-cssetuppermission.md)
    
- [<span data-ttu-id="659bb-125">Cambios realizados por Grant-CsOUPermission en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="659bb-125">Changes made by Grant-CsOUPermission in Skype for Business Server</span></span>](changes-made-by-grant-csoupermission.md)
    

