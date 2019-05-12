---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute es una tabla que contiene los atributos de visibilidad y el comportamiento que se usan en la tabla Node.
ms.openlocfilehash: b81e8ae09561220df381290eed212ef752820edd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929955"
---
# <a name="tblenumattribute"></a><span data-ttu-id="f0547-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="f0547-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="f0547-104">tblEnumAttribute es una tabla que contiene los atributos de visibilidad y el comportamiento que se usan en la tabla Node.</span><span class="sxs-lookup"><span data-stu-id="f0547-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="f0547-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="f0547-105">**Columns**</span></span>

|<span data-ttu-id="f0547-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="f0547-106">**Column**</span></span>|<span data-ttu-id="f0547-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f0547-107">**Type**</span></span>|<span data-ttu-id="f0547-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f0547-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f0547-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="f0547-109">attributeID</span></span>  <br/> |<span data-ttu-id="f0547-110">smallint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="f0547-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="f0547-111">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="f0547-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="f0547-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="f0547-112">attributeName</span></span>  <br/> |<span data-ttu-id="f0547-113">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="f0547-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="f0547-114">Nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="f0547-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="f0547-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f0547-115">**Key**</span></span>

|<span data-ttu-id="f0547-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="f0547-116">**Column**</span></span>|<span data-ttu-id="f0547-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f0547-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f0547-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="f0547-118">attributeID</span></span>  <br/> |<span data-ttu-id="f0547-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="f0547-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="f0547-120">**Valores de tabla**</span><span class="sxs-lookup"><span data-stu-id="f0547-120">**Table Values**</span></span>

|<span data-ttu-id="f0547-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="f0547-121">**attributeID**</span></span>|<span data-ttu-id="f0547-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="f0547-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f0547-123">1</span><span class="sxs-lookup"><span data-stu-id="f0547-123">1</span></span>  <br/> |<span data-ttu-id="f0547-124">Visibilidad.</span><span class="sxs-lookup"><span data-stu-id="f0547-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="f0547-125">2</span><span class="sxs-lookup"><span data-stu-id="f0547-125">2</span></span>  <br/> |<span data-ttu-id="f0547-126">Comportamiento.</span><span class="sxs-lookup"><span data-stu-id="f0547-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f0547-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0547-127">See also</span></span>

[<span data-ttu-id="f0547-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="f0547-128">tblNode</span></span>](tblnode.md)
