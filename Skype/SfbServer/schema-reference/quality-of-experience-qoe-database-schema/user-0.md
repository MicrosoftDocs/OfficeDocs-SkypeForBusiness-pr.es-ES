---
title: Tabla User
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La tabla de usuario es una tabla de soporte que almacena una lista de los distintos usuarios que han participado en las sesiones que se registran en la base de datos. Cada registro de la tabla representa un usuario.
ms.openlocfilehash: 3261133b8c36fe96fd847c075dce0be2a903c417
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="user-table"></a><span data-ttu-id="bc731-104">Tabla User</span><span class="sxs-lookup"><span data-stu-id="bc731-104">User table</span></span>
 
<span data-ttu-id="bc731-105">La tabla de usuario es una tabla de soporte que almacena una lista de los distintos usuarios que han participado en las sesiones que se registran en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bc731-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="bc731-106">Cada registro de la tabla representa un usuario.</span><span class="sxs-lookup"><span data-stu-id="bc731-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="bc731-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="bc731-107">**Column**</span></span>|<span data-ttu-id="bc731-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="bc731-108">**Data Type**</span></span>|<span data-ttu-id="bc731-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="bc731-109">**Key/Index**</span></span>|<span data-ttu-id="bc731-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="bc731-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bc731-111">**AutoCAD**</span><span class="sxs-lookup"><span data-stu-id="bc731-111">**UserKey**</span></span> <br/> |<span data-ttu-id="bc731-112">int</span><span class="sxs-lookup"><span data-stu-id="bc731-112">int</span></span>  <br/> |<span data-ttu-id="bc731-113">Primary</span><span class="sxs-lookup"><span data-stu-id="bc731-113">Primary</span></span>  <br/> |<span data-ttu-id="bc731-114">Número único que identifica este usuario.</span><span class="sxs-lookup"><span data-stu-id="bc731-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="bc731-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="bc731-115">**URI**</span></span> <br/> |<span data-ttu-id="bc731-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="bc731-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="bc731-117">Único</span><span class="sxs-lookup"><span data-stu-id="bc731-117">Unique</span></span>  <br/> |<span data-ttu-id="bc731-118">Cadena URI.</span><span class="sxs-lookup"><span data-stu-id="bc731-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="bc731-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="bc731-119">**URIType**</span></span> <br/> |<span data-ttu-id="bc731-120">int</span><span class="sxs-lookup"><span data-stu-id="bc731-120">int</span></span>  <br/> ||<span data-ttu-id="bc731-121">1 es de tipo desconocido de URI.</span><span class="sxs-lookup"><span data-stu-id="bc731-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="bc731-122">2 es el URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="bc731-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="bc731-123">4 es la conferencia URI.</span><span class="sxs-lookup"><span data-stu-id="bc731-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="bc731-124">8 es el URI del teléfono.</span><span class="sxs-lookup"><span data-stu-id="bc731-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="bc731-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="bc731-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="bc731-126">int</span><span class="sxs-lookup"><span data-stu-id="bc731-126">int</span></span>  <br/> |<span data-ttu-id="bc731-127">Externa</span><span class="sxs-lookup"><span data-stu-id="bc731-127">Foreign</span></span>  <br/> |<span data-ttu-id="bc731-128">Inquilinos del usuario, se hace referenciado en la tabla de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="bc731-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="bc731-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="bc731-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="bc731-130">datetime</span><span class="sxs-lookup"><span data-stu-id="bc731-130">datetime</span></span>  <br/> ||<span data-ttu-id="bc731-131">Marca de hora más reciente cuando el usuario tenía una llamada de audio deficiente.</span><span class="sxs-lookup"><span data-stu-id="bc731-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="bc731-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="bc731-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="bc731-133">datetime</span><span class="sxs-lookup"><span data-stu-id="bc731-133">datetime</span></span>  <br/> ||<span data-ttu-id="bc731-134">Sólo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="bc731-134">For internal use only.</span></span>  <br/> |
   

