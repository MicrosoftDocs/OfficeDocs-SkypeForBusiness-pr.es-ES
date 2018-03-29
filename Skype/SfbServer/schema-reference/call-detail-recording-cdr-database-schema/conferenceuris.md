---
title: Tabla ConferenceUris en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La tabla ConfereneUris es un auxiliar que almacena una lista de la conferencia varios identificadores URI que participaron en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla representa una conferencia URI.
ms.openlocfilehash: 921bb448ffe50d62aa7680db0e8097c186eef8e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d606f-104">Tabla ConferenceUris en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d606f-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d606f-105">La tabla ConfereneUris es un auxiliar que almacena una lista de la conferencia varios identificadores URI que participaron en sesiones de conferencia registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d606f-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="d606f-106">Cada registro de la tabla representa una conferencia URI.</span><span class="sxs-lookup"><span data-stu-id="d606f-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="d606f-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d606f-107">**Column**</span></span>|<span data-ttu-id="d606f-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d606f-108">**Data Type**</span></span>|<span data-ttu-id="d606f-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d606f-109">**Key/Index**</span></span>|<span data-ttu-id="d606f-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d606f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d606f-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="d606f-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="d606f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d606f-112">datetime</span></span>  <br/> |<span data-ttu-id="d606f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d606f-113">Primary</span></span>  <br/> |<span data-ttu-id="d606f-114">Marca de tiempo interno utilizado.</span><span class="sxs-lookup"><span data-stu-id="d606f-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="d606f-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="d606f-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="d606f-116">int</span><span class="sxs-lookup"><span data-stu-id="d606f-116">int</span></span>  <br/> |<span data-ttu-id="d606f-117">Primary</span><span class="sxs-lookup"><span data-stu-id="d606f-117">Primary</span></span>  <br/> |<span data-ttu-id="d606f-118">Número único que identifica esta conferencia URI.</span><span class="sxs-lookup"><span data-stu-id="d606f-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="d606f-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="d606f-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="d606f-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d606f-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="d606f-121">Conferencia de URI.</span><span class="sxs-lookup"><span data-stu-id="d606f-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="d606f-122">**Suma de comprobación**</span><span class="sxs-lookup"><span data-stu-id="d606f-122">**Checksum**</span></span> <br/> |<span data-ttu-id="d606f-123">int</span><span class="sxs-lookup"><span data-stu-id="d606f-123">int</span></span>  <br/> ||<span data-ttu-id="d606f-124">Suma de comprobación de ConferenceUri.</span><span class="sxs-lookup"><span data-stu-id="d606f-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="d606f-125">Utilizado para aumenta la velocidad de las búsquedas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="d606f-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="d606f-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="d606f-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="d606f-127">int</span><span class="sxs-lookup"><span data-stu-id="d606f-127">int</span></span>  <br/> |<span data-ttu-id="d606f-128">Externa</span><span class="sxs-lookup"><span data-stu-id="d606f-128">Foreign</span></span>  <br/> |<span data-ttu-id="d606f-129">Tipo de identificador URI, como conf:chat para la conferencia de mensajes Instantáneos o conf:audio-vídeo para conferencias de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="d606f-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="d606f-130">Consulte la tabla [UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d606f-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

