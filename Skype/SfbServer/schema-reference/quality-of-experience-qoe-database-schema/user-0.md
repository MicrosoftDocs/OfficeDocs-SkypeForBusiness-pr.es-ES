---
title: Tabla User
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La tabla User es una tabla de apoyo donde se almacena una lista de los distintos usuarios que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.
ms.openlocfilehash: 5c84f0b947199fa497964cb1689dccc571a98d14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800080"
---
# <a name="user-table"></a><span data-ttu-id="4d4f0-104">Tabla User</span><span class="sxs-lookup"><span data-stu-id="4d4f0-104">User table</span></span>
 
<span data-ttu-id="4d4f0-p102">La tabla User es una tabla de apoyo donde se almacena una lista de los distintos usuarios que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-p102">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database. Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="4d4f0-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="4d4f0-107">**Column**</span></span>|<span data-ttu-id="4d4f0-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="4d4f0-108">**Data Type**</span></span>|<span data-ttu-id="4d4f0-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="4d4f0-109">**Key/Index**</span></span>|<span data-ttu-id="4d4f0-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="4d4f0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4d4f0-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="4d4f0-111">**UserKey**</span></span> <br/> |<span data-ttu-id="4d4f0-112">entero</span><span class="sxs-lookup"><span data-stu-id="4d4f0-112">int</span></span>  <br/> |<span data-ttu-id="4d4f0-113">Principal</span><span class="sxs-lookup"><span data-stu-id="4d4f0-113">Primary</span></span>  <br/> |<span data-ttu-id="4d4f0-114">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="4d4f0-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="4d4f0-115">**URI**</span></span> <br/> |<span data-ttu-id="4d4f0-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="4d4f0-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="4d4f0-117">Única</span><span class="sxs-lookup"><span data-stu-id="4d4f0-117">Unique</span></span>  <br/> |<span data-ttu-id="4d4f0-118">Cadena del URI.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="4d4f0-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="4d4f0-119">**URIType**</span></span> <br/> |<span data-ttu-id="4d4f0-120">entero</span><span class="sxs-lookup"><span data-stu-id="4d4f0-120">int</span></span>  <br/> ||<span data-ttu-id="4d4f0-121">1 es un tipo de URI desconocido.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="4d4f0-122">2 es un URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="4d4f0-123">4 es un URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="4d4f0-124">8 es un URI de teléfono.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="4d4f0-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="4d4f0-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="4d4f0-126">entero</span><span class="sxs-lookup"><span data-stu-id="4d4f0-126">int</span></span>  <br/> |<span data-ttu-id="4d4f0-127">Externo</span><span class="sxs-lookup"><span data-stu-id="4d4f0-127">Foreign</span></span>  <br/> |<span data-ttu-id="4d4f0-128">Inquilino del usuario, con referencia a la tabla Tenant.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="4d4f0-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="4d4f0-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="4d4f0-130">datetime</span><span class="sxs-lookup"><span data-stu-id="4d4f0-130">datetime</span></span>  <br/> ||<span data-ttu-id="4d4f0-131">Última marca de tiempo en la que el usuario tuvo una llamada de audio de mala calidad.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="4d4f0-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="4d4f0-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="4d4f0-133">datetime</span><span class="sxs-lookup"><span data-stu-id="4d4f0-133">datetime</span></span>  <br/> ||<span data-ttu-id="4d4f0-134">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4d4f0-134">For internal use only.</span></span>  <br/> |
   

