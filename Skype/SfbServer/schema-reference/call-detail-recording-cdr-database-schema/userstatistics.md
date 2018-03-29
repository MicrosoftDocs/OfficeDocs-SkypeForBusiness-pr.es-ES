---
title: Tabla UserStatistics
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabla UserStatistics es un auxiliar. Cada registro de la tabla almacena información acerca del uso de un usuario individual del sistema. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: c4a7952eada01033836811555d2e448d13133a27
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="userstatistics-table"></a><span data-ttu-id="0cca2-105">Tabla UserStatistics</span><span class="sxs-lookup"><span data-stu-id="0cca2-105">UserStatistics table</span></span>
 
<span data-ttu-id="0cca2-106">La tabla UserStatistics es un auxiliar.</span><span class="sxs-lookup"><span data-stu-id="0cca2-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="0cca2-107">Cada registro de la tabla almacena información acerca del uso de un usuario individual del sistema.</span><span class="sxs-lookup"><span data-stu-id="0cca2-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="0cca2-108">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0cca2-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="0cca2-109">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0cca2-109">**Column**</span></span>|<span data-ttu-id="0cca2-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0cca2-110">**Data Type**</span></span>|<span data-ttu-id="0cca2-111">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="0cca2-111">**Key/Index**</span></span>|<span data-ttu-id="0cca2-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="0cca2-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0cca2-113">**ID de usuario**</span><span class="sxs-lookup"><span data-stu-id="0cca2-113">**UserId**</span></span> <br/> |<span data-ttu-id="0cca2-114">int</span><span class="sxs-lookup"><span data-stu-id="0cca2-114">int</span></span>  <br/> |<span data-ttu-id="0cca2-115">Primary</span><span class="sxs-lookup"><span data-stu-id="0cca2-115">Primary</span></span>  <br/> |<span data-ttu-id="0cca2-116">Número único que identifica este usuario.</span><span class="sxs-lookup"><span data-stu-id="0cca2-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="0cca2-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="0cca2-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="0cca2-118">datetime</span><span class="sxs-lookup"><span data-stu-id="0cca2-118">datetime</span></span>  <br/> ||<span data-ttu-id="0cca2-119">Última vez que el usuario conectado.</span><span class="sxs-lookup"><span data-stu-id="0cca2-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="0cca2-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="0cca2-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="0cca2-121">datetime</span><span class="sxs-lookup"><span data-stu-id="0cca2-121">datetime</span></span>  <br/> ||<span data-ttu-id="0cca2-122">Última vez que el usuario organizó una conferencia.</span><span class="sxs-lookup"><span data-stu-id="0cca2-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="0cca2-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="0cca2-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="0cca2-124">datetime</span><span class="sxs-lookup"><span data-stu-id="0cca2-124">datetime</span></span>  <br/> ||<span data-ttu-id="0cca2-125">Última vez que el usuario error de llamada.</span><span class="sxs-lookup"><span data-stu-id="0cca2-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="0cca2-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="0cca2-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="0cca2-127">datetime</span><span class="sxs-lookup"><span data-stu-id="0cca2-127">datetime</span></span>  <br/> ||<span data-ttu-id="0cca2-128">Última vez que el usuario presentó un error de llamada como un organizador de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="0cca2-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

