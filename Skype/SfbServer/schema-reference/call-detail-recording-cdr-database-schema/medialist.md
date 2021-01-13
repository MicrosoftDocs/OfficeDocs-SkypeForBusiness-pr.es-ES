---
title: Tabla MediaList
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: La lista MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.
ms.openlocfilehash: 6f593876a1b42163b6f2e75dbe44c1eb26b2ff16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813140"
---
# <a name="medialist-table"></a><span data-ttu-id="2e76b-103">Tabla MediaList</span><span class="sxs-lookup"><span data-stu-id="2e76b-103">MediaList table</span></span>
 
<span data-ttu-id="2e76b-104">La lista MediaList es una tabla estática que almacena la lista de los diferentes tipos de medios.</span><span class="sxs-lookup"><span data-stu-id="2e76b-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="2e76b-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2e76b-105">**Column**</span></span>|<span data-ttu-id="2e76b-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="2e76b-106">**Data Type**</span></span>|<span data-ttu-id="2e76b-107">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="2e76b-107">**Key/Index**</span></span>|<span data-ttu-id="2e76b-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="2e76b-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2e76b-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="2e76b-109">**MediaId**</span></span> <br/> |<span data-ttu-id="2e76b-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="2e76b-110">tinyint</span></span>  <br/> |<span data-ttu-id="2e76b-111">Principal</span><span class="sxs-lookup"><span data-stu-id="2e76b-111">Primary</span></span>  <br/> |<span data-ttu-id="2e76b-112">Valores: 1-7</span><span class="sxs-lookup"><span data-stu-id="2e76b-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="2e76b-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="2e76b-113">**Media**</span></span> <br/> |<span data-ttu-id="2e76b-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2e76b-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="2e76b-115">Asignación estática de valores MediaID y Media:</span><span class="sxs-lookup"><span data-stu-id="2e76b-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="2e76b-116">1 -- MI</span><span class="sxs-lookup"><span data-stu-id="2e76b-116">1 -- IM</span></span> <br/>  <span data-ttu-id="2e76b-117">2- Transferencia de archivos</span><span class="sxs-lookup"><span data-stu-id="2e76b-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="2e76b-118">3- Asistencia remota</span><span class="sxs-lookup"><span data-stu-id="2e76b-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="2e76b-119">4- Uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="2e76b-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="2e76b-120">5 -- Audio</span><span class="sxs-lookup"><span data-stu-id="2e76b-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="2e76b-121">6 -- Vídeo</span><span class="sxs-lookup"><span data-stu-id="2e76b-121">6 -- Video</span></span> <br/>  <span data-ttu-id="2e76b-122">7- Invitación de aplicación</span><span class="sxs-lookup"><span data-stu-id="2e76b-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="2e76b-123">Si está intentando determinar el tipo de modalidad para los valores de LcsCDR.SessionDetailsView.MediaTypes, debe usar el siguiente fragmento de código join:</span><span class="sxs-lookup"><span data-stu-id="2e76b-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
