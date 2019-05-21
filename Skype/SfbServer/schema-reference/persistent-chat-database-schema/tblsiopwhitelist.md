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
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList es la lista de complementos registrados que se pueden asociar con nodos.
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295177"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="23c43-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="23c43-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="23c43-104">tblSiopWhiteList es la lista de complementos registrados que se pueden asociar con nodos.</span><span class="sxs-lookup"><span data-stu-id="23c43-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="23c43-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="23c43-105">**Columns**</span></span>

|<span data-ttu-id="23c43-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="23c43-106">**Column**</span></span>|<span data-ttu-id="23c43-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="23c43-107">**Type**</span></span>|<span data-ttu-id="23c43-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="23c43-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="23c43-109">siopID</span><span class="sxs-lookup"><span data-stu-id="23c43-109">siopID</span></span>  <br/> |<span data-ttu-id="23c43-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="23c43-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="23c43-111">GUID del complemento.</span><span class="sxs-lookup"><span data-stu-id="23c43-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="23c43-112">siopName</span><span class="sxs-lookup"><span data-stu-id="23c43-112">siopName</span></span>  <br/> |<span data-ttu-id="23c43-113">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="23c43-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="23c43-114">Display: nombre del complemento.</span><span class="sxs-lookup"><span data-stu-id="23c43-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="23c43-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="23c43-115">siopUrl</span></span>  <br/> |<span data-ttu-id="23c43-116">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="23c43-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="23c43-117">Dirección URL del complemento.</span><span class="sxs-lookup"><span data-stu-id="23c43-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="23c43-118">**Clave**</span><span class="sxs-lookup"><span data-stu-id="23c43-118">**Key**</span></span>

|<span data-ttu-id="23c43-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="23c43-119">**Column**</span></span>|<span data-ttu-id="23c43-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="23c43-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23c43-121">siopID</span><span class="sxs-lookup"><span data-stu-id="23c43-121">siopID</span></span>  <br/> |<span data-ttu-id="23c43-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="23c43-122">Primary key.</span></span>  <br/> |
   

