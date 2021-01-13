---
title: Tabla UserStatistics
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabla UserStatistics es una tabla auxiliar. Cada registro de la tabla almacena información sobre el uso del sistema por parte de un usuario individual. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813110"
---
# <a name="userstatistics-table"></a><span data-ttu-id="faea6-105">Tabla UserStatistics</span><span class="sxs-lookup"><span data-stu-id="faea6-105">UserStatistics table</span></span>
 
<span data-ttu-id="faea6-106">La tabla UserStatistics es una tabla auxiliar.</span><span class="sxs-lookup"><span data-stu-id="faea6-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="faea6-107">Cada registro de la tabla almacena información sobre el uso del sistema por parte de un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="faea6-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="faea6-108">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="faea6-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="faea6-109">**Columna**</span><span class="sxs-lookup"><span data-stu-id="faea6-109">**Column**</span></span>|<span data-ttu-id="faea6-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="faea6-110">**Data Type**</span></span>|<span data-ttu-id="faea6-111">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="faea6-111">**Key/Index**</span></span>|<span data-ttu-id="faea6-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="faea6-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="faea6-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="faea6-113">**UserId**</span></span> <br/> |<span data-ttu-id="faea6-114">entero</span><span class="sxs-lookup"><span data-stu-id="faea6-114">int</span></span>  <br/> |<span data-ttu-id="faea6-115">Principal</span><span class="sxs-lookup"><span data-stu-id="faea6-115">Primary</span></span>  <br/> |<span data-ttu-id="faea6-116">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="faea6-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="faea6-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="faea6-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="faea6-118">datetime</span><span class="sxs-lookup"><span data-stu-id="faea6-118">datetime</span></span>  <br/> ||<span data-ttu-id="faea6-119">Hora de la última vez que el usuario inició sesión.</span><span class="sxs-lookup"><span data-stu-id="faea6-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="faea6-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="faea6-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="faea6-121">datetime</span><span class="sxs-lookup"><span data-stu-id="faea6-121">datetime</span></span>  <br/> ||<span data-ttu-id="faea6-122">Última vez que el usuario organizó una conferencia.</span><span class="sxs-lookup"><span data-stu-id="faea6-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="faea6-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="faea6-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="faea6-124">datetime</span><span class="sxs-lookup"><span data-stu-id="faea6-124">datetime</span></span>  <br/> ||<span data-ttu-id="faea6-125">Última vez que el usuario tuvo un error de llamada.</span><span class="sxs-lookup"><span data-stu-id="faea6-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="faea6-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="faea6-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="faea6-127">datetime</span><span class="sxs-lookup"><span data-stu-id="faea6-127">datetime</span></span>  <br/> ||<span data-ttu-id="faea6-128">Última vez que el usuario tuvo un error de llamada como organizador de conferencia.</span><span class="sxs-lookup"><span data-stu-id="faea6-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

