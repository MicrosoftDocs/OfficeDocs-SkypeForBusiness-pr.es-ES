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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: La vista de usuario almacena información sobre los usuarios que han participado en llamadas o sesiones que tienen registros en la base de datos. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 1d170b558dbf77cd8ebeff09a914826830d5621d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814838"
---
# <a name="user-view"></a><span data-ttu-id="422c0-104">Vista de usuario</span><span class="sxs-lookup"><span data-stu-id="422c0-104">User view</span></span>
 
<span data-ttu-id="422c0-105">La vista de usuario almacena información sobre los usuarios que han participado en llamadas o sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="422c0-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="422c0-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="422c0-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="422c0-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="422c0-107">**Column**</span></span>|<span data-ttu-id="422c0-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="422c0-108">**Data Type**</span></span>|<span data-ttu-id="422c0-109">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="422c0-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="422c0-110">Iddeusuario</span><span class="sxs-lookup"><span data-stu-id="422c0-110">UserId</span></span>  <br/> |<span data-ttu-id="422c0-111">int</span><span class="sxs-lookup"><span data-stu-id="422c0-111">int</span></span>  <br/> |<span data-ttu-id="422c0-112">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="422c0-112">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="422c0-113">UserUri</span><span class="sxs-lookup"><span data-stu-id="422c0-113">UserUri</span></span>  <br/> |<span data-ttu-id="422c0-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="422c0-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="422c0-115">Identificador URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="422c0-115">Uri of the user.</span></span>  <br/> |
|<span data-ttu-id="422c0-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="422c0-116">TenantKey</span></span>  <br/> |<span data-ttu-id="422c0-117">identificador</span><span class="sxs-lookup"><span data-stu-id="422c0-117">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="422c0-118">Espacio empresarial de usuario.</span><span class="sxs-lookup"><span data-stu-id="422c0-118">Tenant of user.</span></span> <span data-ttu-id="422c0-119">Para obtener más información, consulte la [tabla de inquilinos](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="422c0-119">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="422c0-120">UriType</span><span class="sxs-lookup"><span data-stu-id="422c0-120">UriType</span></span>  <br/> |<span data-ttu-id="422c0-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="422c0-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="422c0-122">Tipo de URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="422c0-122">Type of user URI.</span></span> <span data-ttu-id="422c0-123">Para obtener más información, consulte la [tabla UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="422c0-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

