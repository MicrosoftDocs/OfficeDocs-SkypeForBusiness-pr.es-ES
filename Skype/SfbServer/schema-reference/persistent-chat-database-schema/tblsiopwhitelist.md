---
title: tblSiopWhiteList
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList es la lista de complementos registrados que pueden asociarse con nodos.
ms.openlocfilehash: 0653ec7f4a663479f7b7d4787eee4dc0a1045aac
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="c30a4-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="c30a4-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="c30a4-104">tblSiopWhiteList es la lista de complementos registrados que pueden asociarse con nodos.</span><span class="sxs-lookup"><span data-stu-id="c30a4-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="c30a4-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="c30a4-105">**Columns**</span></span>

|<span data-ttu-id="c30a4-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c30a4-106">**Column**</span></span>|<span data-ttu-id="c30a4-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c30a4-107">**Type**</span></span>|<span data-ttu-id="c30a4-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c30a4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c30a4-109">siopID</span><span class="sxs-lookup"><span data-stu-id="c30a4-109">siopID</span></span>  <br/> |<span data-ttu-id="c30a4-110">GUID, no nulo</span><span class="sxs-lookup"><span data-stu-id="c30a4-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="c30a4-111">GUID del complemento.</span><span class="sxs-lookup"><span data-stu-id="c30a4-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="c30a4-112">siopName</span><span class="sxs-lookup"><span data-stu-id="c30a4-112">siopName</span></span>  <br/> |<span data-ttu-id="c30a4-113">nvarchar (50), no nulo</span><span class="sxs-lookup"><span data-stu-id="c30a4-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="c30a4-114">Nombre para mostrar del complemento.</span><span class="sxs-lookup"><span data-stu-id="c30a4-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="c30a4-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="c30a4-115">siopUrl</span></span>  <br/> |<span data-ttu-id="c30a4-116">nvarchar (255), no nulo</span><span class="sxs-lookup"><span data-stu-id="c30a4-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="c30a4-117">Dirección URL del complemento.</span><span class="sxs-lookup"><span data-stu-id="c30a4-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="c30a4-118">**Clave**</span><span class="sxs-lookup"><span data-stu-id="c30a4-118">**Key**</span></span>

|<span data-ttu-id="c30a4-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c30a4-119">**Column**</span></span>|<span data-ttu-id="c30a4-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="c30a4-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c30a4-121">siopID</span><span class="sxs-lookup"><span data-stu-id="c30a4-121">siopID</span></span>  <br/> |<span data-ttu-id="c30a4-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="c30a4-122">Primary key.</span></span>  <br/> |
   

