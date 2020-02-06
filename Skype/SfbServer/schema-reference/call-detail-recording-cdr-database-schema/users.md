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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabla usuarios es una tabla de soporte técnico. Cada registro de la tabla almacena información acerca de un usuario implicado en llamadas o sesiones que tienen registros en la base de datos.
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814808"
---
# <a name="users-table"></a><span data-ttu-id="82c8b-104">Tabla Users</span><span class="sxs-lookup"><span data-stu-id="82c8b-104">Users table</span></span>
 
<span data-ttu-id="82c8b-105">La tabla usuarios es una tabla de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="82c8b-105">The Users table is a supporting table.</span></span> <span data-ttu-id="82c8b-106">Cada registro de la tabla almacena información acerca de un usuario implicado en llamadas o sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="82c8b-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>
  
|<span data-ttu-id="82c8b-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="82c8b-107">**Column**</span></span>|<span data-ttu-id="82c8b-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="82c8b-108">**Data Type**</span></span>|<span data-ttu-id="82c8b-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="82c8b-109">**Key/Index**</span></span>|<span data-ttu-id="82c8b-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="82c8b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="82c8b-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="82c8b-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="82c8b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="82c8b-112">datetime</span></span>  <br/> ||<span data-ttu-id="82c8b-113">Marca de tiempo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="82c8b-113">Time stamp for internal use.</span></span>  <br/> |
|<span data-ttu-id="82c8b-114">**Iddeusuario**</span><span class="sxs-lookup"><span data-stu-id="82c8b-114">**UserId**</span></span> <br/> |<span data-ttu-id="82c8b-115">int</span><span class="sxs-lookup"><span data-stu-id="82c8b-115">int</span></span>  <br/> |<span data-ttu-id="82c8b-116">Primary</span><span class="sxs-lookup"><span data-stu-id="82c8b-116">Primary</span></span>  <br/> |<span data-ttu-id="82c8b-117">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="82c8b-117">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="82c8b-118">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="82c8b-118">**UserUri**</span></span> <br/> |<span data-ttu-id="82c8b-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="82c8b-119">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="82c8b-120">URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="82c8b-120">User URI.</span></span>  <br/> |
|<span data-ttu-id="82c8b-121">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="82c8b-121">**TenantId**</span></span> <br/> |<span data-ttu-id="82c8b-122">int</span><span class="sxs-lookup"><span data-stu-id="82c8b-122">int</span></span>  <br/> |<span data-ttu-id="82c8b-123">Extranjero</span><span class="sxs-lookup"><span data-stu-id="82c8b-123">Foreign</span></span>  <br/> |<span data-ttu-id="82c8b-124">El identificador de inquilino de este usuario.</span><span class="sxs-lookup"><span data-stu-id="82c8b-124">This user's Tenant ID.</span></span> <span data-ttu-id="82c8b-125">Para obtener más información, consulte la [tabla de inquilinos](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="82c8b-125">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="82c8b-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="82c8b-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="82c8b-127">int</span><span class="sxs-lookup"><span data-stu-id="82c8b-127">int</span></span>  <br/> |<span data-ttu-id="82c8b-128">Extranjero</span><span class="sxs-lookup"><span data-stu-id="82c8b-128">Foreign</span></span>  <br/> |<span data-ttu-id="82c8b-129">Tipo de URI de este usuario.</span><span class="sxs-lookup"><span data-stu-id="82c8b-129">This user's URI type.</span></span> <span data-ttu-id="82c8b-130">Para obtener más información, consulte la [tabla UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="82c8b-130">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

