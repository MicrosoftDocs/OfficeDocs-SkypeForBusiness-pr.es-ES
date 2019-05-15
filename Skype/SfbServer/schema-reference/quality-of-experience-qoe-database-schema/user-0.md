---
title: Tabla User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: En la tabla de usuario es una tabla de apoyo que almacena una lista de los distintos usuarios que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.
ms.openlocfilehash: 426d272a5c8bee2fd37511edc62bcb3e1a0c533e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907041"
---
# <a name="user-table"></a><span data-ttu-id="08127-104">Tabla User</span><span class="sxs-lookup"><span data-stu-id="08127-104">User table</span></span>
 
<span data-ttu-id="08127-105">En la tabla de usuario es una tabla de apoyo que almacena una lista de los distintos usuarios que han participado en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="08127-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="08127-106">Cada registro de la tabla representa un usuario.</span><span class="sxs-lookup"><span data-stu-id="08127-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="08127-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="08127-107">**Column**</span></span>|<span data-ttu-id="08127-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="08127-108">**Data Type**</span></span>|<span data-ttu-id="08127-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="08127-109">**Key/Index**</span></span>|<span data-ttu-id="08127-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="08127-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="08127-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="08127-111">**UserKey**</span></span> <br/> |<span data-ttu-id="08127-112">int</span><span class="sxs-lookup"><span data-stu-id="08127-112">int</span></span>  <br/> |<span data-ttu-id="08127-113">Primary</span><span class="sxs-lookup"><span data-stu-id="08127-113">Primary</span></span>  <br/> |<span data-ttu-id="08127-114">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="08127-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="08127-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="08127-115">**URI**</span></span> <br/> |<span data-ttu-id="08127-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="08127-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="08127-117">Único</span><span class="sxs-lookup"><span data-stu-id="08127-117">Unique</span></span>  <br/> |<span data-ttu-id="08127-118">Cadena URI.</span><span class="sxs-lookup"><span data-stu-id="08127-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="08127-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="08127-119">**URIType**</span></span> <br/> |<span data-ttu-id="08127-120">int</span><span class="sxs-lookup"><span data-stu-id="08127-120">int</span></span>  <br/> ||<span data-ttu-id="08127-121">1 es el tipo de URI desconocido.</span><span class="sxs-lookup"><span data-stu-id="08127-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="08127-122">2 es el URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="08127-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="08127-123">4 es el URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="08127-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="08127-124">8 es el URI del teléfono.</span><span class="sxs-lookup"><span data-stu-id="08127-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="08127-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="08127-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="08127-126">int</span><span class="sxs-lookup"><span data-stu-id="08127-126">int</span></span>  <br/> |<span data-ttu-id="08127-127">Externa</span><span class="sxs-lookup"><span data-stu-id="08127-127">Foreign</span></span>  <br/> |<span data-ttu-id="08127-128">Inquilino del usuario, de inquilino table.</span><span class="sxs-lookup"><span data-stu-id="08127-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="08127-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="08127-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="08127-130">datetime</span><span class="sxs-lookup"><span data-stu-id="08127-130">datetime</span></span>  <br/> ||<span data-ttu-id="08127-131">Marca de tiempo más reciente cuando el usuario tuvo una llamada de audio deficiente.</span><span class="sxs-lookup"><span data-stu-id="08127-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="08127-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="08127-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="08127-133">datetime</span><span class="sxs-lookup"><span data-stu-id="08127-133">datetime</span></span>  <br/> ||<span data-ttu-id="08127-134">Sólo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="08127-134">For internal use only.</span></span>  <br/> |
   

