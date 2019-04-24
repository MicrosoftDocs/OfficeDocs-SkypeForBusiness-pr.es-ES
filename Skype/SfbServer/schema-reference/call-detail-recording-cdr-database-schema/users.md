---
title: Tabla Users
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: En la tabla de usuarios es una tabla de apoyo. Cada registro en la tabla almacena información sobre un usuario que participó en las llamadas o las sesiones que tienen registros en la base de datos.
ms.openlocfilehash: 3929ba33737c107ee60ec1e31beebb1addbb2e3f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212743"
---
# <a name="users-table"></a><span data-ttu-id="54e7c-104">Tabla Users</span><span class="sxs-lookup"><span data-stu-id="54e7c-104">Users table</span></span>
 
<span data-ttu-id="54e7c-105">En la tabla de usuarios es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="54e7c-105">The Users table is a supporting table.</span></span> <span data-ttu-id="54e7c-106">Cada registro en la tabla almacena información sobre un usuario que participó en las llamadas o las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="54e7c-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="54e7c-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="54e7c-107">**Column**</span></span>|<span data-ttu-id="54e7c-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="54e7c-108">**Data Type**</span></span>|<span data-ttu-id="54e7c-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="54e7c-109">**Key/Index**</span></span>|<span data-ttu-id="54e7c-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="54e7c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="54e7c-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="54e7c-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="54e7c-112">datetime</span><span class="sxs-lookup"><span data-stu-id="54e7c-112">datetime</span></span>  <br/> ||<span data-ttu-id="54e7c-113">Marca de tiempo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="54e7c-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="54e7c-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="54e7c-114">**UserId**</span></span> <br/> |<span data-ttu-id="54e7c-115">int</span><span class="sxs-lookup"><span data-stu-id="54e7c-115">int</span></span>  <br/> |<span data-ttu-id="54e7c-116">Primary</span><span class="sxs-lookup"><span data-stu-id="54e7c-116">Primary</span></span>  <br/> |<span data-ttu-id="54e7c-117">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="54e7c-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="54e7c-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="54e7c-118">**UserUri**</span></span> <br/> |<span data-ttu-id="54e7c-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="54e7c-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="54e7c-120">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="54e7c-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="54e7c-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="54e7c-121">**TenantId**</span></span> <br/> |<span data-ttu-id="54e7c-122">int</span><span class="sxs-lookup"><span data-stu-id="54e7c-122">int</span></span>  <br/> |<span data-ttu-id="54e7c-123">Externa</span><span class="sxs-lookup"><span data-stu-id="54e7c-123">Foreign</span></span>  <br/> |<span data-ttu-id="54e7c-124">Identificador del inquilino. de este usuario</span><span class="sxs-lookup"><span data-stu-id="54e7c-124">This user's Tenant ID.</span></span> <span data-ttu-id="54e7c-125">Consulte la [tabla de los inquilinos](tenants.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="54e7c-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="54e7c-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="54e7c-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="54e7c-127">int</span><span class="sxs-lookup"><span data-stu-id="54e7c-127">int</span></span>  <br/> |<span data-ttu-id="54e7c-128">Externa</span><span class="sxs-lookup"><span data-stu-id="54e7c-128">Foreign</span></span>  <br/> |<span data-ttu-id="54e7c-129">Tipo de URI de este usuario.</span><span class="sxs-lookup"><span data-stu-id="54e7c-129">This user's URI type.</span></span> <span data-ttu-id="54e7c-130">Consulte la [tabla UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="54e7c-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

