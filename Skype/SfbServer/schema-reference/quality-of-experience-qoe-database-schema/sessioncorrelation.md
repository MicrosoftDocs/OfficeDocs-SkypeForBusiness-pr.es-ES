---
title: Tabla SessionCorrelation
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: La tabla SessionCorrelation es una tabla compatible. Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones.
ms.openlocfilehash: 36b617517f3642a2150c72369db858eee62a4a87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802660"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="0b518-104">Tabla SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="0b518-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="0b518-105">La tabla SessionCorrelation es una tabla compatible.</span><span class="sxs-lookup"><span data-stu-id="0b518-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="0b518-106">Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="0b518-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="0b518-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0b518-107">**Column**</span></span>|<span data-ttu-id="0b518-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0b518-108">**Data Type**</span></span>|<span data-ttu-id="0b518-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="0b518-109">**Key/Index**</span></span>|<span data-ttu-id="0b518-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="0b518-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0b518-111">**Suma de comprobación**</span><span class="sxs-lookup"><span data-stu-id="0b518-111">**Checksum**</span></span> <br/> |<span data-ttu-id="0b518-112">entero</span><span class="sxs-lookup"><span data-stu-id="0b518-112">int</span></span>  <br/> |||
|<span data-ttu-id="0b518-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="0b518-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="0b518-114">entero</span><span class="sxs-lookup"><span data-stu-id="0b518-114">int</span></span>  <br/> |<span data-ttu-id="0b518-115">Principal</span><span class="sxs-lookup"><span data-stu-id="0b518-115">Primary</span></span>  <br/> |<span data-ttu-id="0b518-116">Número único que identifica este servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="0b518-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="0b518-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="0b518-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="0b518-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0b518-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0b518-119">Única</span><span class="sxs-lookup"><span data-stu-id="0b518-119">Unique</span></span>  <br/> |<span data-ttu-id="0b518-120">Las sesiones correlacionadas tendrán el mismo identificador de correlación.</span><span class="sxs-lookup"><span data-stu-id="0b518-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="0b518-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="0b518-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="0b518-122">datetime</span><span class="sxs-lookup"><span data-stu-id="0b518-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="0b518-123">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="0b518-123">For internal use only.</span></span>  <br/> |
   

