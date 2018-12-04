---
title: tblEnumAttribute
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
ms.openlocfilehash: bd386bc77d15c627597a5680277235a05d0c8039
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504869"
---
# <a name="tblenumattribute"></a><span data-ttu-id="1d830-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="1d830-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="1d830-104">tblEnumAttribute es una tabla que contiene los atributos de visibilidad y el comportamiento que se usan en la tabla Node.</span><span class="sxs-lookup"><span data-stu-id="1d830-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="1d830-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="1d830-105">**Columns**</span></span>

|<span data-ttu-id="1d830-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1d830-106">**Column**</span></span>|<span data-ttu-id="1d830-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1d830-107">**Type**</span></span>|<span data-ttu-id="1d830-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1d830-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d830-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="1d830-109">attributeID</span></span>  <br/> |<span data-ttu-id="1d830-110">smallint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="1d830-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="1d830-111">Identificador del atributo.</span><span class="sxs-lookup"><span data-stu-id="1d830-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="1d830-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="1d830-112">attributeName</span></span>  <br/> |<span data-ttu-id="1d830-113">nvarchar (256), no es nulo</span><span class="sxs-lookup"><span data-stu-id="1d830-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="1d830-114">Nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="1d830-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="1d830-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="1d830-115">**Key**</span></span>

|<span data-ttu-id="1d830-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1d830-116">**Column**</span></span>|<span data-ttu-id="1d830-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1d830-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1d830-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="1d830-118">attributeID</span></span>  <br/> |<span data-ttu-id="1d830-119">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="1d830-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="1d830-120">**Valores de tabla**</span><span class="sxs-lookup"><span data-stu-id="1d830-120">**Table Values**</span></span>

|<span data-ttu-id="1d830-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="1d830-121">**attributeID**</span></span>|<span data-ttu-id="1d830-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="1d830-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1d830-123">1</span><span class="sxs-lookup"><span data-stu-id="1d830-123">1</span></span>  <br/> |<span data-ttu-id="1d830-124">Visibilidad.</span><span class="sxs-lookup"><span data-stu-id="1d830-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="1d830-125">2</span><span class="sxs-lookup"><span data-stu-id="1d830-125">2</span></span>  <br/> |<span data-ttu-id="1d830-126">Comportamiento.</span><span class="sxs-lookup"><span data-stu-id="1d830-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1d830-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d830-127">See also</span></span>

[<span data-ttu-id="1d830-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="1d830-128">tblNode</span></span>](tblnode.md)