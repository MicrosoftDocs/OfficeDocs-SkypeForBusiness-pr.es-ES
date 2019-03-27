---
title: Tabla taba en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación utilizados por el informe de resumen de tiempo unirse a conferencia. El informe de resumen de tiempo de unirse a conferencia resume la cantidad de tiempo necesario para que los usuarios correctamente unirse a una conferencia; Estos valores de tiempo se notifican como una media y en una de las siguientes categorías:'
ms.openlocfilehash: d6fbae0d077719782b3e93c0fe008ee35ce3370e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895820"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="285cc-104">Tabla taba en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="285cc-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="285cc-105">La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación utilizados por el informe de resumen de tiempo unirse a conferencia.</span><span class="sxs-lookup"><span data-stu-id="285cc-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="285cc-106">El informe de resumen de tiempo de unirse a conferencia resume la cantidad de tiempo necesario para que los usuarios correctamente unirse a una conferencia; Estos valores de tiempo se notifican como una media y en una de las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="285cc-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="285cc-107">Menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="285cc-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="285cc-108">Entre 2 y 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="285cc-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="285cc-109">Entre 5 y 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="285cc-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="285cc-110">Más de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="285cc-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="285cc-111">La tabla ConferenceJoinTimeThresholds contiene los valores de clasificación 2 segundos, 5 segundos y 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="285cc-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="285cc-112">En esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="285cc-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="285cc-113">**Columna**</span><span class="sxs-lookup"><span data-stu-id="285cc-113">**Column**</span></span>|<span data-ttu-id="285cc-114">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="285cc-114">**Data Type**</span></span>|<span data-ttu-id="285cc-115">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="285cc-115">**Key/Index**</span></span>|<span data-ttu-id="285cc-116">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="285cc-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="285cc-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="285cc-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="285cc-118">int</span><span class="sxs-lookup"><span data-stu-id="285cc-118">int</span></span>  <br/> |<span data-ttu-id="285cc-119">Primary</span><span class="sxs-lookup"><span data-stu-id="285cc-119">Primary</span></span>  <br/> |<span data-ttu-id="285cc-120">Identificador único para la clasificación.</span><span class="sxs-lookup"><span data-stu-id="285cc-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="285cc-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="285cc-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="285cc-122">int</span><span class="sxs-lookup"><span data-stu-id="285cc-122">int</span></span>  <br/> || <span data-ttu-id="285cc-123">Límite superior para la clasificación.</span><span class="sxs-lookup"><span data-stu-id="285cc-123">Upper limit for the classification.</span></span> <span data-ttu-id="285cc-124">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="285cc-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="285cc-125">2</span><span class="sxs-lookup"><span data-stu-id="285cc-125">2</span></span> <br/>  <span data-ttu-id="285cc-126">5</span><span class="sxs-lookup"><span data-stu-id="285cc-126">5</span></span> <br/>  <span data-ttu-id="285cc-127">10</span><span class="sxs-lookup"><span data-stu-id="285cc-127">10</span></span> <br/> |
   

