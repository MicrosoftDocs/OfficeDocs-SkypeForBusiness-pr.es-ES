---
title: Tabla MediaList
ms.reviewer: ''
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
ms.openlocfilehash: 72ae6dbb145c3bb284f1090b01585591e4e773bf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877520"
---
# <a name="medialist-table"></a><span data-ttu-id="1a287-103">Tabla MediaList</span><span class="sxs-lookup"><span data-stu-id="1a287-103">MediaList table</span></span>
 
<span data-ttu-id="1a287-104">La tabla MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.</span><span class="sxs-lookup"><span data-stu-id="1a287-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="1a287-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1a287-105">**Column**</span></span>|<span data-ttu-id="1a287-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="1a287-106">**Data Type**</span></span>|<span data-ttu-id="1a287-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="1a287-107">**Key/Index**</span></span>|<span data-ttu-id="1a287-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="1a287-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1a287-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="1a287-109">**MediaId**</span></span> <br/> |<span data-ttu-id="1a287-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="1a287-110">tinyint</span></span>  <br/> |<span data-ttu-id="1a287-111">Primary</span><span class="sxs-lookup"><span data-stu-id="1a287-111">Primary</span></span>  <br/> |<span data-ttu-id="1a287-112">Valores: 1-7</span><span class="sxs-lookup"><span data-stu-id="1a287-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="1a287-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="1a287-113">**Media**</span></span> <br/> |<span data-ttu-id="1a287-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1a287-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="1a287-115">Asignación estática de los valores de MediaID y Media:</span><span class="sxs-lookup"><span data-stu-id="1a287-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="1a287-116">1 – MI</span><span class="sxs-lookup"><span data-stu-id="1a287-116">1 -- IM</span></span> <br/>  <span data-ttu-id="1a287-117">-2 transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="1a287-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="1a287-118">3 - asistencia remota</span><span class="sxs-lookup"><span data-stu-id="1a287-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="1a287-119">4 - uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="1a287-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="1a287-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="1a287-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="1a287-121">6 – Vídeo</span><span class="sxs-lookup"><span data-stu-id="1a287-121">6 -- Video</span></span> <br/>  <span data-ttu-id="1a287-122">7 - invitación a la aplicación</span><span class="sxs-lookup"><span data-stu-id="1a287-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="1a287-123">Si está intentando determinar el tipo de modalidad para los valores en LcsCDR.SessionDetailsView.MediaTypes, deberá usar el siguiente fragmento de código de JOIN. </span><span class="sxs-lookup"><span data-stu-id="1a287-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
