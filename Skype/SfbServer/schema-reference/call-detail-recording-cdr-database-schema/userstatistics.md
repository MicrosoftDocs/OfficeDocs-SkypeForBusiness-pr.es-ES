---
title: Tabla UserStatistics
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: En la tabla UserStatistics es una tabla de apoyo. Cada registro en la tabla almacena información sobre el uso de un usuario concreto del sistema. En esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 45f34a1e8905d19b5ce48d94824591f25ec1ef28
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213042"
---
# <a name="userstatistics-table"></a><span data-ttu-id="e5061-105">Tabla UserStatistics</span><span class="sxs-lookup"><span data-stu-id="e5061-105">UserStatistics table</span></span>
 
<span data-ttu-id="e5061-106">En la tabla UserStatistics es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="e5061-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="e5061-107">Cada registro en la tabla almacena información sobre el uso de un usuario concreto del sistema.</span><span class="sxs-lookup"><span data-stu-id="e5061-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="e5061-108">En esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5061-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e5061-109">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e5061-109">**Column**</span></span>|<span data-ttu-id="e5061-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e5061-110">**Data Type**</span></span>|<span data-ttu-id="e5061-111">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="e5061-111">**Key/Index**</span></span>|<span data-ttu-id="e5061-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="e5061-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e5061-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="e5061-113">**UserId**</span></span> <br/> |<span data-ttu-id="e5061-114">int</span><span class="sxs-lookup"><span data-stu-id="e5061-114">int</span></span>  <br/> |<span data-ttu-id="e5061-115">Primary</span><span class="sxs-lookup"><span data-stu-id="e5061-115">Primary</span></span>  <br/> |<span data-ttu-id="e5061-116">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="e5061-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="e5061-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="e5061-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="e5061-118">datetime</span><span class="sxs-lookup"><span data-stu-id="e5061-118">datetime</span></span>  <br/> ||<span data-ttu-id="e5061-119">Modificó por última vez el usuario iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="e5061-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="e5061-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="e5061-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="e5061-121">datetime</span><span class="sxs-lookup"><span data-stu-id="e5061-121">datetime</span></span>  <br/> ||<span data-ttu-id="e5061-122">Última vez que el usuario organizó una conferencia.</span><span class="sxs-lookup"><span data-stu-id="e5061-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="e5061-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="e5061-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="e5061-124">datetime</span><span class="sxs-lookup"><span data-stu-id="e5061-124">datetime</span></span>  <br/> ||<span data-ttu-id="e5061-125">Última vez que el usuario tuvo un error de llamada.</span><span class="sxs-lookup"><span data-stu-id="e5061-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="e5061-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="e5061-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="e5061-127">datetime</span><span class="sxs-lookup"><span data-stu-id="e5061-127">datetime</span></span>  <br/> ||<span data-ttu-id="e5061-128">Última vez que el usuario tuvo un error de llamada como un organizador de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="e5061-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

