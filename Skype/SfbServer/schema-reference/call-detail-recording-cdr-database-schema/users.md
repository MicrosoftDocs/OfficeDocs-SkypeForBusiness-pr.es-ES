---
title: Tabla Users
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabla de usuarios es una tabla de soporte. Cada registro de la tabla almacena información sobre un usuario implicado en llamadas o sesiones que tengan registros en la base de datos.
ms.openlocfilehash: b14350d060485a57b4af42cbfe26db729872f6f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="users-table"></a><span data-ttu-id="1ac2c-104">Tabla Users</span><span class="sxs-lookup"><span data-stu-id="1ac2c-104">Users table</span></span>
 
<span data-ttu-id="1ac2c-105">La tabla de usuarios es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="1ac2c-105">The Users table is a supporting table.</span></span> <span data-ttu-id="1ac2c-106">Cada registro de la tabla almacena información sobre un usuario implicado en llamadas o sesiones que tengan registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1ac2c-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="1ac2c-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1ac2c-107">**Column**</span></span>|<span data-ttu-id="1ac2c-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="1ac2c-108">**Data Type**</span></span>|<span data-ttu-id="1ac2c-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="1ac2c-109">**Key/Index**</span></span>|<span data-ttu-id="1ac2c-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="1ac2c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1ac2c-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="1ac2c-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="1ac2c-112">datetime</span><span class="sxs-lookup"><span data-stu-id="1ac2c-112">datetime</span></span>  <br/> ||<span data-ttu-id="1ac2c-113">Marca de tiempo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="1ac2c-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="1ac2c-114">**ID de usuario**</span><span class="sxs-lookup"><span data-stu-id="1ac2c-114">**UserId**</span></span> <br/> |<span data-ttu-id="1ac2c-115">int</span><span class="sxs-lookup"><span data-stu-id="1ac2c-115">int</span></span>  <br/> |<span data-ttu-id="1ac2c-116">Primary</span><span class="sxs-lookup"><span data-stu-id="1ac2c-116">Primary</span></span>  <br/> |<span data-ttu-id="1ac2c-117">Número único que identifica este usuario.</span><span class="sxs-lookup"><span data-stu-id="1ac2c-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="1ac2c-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="1ac2c-118">**UserUri**</span></span> <br/> |<span data-ttu-id="1ac2c-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="1ac2c-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="1ac2c-120">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="1ac2c-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="1ac2c-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="1ac2c-121">**TenantId**</span></span> <br/> |<span data-ttu-id="1ac2c-122">int</span><span class="sxs-lookup"><span data-stu-id="1ac2c-122">int</span></span>  <br/> |<span data-ttu-id="1ac2c-123">Externa</span><span class="sxs-lookup"><span data-stu-id="1ac2c-123">Foreign</span></span>  <br/> |<span data-ttu-id="1ac2c-124">Id. de inquilinos de este usuario</span><span class="sxs-lookup"><span data-stu-id="1ac2c-124">This user's Tenant ID.</span></span> <span data-ttu-id="1ac2c-125">Consulte la [tabla de los inquilinos](tenants.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1ac2c-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="1ac2c-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="1ac2c-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="1ac2c-127">int</span><span class="sxs-lookup"><span data-stu-id="1ac2c-127">int</span></span>  <br/> |<span data-ttu-id="1ac2c-128">Externa</span><span class="sxs-lookup"><span data-stu-id="1ac2c-128">Foreign</span></span>  <br/> |<span data-ttu-id="1ac2c-129">Este tipo de usuario URI.</span><span class="sxs-lookup"><span data-stu-id="1ac2c-129">This user's URI type.</span></span> <span data-ttu-id="1ac2c-130">Consulte la [tabla de UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1ac2c-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

