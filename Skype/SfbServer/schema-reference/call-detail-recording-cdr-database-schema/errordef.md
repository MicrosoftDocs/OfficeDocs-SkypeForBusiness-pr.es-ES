---
title: Tabla ErrorDef en Skype Empresarial Server 2015
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La tabla ErrorDef almacena información sobre cada tipo de error que puede producirse. Cada registro es un tipo de error.
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821730"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d477e-104">Tabla ErrorDef en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d477e-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d477e-105">La tabla ErrorDef almacena información sobre cada tipo de error que puede producirse.</span><span class="sxs-lookup"><span data-stu-id="d477e-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="d477e-106">Cada registro es un tipo de error.</span><span class="sxs-lookup"><span data-stu-id="d477e-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="d477e-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d477e-107">**Column**</span></span>|<span data-ttu-id="d477e-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d477e-108">**Data Type**</span></span>|<span data-ttu-id="d477e-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="d477e-109">**Key/Index**</span></span>|<span data-ttu-id="d477e-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d477e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d477e-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="d477e-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="d477e-112">entero</span><span class="sxs-lookup"><span data-stu-id="d477e-112">int</span></span>  <br/> |<span data-ttu-id="d477e-113">Principal</span><span class="sxs-lookup"><span data-stu-id="d477e-113">Primary</span></span>  <br/> |<span data-ttu-id="d477e-114">Número de identificador único que identifica este tipo de error.</span><span class="sxs-lookup"><span data-stu-id="d477e-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="d477e-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="d477e-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="d477e-116">entero</span><span class="sxs-lookup"><span data-stu-id="d477e-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="d477e-117">Código de respuesta SIP estándar asociado a este error.</span><span class="sxs-lookup"><span data-stu-id="d477e-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="d477e-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="d477e-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="d477e-119">entero</span><span class="sxs-lookup"><span data-stu-id="d477e-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="d477e-120">Id. de diagnóstico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d477e-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="d477e-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="d477e-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="d477e-122">Int</span><span class="sxs-lookup"><span data-stu-id="d477e-122">Int</span></span>  <br/> |<span data-ttu-id="d477e-123">Externo</span><span class="sxs-lookup"><span data-stu-id="d477e-123">Foreign</span></span>  <br/> |<span data-ttu-id="d477e-124">Tipo de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d477e-124">Type of the call.</span></span> <span data-ttu-id="d477e-125">Consulte la [tabla CallType en Skype Empresarial Server 2015](calltype.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d477e-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d477e-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="d477e-126">**RequestType**</span></span> <br/> |<span data-ttu-id="d477e-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="d477e-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="d477e-128">Tipo de solicitud que ha generado errores.</span><span class="sxs-lookup"><span data-stu-id="d477e-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="d477e-129">Estos datos pueden convertirse en formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d477e-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="d477e-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="d477e-130">**ContentType**</span></span> <br/> |<span data-ttu-id="d477e-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="d477e-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="d477e-132">Tipo de contenido de la solicitud que ha generado errores.</span><span class="sxs-lookup"><span data-stu-id="d477e-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="d477e-133">Estos datos se pueden convertir al formato de texto mediante esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d477e-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

