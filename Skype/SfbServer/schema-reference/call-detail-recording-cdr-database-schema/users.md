---
title: Tabla Users
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabla Usuarios es una tabla de apoyo. Cada registro de la tabla almacena información sobre un usuario que participa en llamadas o sesiones que tienen registros en la base de datos.
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831620"
---
# <a name="users-table"></a><span data-ttu-id="e33d1-104">Tabla Users</span><span class="sxs-lookup"><span data-stu-id="e33d1-104">Users table</span></span>
 
<span data-ttu-id="e33d1-105">La tabla Usuarios es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="e33d1-105">The Users table is a supporting table.</span></span> <span data-ttu-id="e33d1-106">Cada registro de la tabla almacena información sobre un usuario que participa en llamadas o sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e33d1-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="e33d1-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e33d1-107">**Column**</span></span>|<span data-ttu-id="e33d1-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e33d1-108">**Data Type**</span></span>|<span data-ttu-id="e33d1-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="e33d1-109">**Key/Index**</span></span>|<span data-ttu-id="e33d1-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="e33d1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e33d1-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="e33d1-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="e33d1-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e33d1-112">datetime</span></span>  <br/> ||<span data-ttu-id="e33d1-113">Marca de tiempo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="e33d1-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="e33d1-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="e33d1-114">**UserId**</span></span> <br/> |<span data-ttu-id="e33d1-115">entero</span><span class="sxs-lookup"><span data-stu-id="e33d1-115">int</span></span>  <br/> |<span data-ttu-id="e33d1-116">Principal</span><span class="sxs-lookup"><span data-stu-id="e33d1-116">Primary</span></span>  <br/> |<span data-ttu-id="e33d1-117">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="e33d1-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="e33d1-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="e33d1-118">**UserUri**</span></span> <br/> |<span data-ttu-id="e33d1-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="e33d1-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="e33d1-120">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="e33d1-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="e33d1-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="e33d1-121">**TenantId**</span></span> <br/> |<span data-ttu-id="e33d1-122">entero</span><span class="sxs-lookup"><span data-stu-id="e33d1-122">int</span></span>  <br/> |<span data-ttu-id="e33d1-123">Externo</span><span class="sxs-lookup"><span data-stu-id="e33d1-123">Foreign</span></span>  <br/> |<span data-ttu-id="e33d1-124">El id. de inquilino de este usuario.</span><span class="sxs-lookup"><span data-stu-id="e33d1-124">This user's Tenant ID.</span></span> <span data-ttu-id="e33d1-125">Vea la [tabla Inquilinos](tenants.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e33d1-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="e33d1-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="e33d1-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="e33d1-127">entero</span><span class="sxs-lookup"><span data-stu-id="e33d1-127">int</span></span>  <br/> |<span data-ttu-id="e33d1-128">Externo</span><span class="sxs-lookup"><span data-stu-id="e33d1-128">Foreign</span></span>  <br/> |<span data-ttu-id="e33d1-129">El tipo de URI de este usuario.</span><span class="sxs-lookup"><span data-stu-id="e33d1-129">This user's URI type.</span></span> <span data-ttu-id="e33d1-130">Vea la [tabla UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e33d1-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

