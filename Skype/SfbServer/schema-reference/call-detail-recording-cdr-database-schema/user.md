---
title: Vista de usuario
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: La vista de usuario almacena información acerca de los usuarios que han sido necesarios para las llamadas o las sesiones que tienen registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 9e631c101660e8f14bca25f019f5d991a0d9aadd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213182"
---
# <a name="user-view"></a><span data-ttu-id="ca5d6-104">Vista de usuario</span><span class="sxs-lookup"><span data-stu-id="ca5d6-104">User view</span></span>
 
<span data-ttu-id="ca5d6-105">La vista de usuario almacena información acerca de los usuarios que han sido necesarios para las llamadas o las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ca5d6-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="ca5d6-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca5d6-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="ca5d6-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ca5d6-107">**Column**</span></span>|<span data-ttu-id="ca5d6-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ca5d6-108">**Data Type**</span></span>|<span data-ttu-id="ca5d6-109">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ca5d6-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ca5d6-110">UserId</span><span class="sxs-lookup"><span data-stu-id="ca5d6-110">UserId</span></span>  <br/> |<span data-ttu-id="ca5d6-111">int</span><span class="sxs-lookup"><span data-stu-id="ca5d6-111">int</span></span>  <br/> |<span data-ttu-id="ca5d6-112">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="ca5d6-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="ca5d6-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="ca5d6-113">UserUri</span></span>  <br/> |<span data-ttu-id="ca5d6-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="ca5d6-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ca5d6-115">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="ca5d6-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="ca5d6-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="ca5d6-116">TenantKey</span></span>  <br/> |<span data-ttu-id="ca5d6-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ca5d6-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="ca5d6-118">Inquilino del usuario.</span><span class="sxs-lookup"><span data-stu-id="ca5d6-118">Tenant of user.</span></span> <span data-ttu-id="ca5d6-119">Consulte la [tabla de los inquilinos](tenants.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ca5d6-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ca5d6-120">UriType</span><span class="sxs-lookup"><span data-stu-id="ca5d6-120">UriType</span></span>  <br/> |<span data-ttu-id="ca5d6-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca5d6-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ca5d6-122">Tipo de URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="ca5d6-122">Type of user URI.</span></span> <span data-ttu-id="ca5d6-123">Consulte la [tabla UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ca5d6-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

