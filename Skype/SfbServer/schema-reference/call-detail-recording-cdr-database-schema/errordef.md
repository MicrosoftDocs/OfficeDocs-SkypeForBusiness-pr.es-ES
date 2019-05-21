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
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: La tabla ErrorDef almacena información acerca de cada tipo de error que puede ocurrir. Cada registro es un tipo de error.
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296283"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0c297-104">Tabla ErrorDef en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="0c297-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0c297-105">La tabla ErrorDef almacena información acerca de cada tipo de error que puede ocurrir.</span><span class="sxs-lookup"><span data-stu-id="0c297-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="0c297-106">Cada registro es un tipo de error.</span><span class="sxs-lookup"><span data-stu-id="0c297-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="0c297-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0c297-107">**Column**</span></span>|<span data-ttu-id="0c297-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0c297-108">**Data Type**</span></span>|<span data-ttu-id="0c297-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="0c297-109">**Key/Index**</span></span>|<span data-ttu-id="0c297-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="0c297-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0c297-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="0c297-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="0c297-112">int</span><span class="sxs-lookup"><span data-stu-id="0c297-112">int</span></span>  <br/> |<span data-ttu-id="0c297-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0c297-113">Primary</span></span>  <br/> |<span data-ttu-id="0c297-114">Número de identificación único que identifica este tipo de error.</span><span class="sxs-lookup"><span data-stu-id="0c297-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="0c297-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="0c297-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="0c297-116">int</span><span class="sxs-lookup"><span data-stu-id="0c297-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="0c297-117">Código de respuesta SIP estándar asociado a este error.</span><span class="sxs-lookup"><span data-stu-id="0c297-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="0c297-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="0c297-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="0c297-119">int</span><span class="sxs-lookup"><span data-stu-id="0c297-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="0c297-120">IDENTIFICADOR de diagnóstico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0c297-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="0c297-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="0c297-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="0c297-122">ENT</span><span class="sxs-lookup"><span data-stu-id="0c297-122">Int</span></span>  <br/> |<span data-ttu-id="0c297-123">Extranjero</span><span class="sxs-lookup"><span data-stu-id="0c297-123">Foreign</span></span>  <br/> |<span data-ttu-id="0c297-124">Tipo de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0c297-124">Type of the call.</span></span> <span data-ttu-id="0c297-125">Para obtener más información, consulte la [tabla CallType en Skype empresarial Server 2015](calltype.md) .</span><span class="sxs-lookup"><span data-stu-id="0c297-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0c297-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="0c297-126">**RequestType**</span></span> <br/> |<span data-ttu-id="0c297-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="0c297-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="0c297-128">Tipo de solicitud en la que se produjo un error.</span><span class="sxs-lookup"><span data-stu-id="0c297-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="0c297-129">Estos datos se pueden convertir a formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0c297-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="0c297-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="0c297-130">**ContentType**</span></span> <br/> |<span data-ttu-id="0c297-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="0c297-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="0c297-132">Tipo de contenido de la solicitud en la que se produjo un error.</span><span class="sxs-lookup"><span data-stu-id="0c297-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="0c297-133">Estos datos se pueden convertir a formato de texto con este sintaxis:</span><span class="sxs-lookup"><span data-stu-id="0c297-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

