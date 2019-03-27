---
title: Tabla ErrorDef en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: En la tabla ErrorDef almacena información acerca de cada tipo de error que puedan surgir. Cada registro es un tipo de error.
ms.openlocfilehash: cec601dad24dda522477bfcd7b1e80d0efc45799
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899070"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3127e-104">Tabla ErrorDef en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3127e-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3127e-105">En la tabla ErrorDef almacena información acerca de cada tipo de error que puedan surgir.</span><span class="sxs-lookup"><span data-stu-id="3127e-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="3127e-106">Cada registro es un tipo de error.</span><span class="sxs-lookup"><span data-stu-id="3127e-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="3127e-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3127e-107">**Column**</span></span>|<span data-ttu-id="3127e-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="3127e-108">**Data Type**</span></span>|<span data-ttu-id="3127e-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="3127e-109">**Key/Index**</span></span>|<span data-ttu-id="3127e-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="3127e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3127e-111">**Identificador del error**</span><span class="sxs-lookup"><span data-stu-id="3127e-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="3127e-112">int</span><span class="sxs-lookup"><span data-stu-id="3127e-112">int</span></span>  <br/> |<span data-ttu-id="3127e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3127e-113">Primary</span></span>  <br/> |<span data-ttu-id="3127e-114">Número de identificador único que identifica este tipo de error.</span><span class="sxs-lookup"><span data-stu-id="3127e-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="3127e-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="3127e-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="3127e-116">int</span><span class="sxs-lookup"><span data-stu-id="3127e-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="3127e-117">Código de respuesta SIP estándar asociado con este error.</span><span class="sxs-lookup"><span data-stu-id="3127e-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="3127e-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="3127e-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="3127e-119">int</span><span class="sxs-lookup"><span data-stu-id="3127e-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="3127e-120">Identificador de diagnóstico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3127e-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="3127e-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="3127e-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="3127e-122">Int</span><span class="sxs-lookup"><span data-stu-id="3127e-122">Int</span></span>  <br/> |<span data-ttu-id="3127e-123">Externa</span><span class="sxs-lookup"><span data-stu-id="3127e-123">Foreign</span></span>  <br/> |<span data-ttu-id="3127e-124">Tipo de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3127e-124">Type of the call.</span></span> <span data-ttu-id="3127e-125">Vea la [tabla CallType en Skype para Business Server 2015](calltype.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3127e-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3127e-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="3127e-126">**RequestType**</span></span> <br/> |<span data-ttu-id="3127e-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="3127e-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="3127e-128">Tipo de solicitud que ha fallado.</span><span class="sxs-lookup"><span data-stu-id="3127e-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="3127e-129">Estos datos pueden convertirse a formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="3127e-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="3127e-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="3127e-130">**ContentType**</span></span> <br/> |<span data-ttu-id="3127e-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="3127e-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="3127e-132">Tipo de contenido de la solicitud que ha fallado.</span><span class="sxs-lookup"><span data-stu-id="3127e-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="3127e-133">Estos datos pueden convertirse a formato de texto mediante el uso de este syntaxt:</span><span class="sxs-lookup"><span data-stu-id="3127e-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

