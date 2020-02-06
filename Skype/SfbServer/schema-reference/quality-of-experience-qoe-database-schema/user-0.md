---
title: Tabla User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La tabla de usuario es una tabla de soporte que almacena una lista de los distintos usuarios que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.
ms.openlocfilehash: fcb6c4d45f1392c31ba87637d6e3a1a697f7be9e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805098"
---
# <a name="user-table"></a><span data-ttu-id="d4bd3-104">Tabla User</span><span class="sxs-lookup"><span data-stu-id="d4bd3-104">User table</span></span>
 
<span data-ttu-id="d4bd3-105">La tabla de usuario es una tabla de soporte que almacena una lista de los distintos usuarios que participaron en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d4bd3-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="d4bd3-106">Cada registro de la tabla representa un usuario.</span><span class="sxs-lookup"><span data-stu-id="d4bd3-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="d4bd3-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d4bd3-107">**Column**</span></span>|<span data-ttu-id="d4bd3-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d4bd3-108">**Data Type**</span></span>|<span data-ttu-id="d4bd3-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d4bd3-109">**Key/Index**</span></span>|<span data-ttu-id="d4bd3-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d4bd3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d4bd3-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="d4bd3-111">**UserKey**</span></span> <br/> |<span data-ttu-id="d4bd3-112">int</span><span class="sxs-lookup"><span data-stu-id="d4bd3-112">int</span></span>  <br/> |<span data-ttu-id="d4bd3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d4bd3-113">Primary</span></span>  <br/> |<span data-ttu-id="d4bd3-114">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="d4bd3-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="d4bd3-115">**URL**</span><span class="sxs-lookup"><span data-stu-id="d4bd3-115">**URI**</span></span> <br/> |<span data-ttu-id="d4bd3-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d4bd3-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d4bd3-117">Solo</span><span class="sxs-lookup"><span data-stu-id="d4bd3-117">Unique</span></span>  <br/> |<span data-ttu-id="d4bd3-118">Cadena URI.</span><span class="sxs-lookup"><span data-stu-id="d4bd3-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="d4bd3-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="d4bd3-119">**URIType**</span></span> <br/> |<span data-ttu-id="d4bd3-120">int</span><span class="sxs-lookup"><span data-stu-id="d4bd3-120">int</span></span>  <br/> ||<span data-ttu-id="d4bd3-121">1 es un tipo de URI desconocido.</span><span class="sxs-lookup"><span data-stu-id="d4bd3-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="d4bd3-122">2 es el URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="d4bd3-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="d4bd3-123">4 es el URI de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="d4bd3-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="d4bd3-124">8 es el URI del teléfono.</span><span class="sxs-lookup"><span data-stu-id="d4bd3-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="d4bd3-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="d4bd3-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="d4bd3-126">int</span><span class="sxs-lookup"><span data-stu-id="d4bd3-126">int</span></span>  <br/> |<span data-ttu-id="d4bd3-127">Extranjero</span><span class="sxs-lookup"><span data-stu-id="d4bd3-127">Foreign</span></span>  <br/> |<span data-ttu-id="d4bd3-128">Espacio empresarial del usuario al que se hace referencia desde la tabla de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d4bd3-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="d4bd3-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="d4bd3-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="d4bd3-130">datetime</span><span class="sxs-lookup"><span data-stu-id="d4bd3-130">datetime</span></span>  <br/> ||<span data-ttu-id="d4bd3-131">Última marca de tiempo cuando el usuario tenía una mala llamada de audio.</span><span class="sxs-lookup"><span data-stu-id="d4bd3-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="d4bd3-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d4bd3-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d4bd3-133">datetime</span><span class="sxs-lookup"><span data-stu-id="d4bd3-133">datetime</span></span>  <br/> ||<span data-ttu-id="d4bd3-134">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="d4bd3-134">For internal use only.</span></span>  <br/> |
   

