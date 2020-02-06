---
title: Tabla ErrorDef en Skype empresarial Server 2015
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La tabla ErrorDef almacena información acerca de cada tipo de error que puede ocurrir. Cada registro es un tipo de error.
ms.openlocfilehash: f686692bee334c0927b6e8342cfb7152b3e54f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815238"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d8f89-104">Tabla ErrorDef en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d8f89-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d8f89-105">La tabla ErrorDef almacena información acerca de cada tipo de error que puede ocurrir.</span><span class="sxs-lookup"><span data-stu-id="d8f89-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="d8f89-106">Cada registro es un tipo de error.</span><span class="sxs-lookup"><span data-stu-id="d8f89-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="d8f89-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d8f89-107">**Column**</span></span>|<span data-ttu-id="d8f89-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d8f89-108">**Data Type**</span></span>|<span data-ttu-id="d8f89-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d8f89-109">**Key/Index**</span></span>|<span data-ttu-id="d8f89-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d8f89-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d8f89-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="d8f89-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="d8f89-112">int</span><span class="sxs-lookup"><span data-stu-id="d8f89-112">int</span></span>  <br/> |<span data-ttu-id="d8f89-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d8f89-113">Primary</span></span>  <br/> |<span data-ttu-id="d8f89-114">Número de identificación único que identifica este tipo de error.</span><span class="sxs-lookup"><span data-stu-id="d8f89-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="d8f89-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="d8f89-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="d8f89-116">int</span><span class="sxs-lookup"><span data-stu-id="d8f89-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="d8f89-117">Código de respuesta SIP estándar asociado a este error.</span><span class="sxs-lookup"><span data-stu-id="d8f89-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="d8f89-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="d8f89-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="d8f89-119">int</span><span class="sxs-lookup"><span data-stu-id="d8f89-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="d8f89-120">IDENTIFICADOR de diagnóstico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d8f89-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="d8f89-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="d8f89-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="d8f89-122">ENT</span><span class="sxs-lookup"><span data-stu-id="d8f89-122">Int</span></span>  <br/> |<span data-ttu-id="d8f89-123">Extranjero</span><span class="sxs-lookup"><span data-stu-id="d8f89-123">Foreign</span></span>  <br/> |<span data-ttu-id="d8f89-124">Tipo de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d8f89-124">Type of the call.</span></span> <span data-ttu-id="d8f89-125">Para obtener más información, consulte la [tabla CallType en Skype empresarial Server 2015](calltype.md) .</span><span class="sxs-lookup"><span data-stu-id="d8f89-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d8f89-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="d8f89-126">**RequestType**</span></span> <br/> |<span data-ttu-id="d8f89-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="d8f89-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="d8f89-128">Tipo de solicitud en la que se produjo un error.</span><span class="sxs-lookup"><span data-stu-id="d8f89-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="d8f89-129">Estos datos se pueden convertir a formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d8f89-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="d8f89-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="d8f89-130">**ContentType**</span></span> <br/> |<span data-ttu-id="d8f89-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="d8f89-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="d8f89-132">Tipo de contenido de la solicitud en la que se produjo un error.</span><span class="sxs-lookup"><span data-stu-id="d8f89-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="d8f89-133">Estos datos se pueden convertir a formato de texto con este sintaxis:</span><span class="sxs-lookup"><span data-stu-id="d8f89-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

