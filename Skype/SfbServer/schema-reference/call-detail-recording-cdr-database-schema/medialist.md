---
title: Tabla MediaList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La tabla MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.
ms.openlocfilehash: 3eaa40cb5ae03129edaa36effa7b40012fc38429
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930654"
---
# <a name="medialist-table"></a><span data-ttu-id="3bb63-103">Tabla MediaList</span><span class="sxs-lookup"><span data-stu-id="3bb63-103">MediaList table</span></span>
 
<span data-ttu-id="3bb63-104">La tabla MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.</span><span class="sxs-lookup"><span data-stu-id="3bb63-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="3bb63-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3bb63-105">**Column**</span></span>|<span data-ttu-id="3bb63-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="3bb63-106">**Data Type**</span></span>|<span data-ttu-id="3bb63-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="3bb63-107">**Key/Index**</span></span>|<span data-ttu-id="3bb63-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="3bb63-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3bb63-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="3bb63-109">**MediaId**</span></span> <br/> |<span data-ttu-id="3bb63-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="3bb63-110">tinyint</span></span>  <br/> |<span data-ttu-id="3bb63-111">Primary</span><span class="sxs-lookup"><span data-stu-id="3bb63-111">Primary</span></span>  <br/> |<span data-ttu-id="3bb63-112">Valores: 1-7</span><span class="sxs-lookup"><span data-stu-id="3bb63-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="3bb63-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="3bb63-113">**Media**</span></span> <br/> |<span data-ttu-id="3bb63-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3bb63-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="3bb63-115">Asignación estática de los valores de MediaID y Media:</span><span class="sxs-lookup"><span data-stu-id="3bb63-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="3bb63-116">1 – MI</span><span class="sxs-lookup"><span data-stu-id="3bb63-116">1 -- IM</span></span> <br/>  <span data-ttu-id="3bb63-117">-2 transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="3bb63-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="3bb63-118">3 - asistencia remota</span><span class="sxs-lookup"><span data-stu-id="3bb63-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="3bb63-119">4 - uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="3bb63-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="3bb63-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="3bb63-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="3bb63-121">6 – Vídeo</span><span class="sxs-lookup"><span data-stu-id="3bb63-121">6 -- Video</span></span> <br/>  <span data-ttu-id="3bb63-122">7 - invitación a la aplicación</span><span class="sxs-lookup"><span data-stu-id="3bb63-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="3bb63-123">Si está intentando determinar el tipo de modalidad para los valores en LcsCDR.SessionDetailsView.MediaTypes, deberá usar el siguiente fragmento de código de JOIN. </span><span class="sxs-lookup"><span data-stu-id="3bb63-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
