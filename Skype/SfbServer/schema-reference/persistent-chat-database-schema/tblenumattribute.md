---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute es una tabla que contiene los atributos de visibilidad y el comportamiento que se usan en la tabla Node.
ms.openlocfilehash: 7555656f02fa7808e54100c03de8f80e0e078678
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879703"
---
# <a name="tblenumattribute"></a><span data-ttu-id="5b64a-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="5b64a-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="5b64a-104">tblEnumAttribute es una tabla que contiene los atributos de visibilidad y el comportamiento que se usan en la tabla Node.</span><span class="sxs-lookup"><span data-stu-id="5b64a-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="5b64a-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="5b64a-105">**Columns**</span></span>

|<span data-ttu-id="5b64a-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5b64a-106">**Column**</span></span>|<span data-ttu-id="5b64a-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5b64a-107">**Type**</span></span>|<span data-ttu-id="5b64a-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5b64a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5b64a-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="5b64a-109">attributeID</span></span>  <br/> |<span data-ttu-id="5b64a-110">smallint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="5b64a-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="5b64a-111">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="5b64a-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="5b64a-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="5b64a-112">attributeName</span></span>  <br/> |<span data-ttu-id="5b64a-113">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="5b64a-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="5b64a-114">Nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="5b64a-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="5b64a-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="5b64a-115">**Key**</span></span>

|<span data-ttu-id="5b64a-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5b64a-116">**Column**</span></span>|<span data-ttu-id="5b64a-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5b64a-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5b64a-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="5b64a-118">attributeID</span></span>  <br/> |<span data-ttu-id="5b64a-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="5b64a-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="5b64a-120">**Valores de tabla**</span><span class="sxs-lookup"><span data-stu-id="5b64a-120">**Table Values**</span></span>

|<span data-ttu-id="5b64a-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="5b64a-121">**attributeID**</span></span>|<span data-ttu-id="5b64a-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="5b64a-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5b64a-123">1</span><span class="sxs-lookup"><span data-stu-id="5b64a-123">1</span></span>  <br/> |<span data-ttu-id="5b64a-124">Visibilidad.</span><span class="sxs-lookup"><span data-stu-id="5b64a-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="5b64a-125">2</span><span class="sxs-lookup"><span data-stu-id="5b64a-125">2</span></span>  <br/> |<span data-ttu-id="5b64a-126">Comportamiento.</span><span class="sxs-lookup"><span data-stu-id="5b64a-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5b64a-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b64a-127">See also</span></span>

[<span data-ttu-id="5b64a-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="5b64a-128">tblNode</span></span>](tblnode.md)
