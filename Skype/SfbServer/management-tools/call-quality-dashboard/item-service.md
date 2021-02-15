---
title: Servicio de elementos para el Panel de calidad de llamadas (CQD)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumen: obtenga información sobre el servicio de elementos, que forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: b904f814a837af13e4015af5fbaca924739b8997
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827710"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="7badf-104">Servicio de elementos para el Panel de calidad de llamadas (CQD)</span><span class="sxs-lookup"><span data-stu-id="7badf-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="7badf-105">**Resumen:** Obtenga información sobre el servicio de elementos, que forma parte de la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7badf-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="7badf-106">El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7badf-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="7badf-107">El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7badf-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="7badf-108">Servicio de elemento</span><span class="sxs-lookup"><span data-stu-id="7badf-108">Item Service</span></span>

<span data-ttu-id="7badf-109">La API de repositorio ofrece un servicio de administración de contenido simple, conocido como servicio de elementos, que se puede usar para almacenar cualquier contenido definido por la aplicación para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7badf-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="7badf-110">El contenido del sistema es propiedad del usuario del sistema y lo comparten todos los usuarios con acceso de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="7badf-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="7badf-111">Los contenidos de usuario dedicados son propiedad de usuarios normales y solo los propietarios pueden modificarlos o eliminarlos, pero todos los usuarios siguen teniendo acceso de solo lectura a ellos.</span><span class="sxs-lookup"><span data-stu-id="7badf-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7badf-112">Esta documentación de la API cubre las operaciones de solo lectura de la API de repositorio.</span><span class="sxs-lookup"><span data-stu-id="7badf-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="7badf-113">El Panel de calidad de llamadas guarda informes y consultas como elementos en la base de datos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="7badf-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="7badf-114">Un elemento puede tener subproyecciones opcionales y el Panel de calidad de llamadas organiza informes y consultas en una estructura jerárquica mediante la característica de subproyecciones.</span><span class="sxs-lookup"><span data-stu-id="7badf-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="7badf-115">El servicio de elementos incluye los siguientes conceptos:</span><span class="sxs-lookup"><span data-stu-id="7badf-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="7badf-116">**Elemento:** el elemento básico del repositorio.</span><span class="sxs-lookup"><span data-stu-id="7badf-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="7badf-117">Cada elemento pertenece exactamente a un usuario.</span><span class="sxs-lookup"><span data-stu-id="7badf-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="7badf-118">**Sub item:** la mecánica organizativa básica del repositorio.</span><span class="sxs-lookup"><span data-stu-id="7badf-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="7badf-119">El elemento puede tener cero, uno o más elementos subordinados.</span><span class="sxs-lookup"><span data-stu-id="7badf-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="7badf-120">**Antecesores del** elemento: la lista de elementos, que comienza desde el elemento superior, que es el elemento predeterminado del usuario, lo que lleva a un elemento determinado.</span><span class="sxs-lookup"><span data-stu-id="7badf-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="7badf-121">**Contenido del elemento:** el contenido específico de la aplicación almacenado en Elementos.</span><span class="sxs-lookup"><span data-stu-id="7badf-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="7badf-122">El Panel de calidad de llamadas guarda las representaciones JSON de informes y consultas en contenido.</span><span class="sxs-lookup"><span data-stu-id="7badf-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="7badf-123">Las operaciones rest se incluyen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="7badf-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="7badf-124">**Operación**</span><span class="sxs-lookup"><span data-stu-id="7badf-124">**Operation**</span></span>|<span data-ttu-id="7badf-125">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7badf-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7badf-126">Obtener elementos</span><span class="sxs-lookup"><span data-stu-id="7badf-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="7badf-127">Obtener elementos devuelve todos los elementos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="7badf-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="7badf-128">Obtener elemento</span><span class="sxs-lookup"><span data-stu-id="7badf-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="7badf-129">Obtener elemento devuelve un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="7badf-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="7badf-130">Obtener elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7badf-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="7badf-131">Get Sub-Items devuelve los sub-elementos de un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="7badf-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="7badf-132">Obtener predecesores del elemento</span><span class="sxs-lookup"><span data-stu-id="7badf-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="7badf-133">Obtener antecesores de elemento devuelve los antecesores de un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="7badf-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="7badf-134">Actualizar elemento</span><span class="sxs-lookup"><span data-stu-id="7badf-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="7badf-135">Actualice un elemento específico del repositorio.</span><span class="sxs-lookup"><span data-stu-id="7badf-135">Update a specific item in the repository.</span></span>  <br/> |
   

