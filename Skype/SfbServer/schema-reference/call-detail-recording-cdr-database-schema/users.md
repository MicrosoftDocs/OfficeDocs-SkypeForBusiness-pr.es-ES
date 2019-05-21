---
title: Tabla Users
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabla usuarios es una tabla de soporte técnico. Cada registro de la tabla almacena información acerca de un usuario implicado en llamadas o sesiones que tienen registros en la base de datos.
ms.openlocfilehash: 0dcc2fda73305be2bbe6a7a5c546dac0b05f8273
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295702"
---
# <a name="users-table"></a><span data-ttu-id="1d8a8-104">Tabla Users</span><span class="sxs-lookup"><span data-stu-id="1d8a8-104">Users table</span></span>
 
<span data-ttu-id="1d8a8-105">La tabla usuarios es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="1d8a8-105">The Users table is a supporting table.</span></span> <span data-ttu-id="1d8a8-106">Cada registro de la tabla almacena información acerca de un usuario implicado en llamadas o sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d8a8-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="1d8a8-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1d8a8-107">**Column**</span></span>|<span data-ttu-id="1d8a8-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="1d8a8-108">**Data Type**</span></span>|<span data-ttu-id="1d8a8-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="1d8a8-109">**Key/Index**</span></span>|<span data-ttu-id="1d8a8-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="1d8a8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1d8a8-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="1d8a8-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="1d8a8-112">datetime</span><span class="sxs-lookup"><span data-stu-id="1d8a8-112">datetime</span></span>  <br/> ||<span data-ttu-id="1d8a8-113">Marca de tiempo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="1d8a8-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="1d8a8-114">**Iddeusuario**</span><span class="sxs-lookup"><span data-stu-id="1d8a8-114">**UserId**</span></span> <br/> |<span data-ttu-id="1d8a8-115">int</span><span class="sxs-lookup"><span data-stu-id="1d8a8-115">int</span></span>  <br/> |<span data-ttu-id="1d8a8-116">Primary</span><span class="sxs-lookup"><span data-stu-id="1d8a8-116">Primary</span></span>  <br/> |<span data-ttu-id="1d8a8-117">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="1d8a8-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="1d8a8-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="1d8a8-118">**UserUri**</span></span> <br/> |<span data-ttu-id="1d8a8-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1d8a8-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="1d8a8-120">URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="1d8a8-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="1d8a8-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="1d8a8-121">**TenantId**</span></span> <br/> |<span data-ttu-id="1d8a8-122">int</span><span class="sxs-lookup"><span data-stu-id="1d8a8-122">int</span></span>  <br/> |<span data-ttu-id="1d8a8-123">Extranjero</span><span class="sxs-lookup"><span data-stu-id="1d8a8-123">Foreign</span></span>  <br/> |<span data-ttu-id="1d8a8-124">El identificador de inquilino de este usuario.</span><span class="sxs-lookup"><span data-stu-id="1d8a8-124">This user's Tenant ID.</span></span> <span data-ttu-id="1d8a8-125">Para obtener más información, consulte la [tabla](tenants.md) de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="1d8a8-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="1d8a8-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="1d8a8-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="1d8a8-127">int</span><span class="sxs-lookup"><span data-stu-id="1d8a8-127">int</span></span>  <br/> |<span data-ttu-id="1d8a8-128">Extranjero</span><span class="sxs-lookup"><span data-stu-id="1d8a8-128">Foreign</span></span>  <br/> |<span data-ttu-id="1d8a8-129">Tipo de URI de este usuario.</span><span class="sxs-lookup"><span data-stu-id="1d8a8-129">This user's URI type.</span></span> <span data-ttu-id="1d8a8-130">Para obtener más información, consulte la [tabla UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="1d8a8-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

