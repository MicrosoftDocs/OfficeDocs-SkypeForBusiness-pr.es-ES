---
title: Tabla ConferenceUris en Skype Empresarial Server 2015
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La tabla ConferenceUris es una tabla auxiliar donde se guarda una lista de las diversas URI de conferencia que han participado en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla corresponde a una URI de conferencia.
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816140"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a><span data-ttu-id="46707-104">Tabla ConferenceUris en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="46707-104">ConferenceUris table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="46707-p102">La tabla ConferenceUris es una tabla auxiliar donde se guarda una lista de las diversas URI de conferencia que han participado en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla corresponde a una URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="46707-p102">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>
  
|<span data-ttu-id="46707-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="46707-107">**Column**</span></span>|<span data-ttu-id="46707-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="46707-108">**Data Type**</span></span>|<span data-ttu-id="46707-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="46707-109">**Key/Index**</span></span>|<span data-ttu-id="46707-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="46707-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="46707-111">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="46707-111">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="46707-112">datetime</span><span class="sxs-lookup"><span data-stu-id="46707-112">datetime</span></span>  <br/> |<span data-ttu-id="46707-113">Principal</span><span class="sxs-lookup"><span data-stu-id="46707-113">Primary</span></span>  <br/> |<span data-ttu-id="46707-114">Marca de tiempo, interna utilizada.</span><span class="sxs-lookup"><span data-stu-id="46707-114">Time stamp, Internal used.</span></span>  <br/> |
|<span data-ttu-id="46707-115">**ConferenceUriId**</span><span class="sxs-lookup"><span data-stu-id="46707-115">**ConferenceUriId**</span></span> <br/> |<span data-ttu-id="46707-116">entero</span><span class="sxs-lookup"><span data-stu-id="46707-116">int</span></span>  <br/> |<span data-ttu-id="46707-117">Principal</span><span class="sxs-lookup"><span data-stu-id="46707-117">Primary</span></span>  <br/> |<span data-ttu-id="46707-118">Número único que identifica esta URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="46707-118">Unique number identifying this conference URI.</span></span>  <br/> |
|<span data-ttu-id="46707-119">**ConferenceUri**</span><span class="sxs-lookup"><span data-stu-id="46707-119">**ConferenceUri**</span></span> <br/> |<span data-ttu-id="46707-120">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="46707-120">nvarchar(450)</span></span>  <br/> ||<span data-ttu-id="46707-121">URI de conferencia.</span><span class="sxs-lookup"><span data-stu-id="46707-121">Conference URI.</span></span>  <br/> |
|<span data-ttu-id="46707-122">**Suma de comprobación**</span><span class="sxs-lookup"><span data-stu-id="46707-122">**Checksum**</span></span> <br/> |<span data-ttu-id="46707-123">entero</span><span class="sxs-lookup"><span data-stu-id="46707-123">int</span></span>  <br/> ||<span data-ttu-id="46707-p103">Suma de comprobación de ConferenceUri. Se utiliza para acelerar las búsquedas en bases de datos.</span><span class="sxs-lookup"><span data-stu-id="46707-p103">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="46707-126">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="46707-126">**UriTypeId**</span></span> <br/> |<span data-ttu-id="46707-127">entero</span><span class="sxs-lookup"><span data-stu-id="46707-127">int</span></span>  <br/> |<span data-ttu-id="46707-128">Externo</span><span class="sxs-lookup"><span data-stu-id="46707-128">Foreign</span></span>  <br/> |<span data-ttu-id="46707-129">Tipo de URI, como por ejemplo conf:chat para conferencia de mensajería instantánea, o conf:audio-video para conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="46707-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="46707-130">Vea la [tabla UriTypes para](uritypes.md) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="46707-130">See the [UriTypes table](uritypes.md) table for more information.</span></span> <br/> |
   

