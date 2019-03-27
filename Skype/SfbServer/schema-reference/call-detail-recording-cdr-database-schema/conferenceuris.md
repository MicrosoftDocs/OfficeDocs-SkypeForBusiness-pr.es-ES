---
title: Tabla ConferenceUris en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: En la tabla de ConfereneUris es una tabla de apoyo que almacena una lista de la conferencia distintos de los identificadores URI que han participado en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla representa un URI de conferencia.
ms.openlocfilehash: 6f373774b652e9858af84dd4c16b51fcb3c5d493
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887774"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3defc-104">Tabla ConferenceUris en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3defc-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3defc-105">En la tabla de ConfereneUris es una tabla de apoyo que almacena una lista de la conferencia distintos de los identificadores URI que han participado en sesiones de conferencia registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3defc-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="3defc-106">Cada registro de la tabla representa un URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="3defc-106">Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="3defc-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3defc-107">**Column**</span></span>|<span data-ttu-id="3defc-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="3defc-108">**Data Type**</span></span>|<span data-ttu-id="3defc-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="3defc-109">**Key/Index**</span></span>|<span data-ttu-id="3defc-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="3defc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3defc-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="3defc-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="3defc-112">datetime</span><span class="sxs-lookup"><span data-stu-id="3defc-112">datetime</span></span>  <br/> |<span data-ttu-id="3defc-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3defc-113">Primary</span></span>  <br/> |<span data-ttu-id="3defc-114">Marca de tiempo, interna utilizada.</span><span class="sxs-lookup"><span data-stu-id="3defc-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="3defc-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="3defc-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="3defc-116">int</span><span class="sxs-lookup"><span data-stu-id="3defc-116">int</span></span>  <br/> |<span data-ttu-id="3defc-117">Primary</span><span class="sxs-lookup"><span data-stu-id="3defc-117">Primary</span></span>  <br/> |<span data-ttu-id="3defc-118">Número único que identifica este URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="3defc-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="3defc-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="3defc-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="3defc-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="3defc-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="3defc-121">URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="3defc-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="3defc-122">**Suma de comprobación**</span><span class="sxs-lookup"><span data-stu-id="3defc-122">**Checksum**</span></span> <br/> |<span data-ttu-id="3defc-123">int</span><span class="sxs-lookup"><span data-stu-id="3defc-123">int</span></span>  <br/> ||<span data-ttu-id="3defc-124">Suma de comprobación de URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="3defc-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="3defc-125">Usado para aumenta la velocidad de las búsquedas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3defc-125">Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="3defc-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="3defc-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="3defc-127">int</span><span class="sxs-lookup"><span data-stu-id="3defc-127">int</span></span>  <br/> |<span data-ttu-id="3defc-128">Externa</span><span class="sxs-lookup"><span data-stu-id="3defc-128">Foreign</span></span>  <br/> |<span data-ttu-id="3defc-129">Tipo de URI, como conf:chat para conferencia de mensajería instantánea o conf:audio-vídeo para conferencias de audio y vídeo.</span><span class="sxs-lookup"><span data-stu-id="3defc-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="3defc-130">Vea la tabla de la [tabla UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3defc-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

