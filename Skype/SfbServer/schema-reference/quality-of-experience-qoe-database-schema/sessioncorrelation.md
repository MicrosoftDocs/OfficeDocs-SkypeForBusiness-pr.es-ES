---
title: Tabla SessionCorrelation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabla SessionCorrelation es una tabla de soporte. Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones.
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294659"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="85049-104">Tabla SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="85049-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="85049-105">La tabla SessionCorrelation es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="85049-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="85049-106">Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="85049-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="85049-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="85049-107">**Column**</span></span>|<span data-ttu-id="85049-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="85049-108">**Data Type**</span></span>|<span data-ttu-id="85049-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="85049-109">**Key/Index**</span></span>|<span data-ttu-id="85049-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="85049-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="85049-111">**Comprobación**</span><span class="sxs-lookup"><span data-stu-id="85049-111">**Checksum**</span></span> <br/> |<span data-ttu-id="85049-112">int</span><span class="sxs-lookup"><span data-stu-id="85049-112">int</span></span>  <br/> |||
|<span data-ttu-id="85049-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="85049-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="85049-114">int</span><span class="sxs-lookup"><span data-stu-id="85049-114">int</span></span>  <br/> |<span data-ttu-id="85049-115">Primary</span><span class="sxs-lookup"><span data-stu-id="85049-115">Primary</span></span>  <br/> |<span data-ttu-id="85049-116">Número único que identifica este servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="85049-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="85049-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="85049-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="85049-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="85049-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="85049-119">Solo</span><span class="sxs-lookup"><span data-stu-id="85049-119">Unique</span></span>  <br/> |<span data-ttu-id="85049-120">Las sesiones correlacionadas tendrán el mismo identificador de correlación.</span><span class="sxs-lookup"><span data-stu-id="85049-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="85049-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="85049-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="85049-122">datetime</span><span class="sxs-lookup"><span data-stu-id="85049-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="85049-123">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="85049-123">For internal use only.</span></span>  <br/> |
   

