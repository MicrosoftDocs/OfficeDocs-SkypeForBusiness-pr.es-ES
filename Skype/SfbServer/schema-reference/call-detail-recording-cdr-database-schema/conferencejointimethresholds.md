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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe Resumen de tiempo de combinación de conferencia. En el informe Resumen de tiempo de combinación de conferencia se resume la cantidad de tiempo necesario para que los usuarios se unan correctamente a una conferencia; Estos valores de hora se notifican como promedio y en una de las siguientes categorías:'
ms.openlocfilehash: 1874a94448be5957079b1c53944bc127df761e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815398"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e43bf-104">Tabla ConferenceJoinTimeThresholds en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="e43bf-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e43bf-105">La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe Resumen de tiempo de combinación de conferencia.</span><span class="sxs-lookup"><span data-stu-id="e43bf-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="e43bf-106">En el informe Resumen de tiempo de combinación de conferencia se resume la cantidad de tiempo necesario para que los usuarios se unan correctamente a una conferencia; Estos valores de hora se notifican como promedio y en una de las siguientes categorías:</span><span class="sxs-lookup"><span data-stu-id="e43bf-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="e43bf-107">Menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="e43bf-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="e43bf-108">Entre 2 y 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="e43bf-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="e43bf-109">Entre 5 segundos y 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="e43bf-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="e43bf-110">Más de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="e43bf-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="e43bf-111">La tabla ConferenceJoinTimeThresholds contiene los valores de clasificación de 2 segundos, 5 segundos y 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="e43bf-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="e43bf-112">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e43bf-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e43bf-113">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e43bf-113">**Column**</span></span>|<span data-ttu-id="e43bf-114">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e43bf-114">**Data Type**</span></span>|<span data-ttu-id="e43bf-115">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="e43bf-115">**Key/Index**</span></span>|<span data-ttu-id="e43bf-116">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="e43bf-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e43bf-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="e43bf-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="e43bf-118">int</span><span class="sxs-lookup"><span data-stu-id="e43bf-118">int</span></span>  <br/> |<span data-ttu-id="e43bf-119">Primary</span><span class="sxs-lookup"><span data-stu-id="e43bf-119">Primary</span></span>  <br/> |<span data-ttu-id="e43bf-120">Identificador único de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="e43bf-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="e43bf-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="e43bf-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="e43bf-122">int</span><span class="sxs-lookup"><span data-stu-id="e43bf-122">int</span></span>  <br/> || <span data-ttu-id="e43bf-123">Límite superior de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="e43bf-123">Upper limit for the classification.</span></span> <span data-ttu-id="e43bf-124">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="e43bf-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="e43bf-125">1</span><span class="sxs-lookup"><span data-stu-id="e43bf-125">2</span></span> <br/>  <span data-ttu-id="e43bf-126">5</span><span class="sxs-lookup"><span data-stu-id="e43bf-126">5</span></span> <br/>  <span data-ttu-id="e43bf-127">base10</span><span class="sxs-lookup"><span data-stu-id="e43bf-127">10</span></span> <br/> |
   

