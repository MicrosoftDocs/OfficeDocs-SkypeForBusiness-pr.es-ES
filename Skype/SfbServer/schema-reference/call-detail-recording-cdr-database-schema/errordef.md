---
title: Tabla ErrorDef en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La tabla ErrorDef almacena información sobre cada tipo de error que puede producirse. Cada registro es un tipo de error.
ms.openlocfilehash: 4583e1130d257a99d075f2dec0dea80ee6b1390c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="866e1-104">Tabla ErrorDef en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="866e1-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="866e1-105">La tabla ErrorDef almacena información sobre cada tipo de error que puede producirse.</span><span class="sxs-lookup"><span data-stu-id="866e1-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="866e1-106">Cada registro es un tipo de error.</span><span class="sxs-lookup"><span data-stu-id="866e1-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="866e1-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="866e1-107">**Column**</span></span>|<span data-ttu-id="866e1-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="866e1-108">**Data Type**</span></span>|<span data-ttu-id="866e1-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="866e1-109">**Key/Index**</span></span>|<span data-ttu-id="866e1-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="866e1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="866e1-111">**Identificador del error**</span><span class="sxs-lookup"><span data-stu-id="866e1-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="866e1-112">int</span><span class="sxs-lookup"><span data-stu-id="866e1-112">int</span></span>  <br/> |<span data-ttu-id="866e1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="866e1-113">Primary</span></span>  <br/> |<span data-ttu-id="866e1-114">Número de identificación exclusivo que identifica este tipo de error.</span><span class="sxs-lookup"><span data-stu-id="866e1-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="866e1-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="866e1-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="866e1-116">int</span><span class="sxs-lookup"><span data-stu-id="866e1-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="866e1-117">Código de respuesta SIP estándar asociada a este error.</span><span class="sxs-lookup"><span data-stu-id="866e1-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="866e1-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="866e1-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="866e1-119">int</span><span class="sxs-lookup"><span data-stu-id="866e1-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="866e1-120">Id. de diagnóstico de Microsoft</span><span class="sxs-lookup"><span data-stu-id="866e1-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="866e1-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="866e1-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="866e1-122">Int</span><span class="sxs-lookup"><span data-stu-id="866e1-122">Int</span></span>  <br/> |<span data-ttu-id="866e1-123">Externa</span><span class="sxs-lookup"><span data-stu-id="866e1-123">Foreign</span></span>  <br/> |<span data-ttu-id="866e1-124">Tipo de la llamada.</span><span class="sxs-lookup"><span data-stu-id="866e1-124">Type of the call.</span></span> <span data-ttu-id="866e1-125">Consulte la [tabla de CallType en Skype para Business Server 2015](calltype.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="866e1-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="866e1-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="866e1-126">**RequestType**</span></span> <br/> |<span data-ttu-id="866e1-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="866e1-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="866e1-128">Tipo de solicitud que falló.</span><span class="sxs-lookup"><span data-stu-id="866e1-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="866e1-129">Estos datos se pueden convertir a formato de texto utilizando esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="866e1-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="866e1-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="866e1-130">**ContentType**</span></span> <br/> |<span data-ttu-id="866e1-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="866e1-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="866e1-132">Tipo de contenido de la solicitud que falló.</span><span class="sxs-lookup"><span data-stu-id="866e1-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="866e1-133">Estos datos se pueden convertir a formato de texto mediante el uso de este syntaxt:</span><span class="sxs-lookup"><span data-stu-id="866e1-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

