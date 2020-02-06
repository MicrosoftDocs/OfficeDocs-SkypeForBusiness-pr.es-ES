---
title: Tabla UserStatistics
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabla UserStatistics es una tabla de soporte. Cada registro de la tabla almacena información sobre el uso del sistema por un usuario individual. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 048c26279deb6f89e69784d754567dfde84d9983
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814798"
---
# <a name="userstatistics-table"></a><span data-ttu-id="eea36-105">Tabla UserStatistics</span><span class="sxs-lookup"><span data-stu-id="eea36-105">UserStatistics table</span></span>
 
<span data-ttu-id="eea36-106">La tabla UserStatistics es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="eea36-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="eea36-107">Cada registro de la tabla almacena información sobre el uso del sistema por un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="eea36-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="eea36-108">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eea36-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="eea36-109">**Columna**</span><span class="sxs-lookup"><span data-stu-id="eea36-109">**Column**</span></span>|<span data-ttu-id="eea36-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="eea36-110">**Data Type**</span></span>|<span data-ttu-id="eea36-111">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="eea36-111">**Key/Index**</span></span>|<span data-ttu-id="eea36-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="eea36-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="eea36-113">**Iddeusuario**</span><span class="sxs-lookup"><span data-stu-id="eea36-113">**UserId**</span></span> <br/> |<span data-ttu-id="eea36-114">int</span><span class="sxs-lookup"><span data-stu-id="eea36-114">int</span></span>  <br/> |<span data-ttu-id="eea36-115">Primary</span><span class="sxs-lookup"><span data-stu-id="eea36-115">Primary</span></span>  <br/> |<span data-ttu-id="eea36-116">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="eea36-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="eea36-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="eea36-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="eea36-118">datetime</span><span class="sxs-lookup"><span data-stu-id="eea36-118">datetime</span></span>  <br/> ||<span data-ttu-id="eea36-119">La última vez que el usuario inició sesión.</span><span class="sxs-lookup"><span data-stu-id="eea36-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="eea36-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="eea36-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="eea36-121">datetime</span><span class="sxs-lookup"><span data-stu-id="eea36-121">datetime</span></span>  <br/> ||<span data-ttu-id="eea36-122">La última vez que el usuario organizó una conferencia.</span><span class="sxs-lookup"><span data-stu-id="eea36-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="eea36-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="eea36-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="eea36-124">datetime</span><span class="sxs-lookup"><span data-stu-id="eea36-124">datetime</span></span>  <br/> ||<span data-ttu-id="eea36-125">La última vez que el usuario experimentó un error de llamada.</span><span class="sxs-lookup"><span data-stu-id="eea36-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="eea36-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="eea36-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="eea36-127">datetime</span><span class="sxs-lookup"><span data-stu-id="eea36-127">datetime</span></span>  <br/> ||<span data-ttu-id="eea36-128">La última vez que el usuario experimentó un error de llamada como organizador de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="eea36-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

