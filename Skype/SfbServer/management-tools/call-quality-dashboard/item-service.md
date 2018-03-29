---
title: Servicio de elementos de panel de calidad de la llamada (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumen: Conozca el servicio del elemento, que es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 218fdb4f2c4b3d73fb4e7f78b5679b66eecf34cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="910ae-104">Servicio de elementos de panel de calidad de la llamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="910ae-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="910ae-105">**Resumen:** Obtener información sobre el servicio del elemento, que es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="910ae-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="910ae-106">Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="910ae-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="910ae-107">El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="910ae-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="910ae-108">Servicio del elemento</span><span class="sxs-lookup"><span data-stu-id="910ae-108">Item Service</span></span>

<span data-ttu-id="910ae-109">API del depósito ofrece un servicio de administración de contenido simple, conocido como servicio de elemento, que se puede utilizar para almacenar cualquier contenido definido por la aplicación para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="910ae-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="910ae-110">El contenido del sistema es propiedad del usuario del sistema y compartido por todos los usuarios con acceso de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="910ae-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="910ae-111">Contenido de usuario dedicada son propiedad de usuarios normales y sólo los propietarios pueden modificar o eliminar, pero todos los usuarios aún tienen acceso de sólo lectura a ellos.</span><span class="sxs-lookup"><span data-stu-id="910ae-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="910ae-112">Esta documentación de API cubre operaciones de sólo lectura de la API del depósito.</span><span class="sxs-lookup"><span data-stu-id="910ae-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="910ae-113">Panel de calidad llamada guarda informes y consultas como elementos en la base de datos de repositorio.</span><span class="sxs-lookup"><span data-stu-id="910ae-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="910ae-114">Un elemento puede tener elementos secundarios opcionales, y llamar al panel de calidad organiza los informes y consultas en una estructura jerárquica con la característica de subelementos.</span><span class="sxs-lookup"><span data-stu-id="910ae-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="910ae-115">Servicio de elemento incluye los siguientes conceptos:</span><span class="sxs-lookup"><span data-stu-id="910ae-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="910ae-116">**Elemento** : elemento básico del repositorio.</span><span class="sxs-lookup"><span data-stu-id="910ae-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="910ae-117">Cada elemento pertenece a exactamente un usuario.</span><span class="sxs-lookup"><span data-stu-id="910ae-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="910ae-118">**Subtema** - los mecanismos básicos de organización del repositorio.</span><span class="sxs-lookup"><span data-stu-id="910ae-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="910ae-119">Elemento puede tener cero, uno o más elementos subordinan.</span><span class="sxs-lookup"><span data-stu-id="910ae-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="910ae-120">**Los antecesores de elemento** - la lista de elementos, comenzando por el elemento de nivel superior, que es el elemento del usuario, llevando a un determinado elemento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="910ae-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="910ae-121">**Elemento de contenido** - el contenido específico de la aplicación almacenado en artículos.</span><span class="sxs-lookup"><span data-stu-id="910ae-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="910ae-122">Panel de calidad llamada guarda representaciones JSON de informes y consultas en contenido.</span><span class="sxs-lookup"><span data-stu-id="910ae-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="910ae-123">Las operaciones de resto se incluyen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="910ae-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="910ae-124">**Operación**</span><span class="sxs-lookup"><span data-stu-id="910ae-124">**Operation**</span></span>|<span data-ttu-id="910ae-125">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="910ae-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="910ae-126">Obtener elementos</span><span class="sxs-lookup"><span data-stu-id="910ae-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="910ae-127">Obtener elementos devuelve todos los elementos en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="910ae-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="910ae-128">Obtener elemento</span><span class="sxs-lookup"><span data-stu-id="910ae-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="910ae-129">Obtener un elemento específico de devoluciones de artículos.</span><span class="sxs-lookup"><span data-stu-id="910ae-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="910ae-130">Obtener elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="910ae-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="910ae-131">Obtener elementos secundarios devuelve subelementos de un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="910ae-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="910ae-132">Obtener los antecesores del elemento</span><span class="sxs-lookup"><span data-stu-id="910ae-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="910ae-133">Antecesores del elemento Get devuelve a los antecesores de un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="910ae-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="910ae-134">Actualizar artículo</span><span class="sxs-lookup"><span data-stu-id="910ae-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="910ae-135">Actualizar un elemento específico en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="910ae-135">Update a specific item in the repository.</span></span>  <br/> |
   

