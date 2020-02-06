---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList es la lista de complementos registrados que se pueden asociar con nodos.
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812118"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="da95b-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="da95b-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="da95b-104">tblSiopWhiteList es la lista de complementos registrados que se pueden asociar con nodos.</span><span class="sxs-lookup"><span data-stu-id="da95b-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="da95b-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="da95b-105">**Columns**</span></span>

|<span data-ttu-id="da95b-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="da95b-106">**Column**</span></span>|<span data-ttu-id="da95b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="da95b-107">**Type**</span></span>|<span data-ttu-id="da95b-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="da95b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="da95b-109">siopID</span><span class="sxs-lookup"><span data-stu-id="da95b-109">siopID</span></span>  <br/> |<span data-ttu-id="da95b-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="da95b-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="da95b-111">GUID del complemento.</span><span class="sxs-lookup"><span data-stu-id="da95b-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="da95b-112">siopName</span><span class="sxs-lookup"><span data-stu-id="da95b-112">siopName</span></span>  <br/> |<span data-ttu-id="da95b-113">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="da95b-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="da95b-114">Display: nombre del complemento.</span><span class="sxs-lookup"><span data-stu-id="da95b-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="da95b-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="da95b-115">siopUrl</span></span>  <br/> |<span data-ttu-id="da95b-116">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="da95b-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="da95b-117">Dirección URL del complemento.</span><span class="sxs-lookup"><span data-stu-id="da95b-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="da95b-118">**Clave**</span><span class="sxs-lookup"><span data-stu-id="da95b-118">**Key**</span></span>

|<span data-ttu-id="da95b-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="da95b-119">**Column**</span></span>|<span data-ttu-id="da95b-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="da95b-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="da95b-121">siopID</span><span class="sxs-lookup"><span data-stu-id="da95b-121">siopID</span></span>  <br/> |<span data-ttu-id="da95b-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="da95b-122">Primary key.</span></span>  <br/> |
   

