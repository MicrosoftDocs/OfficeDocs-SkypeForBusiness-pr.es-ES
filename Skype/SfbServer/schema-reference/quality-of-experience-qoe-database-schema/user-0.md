---
title: Tabla User
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: En la tabla de usuario es una tabla de apoyo que almacena una lista de los distintos usuarios que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.
ms.openlocfilehash: fcdc8682b86432613af79d5e4d2abbdb248fef0f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881677"
---
# <a name="user-table"></a><span data-ttu-id="7def2-104">Tabla User</span><span class="sxs-lookup"><span data-stu-id="7def2-104">User table</span></span>
 
<span data-ttu-id="7def2-105">En la tabla de usuario es una tabla de apoyo que almacena una lista de los distintos usuarios que han participado en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7def2-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="7def2-106">Cada registro de la tabla representa un usuario.</span><span class="sxs-lookup"><span data-stu-id="7def2-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="7def2-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7def2-107">**Column**</span></span>|<span data-ttu-id="7def2-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="7def2-108">**Data Type**</span></span>|<span data-ttu-id="7def2-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="7def2-109">**Key/Index**</span></span>|<span data-ttu-id="7def2-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="7def2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7def2-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="7def2-111">**UserKey**</span></span> <br/> |<span data-ttu-id="7def2-112">int</span><span class="sxs-lookup"><span data-stu-id="7def2-112">int</span></span>  <br/> |<span data-ttu-id="7def2-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7def2-113">Primary</span></span>  <br/> |<span data-ttu-id="7def2-114">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="7def2-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="7def2-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="7def2-115">**URI**</span></span> <br/> |<span data-ttu-id="7def2-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="7def2-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="7def2-117">Único</span><span class="sxs-lookup"><span data-stu-id="7def2-117">Unique</span></span>  <br/> |<span data-ttu-id="7def2-118">Cadena URI.</span><span class="sxs-lookup"><span data-stu-id="7def2-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="7def2-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="7def2-119">**URIType**</span></span> <br/> |<span data-ttu-id="7def2-120">int</span><span class="sxs-lookup"><span data-stu-id="7def2-120">int</span></span>  <br/> ||<span data-ttu-id="7def2-121">1 es el tipo de URI desconocido.</span><span class="sxs-lookup"><span data-stu-id="7def2-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="7def2-122">2 es el URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="7def2-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="7def2-123">4 es el URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="7def2-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="7def2-124">8 es el URI del teléfono.</span><span class="sxs-lookup"><span data-stu-id="7def2-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="7def2-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="7def2-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="7def2-126">int</span><span class="sxs-lookup"><span data-stu-id="7def2-126">int</span></span>  <br/> |<span data-ttu-id="7def2-127">Externa</span><span class="sxs-lookup"><span data-stu-id="7def2-127">Foreign</span></span>  <br/> |<span data-ttu-id="7def2-128">Inquilino del usuario, de inquilino table.</span><span class="sxs-lookup"><span data-stu-id="7def2-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="7def2-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="7def2-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="7def2-130">datetime</span><span class="sxs-lookup"><span data-stu-id="7def2-130">datetime</span></span>  <br/> ||<span data-ttu-id="7def2-131">Marca de tiempo más reciente cuando el usuario tuvo una llamada de audio deficiente.</span><span class="sxs-lookup"><span data-stu-id="7def2-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="7def2-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="7def2-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="7def2-133">datetime</span><span class="sxs-lookup"><span data-stu-id="7def2-133">datetime</span></span>  <br/> ||<span data-ttu-id="7def2-134">Sólo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="7def2-134">For internal use only.</span></span>  <br/> |
   

