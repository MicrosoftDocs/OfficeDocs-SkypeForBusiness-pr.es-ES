---
title: Tabla SessionCorrelation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: En la tabla SessionCorrelation es una tabla de apoyo. Cada registro representa una CorrelationID que se usa para correlacionar varias sesiones.
ms.openlocfilehash: 4efd1aeba45fb12aee646c401f492450f375aa20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907083"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="08880-104">Tabla SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="08880-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="08880-105">En la tabla SessionCorrelation es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="08880-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="08880-106">Cada registro representa una CorrelationID que se usa para correlacionar varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="08880-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="08880-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="08880-107">**Column**</span></span>|<span data-ttu-id="08880-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="08880-108">**Data Type**</span></span>|<span data-ttu-id="08880-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="08880-109">**Key/Index**</span></span>|<span data-ttu-id="08880-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="08880-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="08880-111">**Suma de comprobación**</span><span class="sxs-lookup"><span data-stu-id="08880-111">**Checksum**</span></span> <br/> |<span data-ttu-id="08880-112">int</span><span class="sxs-lookup"><span data-stu-id="08880-112">int</span></span>  <br/> |||
|<span data-ttu-id="08880-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="08880-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="08880-114">int</span><span class="sxs-lookup"><span data-stu-id="08880-114">int</span></span>  <br/> |<span data-ttu-id="08880-115">Primary</span><span class="sxs-lookup"><span data-stu-id="08880-115">Primary</span></span>  <br/> |<span data-ttu-id="08880-116">Número único que identifica este / servidor de conferencia A/v.</span><span class="sxs-lookup"><span data-stu-id="08880-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="08880-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="08880-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="08880-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="08880-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="08880-119">Único</span><span class="sxs-lookup"><span data-stu-id="08880-119">Unique</span></span>  <br/> |<span data-ttu-id="08880-120">Las sesiones correlacionadas tendrán el mismo identificador de correlación.</span><span class="sxs-lookup"><span data-stu-id="08880-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="08880-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="08880-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="08880-122">datetime</span><span class="sxs-lookup"><span data-stu-id="08880-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="08880-123">Sólo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="08880-123">For internal use only.</span></span>  <br/> |
   

