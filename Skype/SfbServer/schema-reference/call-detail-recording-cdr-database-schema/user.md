---
title: Vista de usuario
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: La vista de usuario almacena información sobre los usuarios que han participado en llamadas o sesiones que tengan registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 014b773a60cc053c0ec258c7dd853e31a590319c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="user-view"></a><span data-ttu-id="7a9a1-104">Vista de usuario</span><span class="sxs-lookup"><span data-stu-id="7a9a1-104">User view</span></span>
 
<span data-ttu-id="7a9a1-105">La vista de usuario almacena información sobre los usuarios que han participado en llamadas o sesiones que tengan registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a9a1-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="7a9a1-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a9a1-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="7a9a1-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7a9a1-107">**Column**</span></span>|<span data-ttu-id="7a9a1-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="7a9a1-108">**Data Type**</span></span>|<span data-ttu-id="7a9a1-109">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="7a9a1-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7a9a1-110">ID de usuario</span><span class="sxs-lookup"><span data-stu-id="7a9a1-110">UserId</span></span>  <br/> |<span data-ttu-id="7a9a1-111">int</span><span class="sxs-lookup"><span data-stu-id="7a9a1-111">int</span></span>  <br/> |<span data-ttu-id="7a9a1-112">Número único que identifica este usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9a1-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="7a9a1-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="7a9a1-113">UserUri</span></span>  <br/> |<span data-ttu-id="7a9a1-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="7a9a1-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="7a9a1-115">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9a1-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="7a9a1-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="7a9a1-116">TenantKey</span></span>  <br/> |<span data-ttu-id="7a9a1-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="7a9a1-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="7a9a1-118">Inquilinos del usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9a1-118">Tenant of user.</span></span> <span data-ttu-id="7a9a1-119">Consulte la [tabla de los inquilinos](tenants.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7a9a1-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="7a9a1-120">UriType</span><span class="sxs-lookup"><span data-stu-id="7a9a1-120">UriType</span></span>  <br/> |<span data-ttu-id="7a9a1-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7a9a1-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7a9a1-122">Tipo de URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="7a9a1-122">Type of user URI.</span></span> <span data-ttu-id="7a9a1-123">Consulte la [tabla de UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7a9a1-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

