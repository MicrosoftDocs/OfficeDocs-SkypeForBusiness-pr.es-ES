---
title: Tabla MediaList
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La tabla MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.
ms.openlocfilehash: b44a6dd8a4263f50cd187b6c4b154815e1e6350a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="medialist-table"></a><span data-ttu-id="d9bdc-103">Tabla MediaList</span><span class="sxs-lookup"><span data-stu-id="d9bdc-103">MediaList table</span></span>
 
<span data-ttu-id="d9bdc-104">La tabla MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.</span><span class="sxs-lookup"><span data-stu-id="d9bdc-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="d9bdc-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d9bdc-105">**Column**</span></span>|<span data-ttu-id="d9bdc-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d9bdc-106">**Data Type**</span></span>|<span data-ttu-id="d9bdc-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d9bdc-107">**Key/Index**</span></span>|<span data-ttu-id="d9bdc-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d9bdc-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d9bdc-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="d9bdc-109">**MediaId**</span></span> <br/> |<span data-ttu-id="d9bdc-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="d9bdc-110">tinyint</span></span>  <br/> |<span data-ttu-id="d9bdc-111">Primary</span><span class="sxs-lookup"><span data-stu-id="d9bdc-111">Primary</span></span>  <br/> |<span data-ttu-id="d9bdc-112">Valores: 1-7</span><span class="sxs-lookup"><span data-stu-id="d9bdc-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="d9bdc-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="d9bdc-113">**Media**</span></span> <br/> |<span data-ttu-id="d9bdc-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d9bdc-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="d9bdc-115">Asignación estática de los valores de MediaID y Media:</span><span class="sxs-lookup"><span data-stu-id="d9bdc-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="d9bdc-116">1 – MI</span><span class="sxs-lookup"><span data-stu-id="d9bdc-116">1 -- IM</span></span> <br/>  <span data-ttu-id="d9bdc-117">-2 transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="d9bdc-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="d9bdc-118">3 - asistencia remoto</span><span class="sxs-lookup"><span data-stu-id="d9bdc-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="d9bdc-119">4 - aplicaciones compartidas</span><span class="sxs-lookup"><span data-stu-id="d9bdc-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="d9bdc-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="d9bdc-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="d9bdc-121">6 – Vídeo</span><span class="sxs-lookup"><span data-stu-id="d9bdc-121">6 -- Video</span></span> <br/>  <span data-ttu-id="d9bdc-122">7 - app Invite</span><span class="sxs-lookup"><span data-stu-id="d9bdc-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="d9bdc-123">Si está intentando determinar el tipo de modalidad para los valores en LcsCDR.SessionDetailsView.MediaTypes, deberá usar el siguiente fragmento de código de JOIN. </span><span class="sxs-lookup"><span data-stu-id="d9bdc-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```


