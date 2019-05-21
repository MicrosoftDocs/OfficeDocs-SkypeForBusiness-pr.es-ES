---
title: Vista de usuario
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: La vista de usuario almacena información sobre los usuarios que han participado en llamadas o sesiones que tienen registros en la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 2fe0ba4748a776a8f17065a3c5db21d34bd6340d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295744"
---
# <a name="user-view"></a><span data-ttu-id="feddf-104">Vista de usuario</span><span class="sxs-lookup"><span data-stu-id="feddf-104">User view</span></span>
 
<span data-ttu-id="feddf-105">La vista de usuario almacena información sobre los usuarios que han participado en llamadas o sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="feddf-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="feddf-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="feddf-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="feddf-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="feddf-107">**Column**</span></span>|<span data-ttu-id="feddf-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="feddf-108">**Data Type**</span></span>|<span data-ttu-id="feddf-109">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="feddf-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="feddf-110">Iddeusuario</span><span class="sxs-lookup"><span data-stu-id="feddf-110">UserId</span></span>  <br/> |<span data-ttu-id="feddf-111">int</span><span class="sxs-lookup"><span data-stu-id="feddf-111">int</span></span>  <br/> |<span data-ttu-id="feddf-112">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="feddf-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="feddf-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="feddf-113">UserUri</span></span>  <br/> |<span data-ttu-id="feddf-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="feddf-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="feddf-115">Identificador URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="feddf-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="feddf-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="feddf-116">TenantKey</span></span>  <br/> |<span data-ttu-id="feddf-117">identificador</span><span class="sxs-lookup"><span data-stu-id="feddf-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="feddf-118">Espacio empresarial de usuario.</span><span class="sxs-lookup"><span data-stu-id="feddf-118">Tenant of user.</span></span> <span data-ttu-id="feddf-119">Para obtener más información, consulte la [tabla](tenants.md) de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="feddf-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="feddf-120">UriType</span><span class="sxs-lookup"><span data-stu-id="feddf-120">UriType</span></span>  <br/> |<span data-ttu-id="feddf-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="feddf-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="feddf-122">Tipo de URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="feddf-122">Type of user URI.</span></span> <span data-ttu-id="feddf-123">Para obtener más información, consulte la [tabla UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="feddf-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

