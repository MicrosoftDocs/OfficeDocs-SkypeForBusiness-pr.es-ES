---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList es la lista de complementos registrados que se pueden asociar con nodos.
ms.openlocfilehash: e5201fff31982da039d864adc4d29d900dbdcf99
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212386"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="061c2-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="061c2-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="061c2-104">tblSiopWhiteList es la lista de complementos registrados que se pueden asociar con nodos.</span><span class="sxs-lookup"><span data-stu-id="061c2-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="061c2-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="061c2-105">**Columns**</span></span>

|<span data-ttu-id="061c2-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="061c2-106">**Column**</span></span>|<span data-ttu-id="061c2-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="061c2-107">**Type**</span></span>|<span data-ttu-id="061c2-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="061c2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="061c2-109">siopID</span><span class="sxs-lookup"><span data-stu-id="061c2-109">siopID</span></span>  <br/> |<span data-ttu-id="061c2-110">GUID, no es nulo</span><span class="sxs-lookup"><span data-stu-id="061c2-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="061c2-111">GUID del complemento.</span><span class="sxs-lookup"><span data-stu-id="061c2-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="061c2-112">siopName</span><span class="sxs-lookup"><span data-stu-id="061c2-112">siopName</span></span>  <br/> |<span data-ttu-id="061c2-113">nvarchar (50), no es nulo</span><span class="sxs-lookup"><span data-stu-id="061c2-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="061c2-114">Nombre para mostrar del complemento.</span><span class="sxs-lookup"><span data-stu-id="061c2-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="061c2-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="061c2-115">siopUrl</span></span>  <br/> |<span data-ttu-id="061c2-116">nvarchar (255), no es nulo</span><span class="sxs-lookup"><span data-stu-id="061c2-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="061c2-117">Dirección URL del complemento.</span><span class="sxs-lookup"><span data-stu-id="061c2-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="061c2-118">**Clave**</span><span class="sxs-lookup"><span data-stu-id="061c2-118">**Key**</span></span>

|<span data-ttu-id="061c2-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="061c2-119">**Column**</span></span>|<span data-ttu-id="061c2-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="061c2-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="061c2-121">siopID</span><span class="sxs-lookup"><span data-stu-id="061c2-121">siopID</span></span>  <br/> |<span data-ttu-id="061c2-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="061c2-122">Primary key.</span></span>  <br/> |
   

