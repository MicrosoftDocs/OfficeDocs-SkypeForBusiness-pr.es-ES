---
title: Tabla Users
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: En la tabla de usuarios es una tabla de apoyo. Cada registro en la tabla almacena información sobre un usuario que participó en las llamadas o las sesiones que tienen registros en la base de datos.
ms.openlocfilehash: fbe3ff7d2570f78cdf3b3418629fb9fd6209d944
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929990"
---
# <a name="users-table"></a><span data-ttu-id="1ed7e-104">Tabla Users</span><span class="sxs-lookup"><span data-stu-id="1ed7e-104">Users table</span></span>
 
<span data-ttu-id="1ed7e-105">En la tabla de usuarios es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="1ed7e-105">The Users table is a supporting table.</span></span> <span data-ttu-id="1ed7e-106">Cada registro en la tabla almacena información sobre un usuario que participó en las llamadas o las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1ed7e-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="1ed7e-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1ed7e-107">**Column**</span></span>|<span data-ttu-id="1ed7e-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="1ed7e-108">**Data Type**</span></span>|<span data-ttu-id="1ed7e-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="1ed7e-109">**Key/Index**</span></span>|<span data-ttu-id="1ed7e-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="1ed7e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1ed7e-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="1ed7e-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="1ed7e-112">datetime</span><span class="sxs-lookup"><span data-stu-id="1ed7e-112">datetime</span></span>  <br/> ||<span data-ttu-id="1ed7e-113">Marca de tiempo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="1ed7e-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="1ed7e-114">**UserId**</span><span class="sxs-lookup"><span data-stu-id="1ed7e-114">**UserId**</span></span> <br/> |<span data-ttu-id="1ed7e-115">int</span><span class="sxs-lookup"><span data-stu-id="1ed7e-115">int</span></span>  <br/> |<span data-ttu-id="1ed7e-116">Primary</span><span class="sxs-lookup"><span data-stu-id="1ed7e-116">Primary</span></span>  <br/> |<span data-ttu-id="1ed7e-117">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="1ed7e-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="1ed7e-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="1ed7e-118">**UserUri**</span></span> <br/> |<span data-ttu-id="1ed7e-119">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="1ed7e-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="1ed7e-120">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="1ed7e-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="1ed7e-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="1ed7e-121">**TenantId**</span></span> <br/> |<span data-ttu-id="1ed7e-122">int</span><span class="sxs-lookup"><span data-stu-id="1ed7e-122">int</span></span>  <br/> |<span data-ttu-id="1ed7e-123">Externa</span><span class="sxs-lookup"><span data-stu-id="1ed7e-123">Foreign</span></span>  <br/> |<span data-ttu-id="1ed7e-124">Identificador del inquilino. de este usuario</span><span class="sxs-lookup"><span data-stu-id="1ed7e-124">This user's Tenant ID.</span></span> <span data-ttu-id="1ed7e-125">Consulte la [tabla de los inquilinos](tenants.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1ed7e-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="1ed7e-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="1ed7e-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="1ed7e-127">int</span><span class="sxs-lookup"><span data-stu-id="1ed7e-127">int</span></span>  <br/> |<span data-ttu-id="1ed7e-128">Externa</span><span class="sxs-lookup"><span data-stu-id="1ed7e-128">Foreign</span></span>  <br/> |<span data-ttu-id="1ed7e-129">Tipo de URI de este usuario.</span><span class="sxs-lookup"><span data-stu-id="1ed7e-129">This user's URI type.</span></span> <span data-ttu-id="1ed7e-130">Consulte la [tabla UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1ed7e-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

