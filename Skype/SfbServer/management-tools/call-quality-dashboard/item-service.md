---
title: Servicio de elemento para el panel de calidad de llamada (CQD)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 'Resumen: Información sobre el servicio de elemento, que es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: cbebdcfcac62eae375c13785b8d9866d055c2b50
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897502"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="40acb-104">Servicio de elemento para el panel de calidad de llamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="40acb-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="40acb-105">**Resumen:** Obtenga información sobre el servicio de elemento, que es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="40acb-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="40acb-106">Panel de calidad de llamada es una herramienta de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="40acb-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="40acb-107">El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad.</span><span class="sxs-lookup"><span data-stu-id="40acb-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="40acb-108">Servicio de elemento</span><span class="sxs-lookup"><span data-stu-id="40acb-108">Item Service</span></span>

<span data-ttu-id="40acb-109">API del depósito ofrece un servicio de administración de contenido simple, conocido como servicio de elemento, que se puede usar para almacenar cualquier contenido definido por la aplicación para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="40acb-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="40acb-110">El contenido del sistema es propiedad del usuario del sistema y compartido por todos los usuarios con acceso de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="40acb-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="40acb-111">Contenido de usuario dedicada pertenecen a los usuarios habituales y sólo los propietarios pueden modificar o eliminar, pero aún, todos los usuarios tienen acceso de solo lectura a ellos.</span><span class="sxs-lookup"><span data-stu-id="40acb-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="40acb-112">Esta documentación de API trata las operaciones de sólo lectura de API de repositorio.</span><span class="sxs-lookup"><span data-stu-id="40acb-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="40acb-113">Panel de calidad de llamada guarda informes y consultas como elementos en la base de datos de repositorio.</span><span class="sxs-lookup"><span data-stu-id="40acb-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="40acb-114">Un elemento puede tener elementos secundarios opcionales y panel de calidad de llamadas organiza los informes y consultas en una estructura jerárquica con la característica de elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="40acb-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="40acb-115">Servicio de elemento incluye los siguientes conceptos:</span><span class="sxs-lookup"><span data-stu-id="40acb-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="40acb-116">**Elemento** - el elemento básico del repositorio.</span><span class="sxs-lookup"><span data-stu-id="40acb-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="40acb-117">Cada elemento pertenece a exactamente un usuario.</span><span class="sxs-lookup"><span data-stu-id="40acb-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="40acb-118">**Elemento secundario** - los mecanismos básicos organizativos del repositorio.</span><span class="sxs-lookup"><span data-stu-id="40acb-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="40acb-119">Elemento puede tener cero, uno o más elementos subordinados.</span><span class="sxs-lookup"><span data-stu-id="40acb-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="40acb-120">**Elemento antecesores** - la lista de elementos, comenzando desde el elemento de nivel superior, que es el valor predeterminado de elemento del usuario, lo que lleva a un elemento determinado.</span><span class="sxs-lookup"><span data-stu-id="40acb-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="40acb-121">**Elemento de contenido** : el contenido específico de la aplicación almacenado en los elementos.</span><span class="sxs-lookup"><span data-stu-id="40acb-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="40acb-122">Panel de calidad de llamada guarda representaciones de JSON de informes y consultas en contenido.</span><span class="sxs-lookup"><span data-stu-id="40acb-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="40acb-123">Las operaciones de REST se incluyen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="40acb-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="40acb-124">**Operación**</span><span class="sxs-lookup"><span data-stu-id="40acb-124">**Operation**</span></span>|<span data-ttu-id="40acb-125">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="40acb-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="40acb-126">Obtener elementos</span><span class="sxs-lookup"><span data-stu-id="40acb-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="40acb-127">Obtener elementos devuelve todos los elementos en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="40acb-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="40acb-128">Obtener elemento</span><span class="sxs-lookup"><span data-stu-id="40acb-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="40acb-129">Obtener elemento devuelve un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="40acb-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="40acb-130">Obtener elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="40acb-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="40acb-131">Obtener elementos secundarios devuelve elementos secundarios de un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="40acb-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="40acb-132">Obtener predecesores del elemento</span><span class="sxs-lookup"><span data-stu-id="40acb-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="40acb-133">Get elemento antecesores devuelve a antecesores de un elemento específico.</span><span class="sxs-lookup"><span data-stu-id="40acb-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="40acb-134">Actualizar elemento</span><span class="sxs-lookup"><span data-stu-id="40acb-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="40acb-135">Actualizar un elemento específico en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="40acb-135">Update a specific item in the repository.</span></span>  <br/> |
   

