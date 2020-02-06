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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabla SessionCorrelation es una tabla de soporte. Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones.
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805748"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="9a78e-104">Tabla SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="9a78e-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="9a78e-105">La tabla SessionCorrelation es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="9a78e-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="9a78e-106">Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="9a78e-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="9a78e-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9a78e-107">**Column**</span></span>|<span data-ttu-id="9a78e-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9a78e-108">**Data Type**</span></span>|<span data-ttu-id="9a78e-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="9a78e-109">**Key/Index**</span></span>|<span data-ttu-id="9a78e-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="9a78e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9a78e-111">**Comprobación**</span><span class="sxs-lookup"><span data-stu-id="9a78e-111">**Checksum**</span></span> <br/> |<span data-ttu-id="9a78e-112">int</span><span class="sxs-lookup"><span data-stu-id="9a78e-112">int</span></span>  <br/> |||
|<span data-ttu-id="9a78e-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="9a78e-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="9a78e-114">int</span><span class="sxs-lookup"><span data-stu-id="9a78e-114">int</span></span>  <br/> |<span data-ttu-id="9a78e-115">Primary</span><span class="sxs-lookup"><span data-stu-id="9a78e-115">Primary</span></span>  <br/> |<span data-ttu-id="9a78e-116">Número único que identifica este servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="9a78e-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="9a78e-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="9a78e-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="9a78e-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9a78e-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9a78e-119">Solo</span><span class="sxs-lookup"><span data-stu-id="9a78e-119">Unique</span></span>  <br/> |<span data-ttu-id="9a78e-120">Las sesiones correlacionadas tendrán el mismo identificador de correlación.</span><span class="sxs-lookup"><span data-stu-id="9a78e-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="9a78e-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="9a78e-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="9a78e-122">datetime</span><span class="sxs-lookup"><span data-stu-id="9a78e-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="9a78e-123">Solo para uso interno.</span><span class="sxs-lookup"><span data-stu-id="9a78e-123">For internal use only.</span></span>  <br/> |
   

