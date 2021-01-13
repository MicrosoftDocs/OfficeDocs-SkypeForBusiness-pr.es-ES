---
title: Tabla ConferenceJoinTimeThresholds en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe de resumen de hora de incorporación a la conferencia. El informe de resumen de hora de incorporación a la conferencia resume el tiempo que necesitaron los usuarios para unirse a la conferencia. Estos valores de tiempo se registran como promedio y en una de las categorías siguientes:'
ms.openlocfilehash: dfa7293307376b5fb5c86cec6f7504d363b005f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813310"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4850a-104">Tabla ConferenceJoinTimeThresholds en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="4850a-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4850a-p102">La tabla ConferenceJoinTimeThresholds contiene los límites de clasificación usados por el informe de resumen de hora de incorporación a la conferencia. El informe de resumen de hora de incorporación a la conferencia resume el tiempo que necesitaron los usuarios para unirse a la conferencia. Estos valores de tiempo se registran como promedio y en una de las categorías siguientes:</span><span class="sxs-lookup"><span data-stu-id="4850a-p102">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="4850a-107">Menos de 2 segundos.</span><span class="sxs-lookup"><span data-stu-id="4850a-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="4850a-108">Entre 2 y 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="4850a-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="4850a-109">Entre 5 y 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="4850a-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="4850a-110">Más de 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="4850a-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="4850a-111">La tabla ConferenceJoinTimeThresholds contiene los valores de clasificación 2 segundos, 5 segundos y 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="4850a-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="4850a-112">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4850a-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4850a-113">**Columna**</span><span class="sxs-lookup"><span data-stu-id="4850a-113">**Column**</span></span>|<span data-ttu-id="4850a-114">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="4850a-114">**Data Type**</span></span>|<span data-ttu-id="4850a-115">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="4850a-115">**Key/Index**</span></span>|<span data-ttu-id="4850a-116">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="4850a-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4850a-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="4850a-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="4850a-118">entero</span><span class="sxs-lookup"><span data-stu-id="4850a-118">int</span></span>  <br/> |<span data-ttu-id="4850a-119">Principal</span><span class="sxs-lookup"><span data-stu-id="4850a-119">Primary</span></span>  <br/> |<span data-ttu-id="4850a-120">Identificador único de la clasificación.</span><span class="sxs-lookup"><span data-stu-id="4850a-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="4850a-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="4850a-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="4850a-122">entero</span><span class="sxs-lookup"><span data-stu-id="4850a-122">int</span></span>  <br/> || <span data-ttu-id="4850a-p103">Límite máximo de la clasificación. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="4850a-p103">Upper limit for the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="4850a-125">2 </span><span class="sxs-lookup"><span data-stu-id="4850a-125">2</span></span> <br/>  <span data-ttu-id="4850a-126">5 </span><span class="sxs-lookup"><span data-stu-id="4850a-126">5</span></span> <br/>  <span data-ttu-id="4850a-127">10 </span><span class="sxs-lookup"><span data-stu-id="4850a-127">10</span></span> <br/> |
   

