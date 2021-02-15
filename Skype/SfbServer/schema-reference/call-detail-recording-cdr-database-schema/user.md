---
title: Vista de usuario
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: La vista de usuario almacena información sobre usuarios que han participado en llamadas o sesiones con registros en la base de datos. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831700"
---
# <a name="user-view"></a><span data-ttu-id="7ac13-104">Vista de usuario</span><span class="sxs-lookup"><span data-stu-id="7ac13-104">User view</span></span>
 
<span data-ttu-id="7ac13-105">La vista de usuario almacena información sobre usuarios que han participado en llamadas o sesiones con registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7ac13-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="7ac13-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ac13-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="7ac13-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7ac13-107">**Column**</span></span>|<span data-ttu-id="7ac13-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="7ac13-108">**Data Type**</span></span>|<span data-ttu-id="7ac13-109">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="7ac13-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7ac13-110">UserId</span><span class="sxs-lookup"><span data-stu-id="7ac13-110">UserId</span></span>  <br/> |<span data-ttu-id="7ac13-111">entero</span><span class="sxs-lookup"><span data-stu-id="7ac13-111">int</span></span>  <br/> |<span data-ttu-id="7ac13-112">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="7ac13-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="7ac13-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="7ac13-113">UserUri</span></span>  <br/> |<span data-ttu-id="7ac13-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="7ac13-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="7ac13-115">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="7ac13-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="7ac13-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="7ac13-116">TenantKey</span></span>  <br/> |<span data-ttu-id="7ac13-117">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="7ac13-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="7ac13-118">Inquilino del usuario.</span><span class="sxs-lookup"><span data-stu-id="7ac13-118">Tenant of user.</span></span> <span data-ttu-id="7ac13-119">Vea la [tabla Inquilinos](tenants.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7ac13-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="7ac13-120">UriType</span><span class="sxs-lookup"><span data-stu-id="7ac13-120">UriType</span></span>  <br/> |<span data-ttu-id="7ac13-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="7ac13-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="7ac13-122">Tipo de URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="7ac13-122">Type of user URI.</span></span> <span data-ttu-id="7ac13-123">Vea la [tabla UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7ac13-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

