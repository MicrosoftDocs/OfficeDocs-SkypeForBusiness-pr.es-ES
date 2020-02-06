---
title: Servicio de artículos para el panel de calidad de llamadas (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumen: Obtenga información sobre el servicio de elementos, que forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 5fdf2aedcb1a5e8d7d1929d7af70c5911cae46f0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816719"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="aa567-104">Servicio de artículos para el panel de calidad de llamadas (CQD)</span><span class="sxs-lookup"><span data-stu-id="aa567-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="aa567-105">**Resumen:** Obtenga más información sobre el servicio de elementos, que forma parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="aa567-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="aa567-106">El panel de calidad de llamadas es una herramienta para Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="aa567-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="aa567-107">El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="aa567-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="aa567-108">Servicio de elemento</span><span class="sxs-lookup"><span data-stu-id="aa567-108">Item Service</span></span>

<span data-ttu-id="aa567-109">La API de repositorio ofrece un servicio de administración de contenido simple, conocido como servicio de elementos, que se puede usar para almacenar cualquier contenido definido por la aplicación para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="aa567-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="aa567-110">El contenido del sistema pertenece al usuario del sistema y lo comparten todos los usuarios con acceso de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="aa567-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="aa567-111">El contenido del usuario dedicado pertenece a usuarios normales, y solo los propietarios pueden modificarlos o eliminarlos, pero todos los usuarios siguen teniendo acceso de solo lectura a ellos.</span><span class="sxs-lookup"><span data-stu-id="aa567-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa567-112">Esta documentación de API cubre las operaciones de solo lectura de la API del repositorio.</span><span class="sxs-lookup"><span data-stu-id="aa567-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="aa567-113">El panel de calidad de llamadas guarda informes y consultas como elementos en la base de datos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="aa567-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="aa567-114">Un elemento puede tener subelementos opcionales y el panel de calidad de llamadas organiza los informes y las consultas en una estructura jerárquica mediante la característica subelementos.</span><span class="sxs-lookup"><span data-stu-id="aa567-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="aa567-115">El servicio de artículos incluye los siguientes conceptos:</span><span class="sxs-lookup"><span data-stu-id="aa567-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="aa567-116">**Elemento** : el elemento básico del repositorio.</span><span class="sxs-lookup"><span data-stu-id="aa567-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="aa567-117">Cada elemento pertenece a un solo usuario.</span><span class="sxs-lookup"><span data-stu-id="aa567-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="aa567-118">**Elemento secundario** : el mecanismo básico de la organización del repositorio.</span><span class="sxs-lookup"><span data-stu-id="aa567-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="aa567-119">El elemento puede tener cero, uno o más elementos subordinados.</span><span class="sxs-lookup"><span data-stu-id="aa567-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="aa567-120">**Antecesores de elemento** : la lista de elementos, empezando por el elemento de nivel superior, que es el elemento predeterminado del usuario, que lleva a un elemento determinado.</span><span class="sxs-lookup"><span data-stu-id="aa567-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="aa567-121">**Contenido del elemento** : el contenido específico de la aplicación almacenado en los elementos.</span><span class="sxs-lookup"><span data-stu-id="aa567-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="aa567-122">El panel de calidad de llamadas guarda las representaciones JSON de informes y consultas en el contenido.</span><span class="sxs-lookup"><span data-stu-id="aa567-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="aa567-123">Las operaciones de REST se incluyen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="aa567-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="aa567-124">**Operación**</span><span class="sxs-lookup"><span data-stu-id="aa567-124">**Operation**</span></span>|<span data-ttu-id="aa567-125">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="aa567-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="aa567-126">Obtener elementos</span><span class="sxs-lookup"><span data-stu-id="aa567-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="aa567-127">Obtener elementos devuelve todos los elementos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="aa567-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="aa567-128">Obtener elemento</span><span class="sxs-lookup"><span data-stu-id="aa567-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="aa567-129">Obtener elemento devuelve un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="aa567-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="aa567-130">Obtener elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aa567-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="aa567-131">Obtener subelementos devuelve los subelementos de un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="aa567-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="aa567-132">Obtener predecesores del elemento</span><span class="sxs-lookup"><span data-stu-id="aa567-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="aa567-133">Obtener elementos antecesores del elemento devuelve los antecesores de un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="aa567-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="aa567-134">Actualizar elemento</span><span class="sxs-lookup"><span data-stu-id="aa567-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="aa567-135">Actualice un elemento específico del repositorio.</span><span class="sxs-lookup"><span data-stu-id="aa567-135">Update a specific item in the repository.</span></span>  <br/> |
   

