---
title: Tabla ConferenceJoinTimeThresholds en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe Resumen de tiempo de combinación de conferencia. En el informe Resumen de tiempo de combinación de conferencia se resume la cantidad de tiempo necesario para que los usuarios se unan correctamente a una conferencia; Estos valores de hora se notifican como promedio y en una de las siguientes categorías:'
ms.openlocfilehash: 4b2f27b6ab826ff95c1478cf54e8a21c148b1d3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296500"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5de78-104">Tabla ConferenceJoinTimeThresholds en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="5de78-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5de78-105">La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe Resumen de tiempo de combinación de conferencia.</span><span class="sxs-lookup"><span data-stu-id="5de78-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="5de78-106">En el informe Resumen de tiempo de combinación de conferencia se resume la cantidad de tiempo necesario para que los usuarios se unan correctamente a una conferencia; Estos valores de hora se notifican como promedio y en una de las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="5de78-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="5de78-107">Menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="5de78-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="5de78-108">Entre 2 y 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="5de78-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="5de78-109">Entre 5 segundos y 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="5de78-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="5de78-110">Más de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="5de78-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="5de78-111">La tabla ConferenceJoinTimeThresholds contiene los valores de clasificación de 2 segundos, 5 segundos y 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="5de78-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="5de78-112">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5de78-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5de78-113">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5de78-113">**Column**</span></span>|<span data-ttu-id="5de78-114">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="5de78-114">**Data Type**</span></span>|<span data-ttu-id="5de78-115">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="5de78-115">**Key/Index**</span></span>|<span data-ttu-id="5de78-116">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="5de78-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5de78-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="5de78-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="5de78-118">int</span><span class="sxs-lookup"><span data-stu-id="5de78-118">int</span></span>  <br/> |<span data-ttu-id="5de78-119">Primary</span><span class="sxs-lookup"><span data-stu-id="5de78-119">Primary</span></span>  <br/> |<span data-ttu-id="5de78-120">Identificador único de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="5de78-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="5de78-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="5de78-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="5de78-122">int</span><span class="sxs-lookup"><span data-stu-id="5de78-122">int</span></span>  <br/> || <span data-ttu-id="5de78-123">Límite superior de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="5de78-123">Upper limit for the classification.</span></span> <span data-ttu-id="5de78-124">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="5de78-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="5de78-125">2</span><span class="sxs-lookup"><span data-stu-id="5de78-125">2</span></span> <br/>  <span data-ttu-id="5de78-126">5</span><span class="sxs-lookup"><span data-stu-id="5de78-126">5</span></span> <br/>  <span data-ttu-id="5de78-127">base10</span><span class="sxs-lookup"><span data-stu-id="5de78-127">10</span></span> <br/> |
   

