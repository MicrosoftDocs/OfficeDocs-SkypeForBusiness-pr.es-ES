---
title: Tabla UserStatistics
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: En la tabla UserStatistics es una tabla de apoyo. Cada registro en la tabla almacena información sobre el uso de un usuario concreto del sistema. En esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: c2e0acffa7b75b3c54781e3e4e9a8b033be5e440
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929983"
---
# <a name="userstatistics-table"></a><span data-ttu-id="d84f9-105">Tabla UserStatistics</span><span class="sxs-lookup"><span data-stu-id="d84f9-105">UserStatistics table</span></span>
 
<span data-ttu-id="d84f9-106">En la tabla UserStatistics es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="d84f9-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="d84f9-107">Cada registro en la tabla almacena información sobre el uso de un usuario concreto del sistema.</span><span class="sxs-lookup"><span data-stu-id="d84f9-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="d84f9-108">En esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d84f9-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d84f9-109">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d84f9-109">**Column**</span></span>|<span data-ttu-id="d84f9-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d84f9-110">**Data Type**</span></span>|<span data-ttu-id="d84f9-111">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d84f9-111">**Key/Index**</span></span>|<span data-ttu-id="d84f9-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d84f9-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d84f9-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="d84f9-113">**UserId**</span></span> <br/> |<span data-ttu-id="d84f9-114">int</span><span class="sxs-lookup"><span data-stu-id="d84f9-114">int</span></span>  <br/> |<span data-ttu-id="d84f9-115">Primary</span><span class="sxs-lookup"><span data-stu-id="d84f9-115">Primary</span></span>  <br/> |<span data-ttu-id="d84f9-116">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="d84f9-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="d84f9-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="d84f9-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="d84f9-118">datetime</span><span class="sxs-lookup"><span data-stu-id="d84f9-118">datetime</span></span>  <br/> ||<span data-ttu-id="d84f9-119">Modificó por última vez el usuario iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="d84f9-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="d84f9-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="d84f9-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="d84f9-121">datetime</span><span class="sxs-lookup"><span data-stu-id="d84f9-121">datetime</span></span>  <br/> ||<span data-ttu-id="d84f9-122">Última vez que el usuario organizó una conferencia.</span><span class="sxs-lookup"><span data-stu-id="d84f9-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="d84f9-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="d84f9-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="d84f9-124">datetime</span><span class="sxs-lookup"><span data-stu-id="d84f9-124">datetime</span></span>  <br/> ||<span data-ttu-id="d84f9-125">Última vez que el usuario tuvo un error de llamada.</span><span class="sxs-lookup"><span data-stu-id="d84f9-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="d84f9-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="d84f9-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="d84f9-127">datetime</span><span class="sxs-lookup"><span data-stu-id="d84f9-127">datetime</span></span>  <br/> ||<span data-ttu-id="d84f9-128">Última vez que el usuario tuvo un error de llamada como un organizador de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="d84f9-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

