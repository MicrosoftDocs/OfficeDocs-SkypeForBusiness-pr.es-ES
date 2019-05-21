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
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabla UserStatistics es una tabla de soporte. Cada registro de la tabla almacena información sobre el uso del sistema por un usuario individual. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295695"
---
# <a name="userstatistics-table"></a><span data-ttu-id="2c079-105">Tabla UserStatistics</span><span class="sxs-lookup"><span data-stu-id="2c079-105">UserStatistics table</span></span>
 
<span data-ttu-id="2c079-106">La tabla UserStatistics es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="2c079-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="2c079-107">Cada registro de la tabla almacena información sobre el uso del sistema por un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="2c079-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="2c079-108">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2c079-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="2c079-109">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2c079-109">**Column**</span></span>|<span data-ttu-id="2c079-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="2c079-110">**Data Type**</span></span>|<span data-ttu-id="2c079-111">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="2c079-111">**Key/Index**</span></span>|<span data-ttu-id="2c079-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="2c079-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c079-113">**Iddeusuario**</span><span class="sxs-lookup"><span data-stu-id="2c079-113">**UserId**</span></span> <br/> |<span data-ttu-id="2c079-114">int</span><span class="sxs-lookup"><span data-stu-id="2c079-114">int</span></span>  <br/> |<span data-ttu-id="2c079-115">Primary</span><span class="sxs-lookup"><span data-stu-id="2c079-115">Primary</span></span>  <br/> |<span data-ttu-id="2c079-116">Número único que identifica a este usuario.</span><span class="sxs-lookup"><span data-stu-id="2c079-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="2c079-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="2c079-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="2c079-118">datetime</span><span class="sxs-lookup"><span data-stu-id="2c079-118">datetime</span></span>  <br/> ||<span data-ttu-id="2c079-119">La última vez que el usuario inició sesión.</span><span class="sxs-lookup"><span data-stu-id="2c079-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="2c079-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="2c079-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="2c079-121">datetime</span><span class="sxs-lookup"><span data-stu-id="2c079-121">datetime</span></span>  <br/> ||<span data-ttu-id="2c079-122">La última vez que el usuario organizó una conferencia.</span><span class="sxs-lookup"><span data-stu-id="2c079-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="2c079-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="2c079-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="2c079-124">datetime</span><span class="sxs-lookup"><span data-stu-id="2c079-124">datetime</span></span>  <br/> ||<span data-ttu-id="2c079-125">La última vez que el usuario experimentó un error de llamada.</span><span class="sxs-lookup"><span data-stu-id="2c079-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="2c079-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="2c079-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="2c079-127">datetime</span><span class="sxs-lookup"><span data-stu-id="2c079-127">datetime</span></span>  <br/> ||<span data-ttu-id="2c079-128">La última vez que el usuario experimentó un error de llamada como organizador de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="2c079-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

