---
title: Tabla MediaList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La tabla MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.
ms.openlocfilehash: 243fd3fb705826584f4e786441cdc1faa9075777
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992930"
---
# <a name="medialist-table"></a><span data-ttu-id="ee4ad-103">Tabla MediaList</span><span class="sxs-lookup"><span data-stu-id="ee4ad-103">MediaList table</span></span>
 
<span data-ttu-id="ee4ad-104">La tabla MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.</span><span class="sxs-lookup"><span data-stu-id="ee4ad-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="ee4ad-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ee4ad-105">**Column**</span></span>|<span data-ttu-id="ee4ad-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ee4ad-106">**Data Type**</span></span>|<span data-ttu-id="ee4ad-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="ee4ad-107">**Key/Index**</span></span>|<span data-ttu-id="ee4ad-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ee4ad-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ee4ad-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="ee4ad-109">**MediaId**</span></span> <br/> |<span data-ttu-id="ee4ad-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="ee4ad-110">tinyint</span></span>  <br/> |<span data-ttu-id="ee4ad-111">Primary</span><span class="sxs-lookup"><span data-stu-id="ee4ad-111">Primary</span></span>  <br/> |<span data-ttu-id="ee4ad-112">Valores: 1-7</span><span class="sxs-lookup"><span data-stu-id="ee4ad-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="ee4ad-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="ee4ad-113">**Media**</span></span> <br/> |<span data-ttu-id="ee4ad-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ee4ad-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="ee4ad-115">Asignación estática de los valores de MediaID y Media:</span><span class="sxs-lookup"><span data-stu-id="ee4ad-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="ee4ad-116">1 – MI</span><span class="sxs-lookup"><span data-stu-id="ee4ad-116">1 -- IM</span></span> <br/>  <span data-ttu-id="ee4ad-117">2-transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="ee4ad-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="ee4ad-118">3-asistencia remota</span><span class="sxs-lookup"><span data-stu-id="ee4ad-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="ee4ad-119">4-uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ee4ad-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="ee4ad-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="ee4ad-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="ee4ad-121">6 – Vídeo</span><span class="sxs-lookup"><span data-stu-id="ee4ad-121">6 -- Video</span></span> <br/>  <span data-ttu-id="ee4ad-122">7-invitación a la aplicación</span><span class="sxs-lookup"><span data-stu-id="ee4ad-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="ee4ad-123">Si está intentando determinar el tipo de modalidad para los valores en LcsCDR.SessionDetailsView.MediaTypes, deberá usar el siguiente fragmento de código de JOIN. </span><span class="sxs-lookup"><span data-stu-id="ee4ad-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```json
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
