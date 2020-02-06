---
title: Tabla ConferenceUris en Skype empresarial Server 2015
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La tabla ConfereneUris es una tabla de soporte que almacena una lista de los distintos URI de conferencia que participaron en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla representa un URI de conferencia.
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815318"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d980e-104">Tabla ConferenceUris en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d980e-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d980e-105">La tabla ConfereneUris es una tabla de soporte que almacena una lista de los distintos URI de conferencia que participaron en sesiones de conferencia registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d980e-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="d980e-106">Cada registro de la tabla representa un URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d980e-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="d980e-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d980e-107">**Column**</span></span>|<span data-ttu-id="d980e-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d980e-108">**Data Type**</span></span>|<span data-ttu-id="d980e-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d980e-109">**Key/Index**</span></span>|<span data-ttu-id="d980e-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d980e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d980e-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d980e-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d980e-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d980e-112">datetime</span></span>  <br/> |<span data-ttu-id="d980e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d980e-113">Primary</span></span>  <br/> |<span data-ttu-id="d980e-114">Marca de tiempo, usada internamente.</span><span class="sxs-lookup"><span data-stu-id="d980e-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="d980e-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="d980e-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="d980e-116">int</span><span class="sxs-lookup"><span data-stu-id="d980e-116">int</span></span>  <br/> |<span data-ttu-id="d980e-117">Primary</span><span class="sxs-lookup"><span data-stu-id="d980e-117">Primary</span></span>  <br/> |<span data-ttu-id="d980e-118">Número único que identifica este URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d980e-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="d980e-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="d980e-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="d980e-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d980e-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="d980e-121">URI de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="d980e-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="d980e-122">**Comprobación**</span><span class="sxs-lookup"><span data-stu-id="d980e-122">**Checksum**</span></span> <br/> |<span data-ttu-id="d980e-123">int</span><span class="sxs-lookup"><span data-stu-id="d980e-123">int</span></span>  <br/> ||<span data-ttu-id="d980e-124">Suma de comprobación de ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="d980e-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="d980e-125">Se usa para aumentar la velocidad de las búsquedas de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="d980e-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="d980e-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="d980e-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="d980e-127">int</span><span class="sxs-lookup"><span data-stu-id="d980e-127">int</span></span>  <br/> |<span data-ttu-id="d980e-128">Extranjero</span><span class="sxs-lookup"><span data-stu-id="d980e-128">Foreign</span></span>  <br/> |<span data-ttu-id="d980e-129">Tipo de URI, como conf: chat para conferencias de mensajería instantánea o conf: audio-video para conferencias de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="d980e-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="d980e-130">Para obtener más información, consulte la tabla de la [tabla UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="d980e-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

