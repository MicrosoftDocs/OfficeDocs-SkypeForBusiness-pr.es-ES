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
# <a name="sessioncorrelation-table"></a><span data-ttu-id="4271e-104">Tabla SessionCorrelation</span><span class="sxs-lookup"><span data-stu-id="4271e-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="4271e-105">La tabla SessionCorrelation es una tabla compatible.</span><span class="sxs-lookup"><span data-stu-id="4271e-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="4271e-106">Cada registro representa un CorrelationID que se usa para correlacionar varias sesiones.</span><span class="sxs-lookup"><span data-stu-id="4271e-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="4271e-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="4271e-107">**Column**</span></span>|<span data-ttu-id="4271e-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="4271e-108">**Data Type**</span></span>|<span data-ttu-id="4271e-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="4271e-109">**Key/Index**</span></span>|<span data-ttu-id="4271e-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="4271e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4271e-111">**Suma de comprobación**</span><span class="sxs-lookup"><span data-stu-id="4271e-111">**Checksum**</span></span> <br/> |<span data-ttu-id="4271e-112">entero</span><span class="sxs-lookup"><span data-stu-id="4271e-112">int</span></span>  <br/> |||
|<span data-ttu-id="4271e-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="4271e-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="4271e-114">entero</span><span class="sxs-lookup"><span data-stu-id="4271e-114">int</span></span>  <br/> |<span data-ttu-id="4271e-115">Principal</span><span class="sxs-lookup"><span data-stu-id="4271e-115">Primary</span></span>  <br/> |<span data-ttu-id="4271e-116">Número único que identifica este servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="4271e-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="4271e-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="4271e-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="4271e-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4271e-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4271e-119">Única</span><span class="sxs-lookup"><span data-stu-id="4271e-119">Unique</span></span>  <br/> |<span data-ttu-id="4271e-120">Las sesiones correlacionadas tendrán el mismo identificador de correlación.</span><span class="sxs-lookup"><span data-stu-id="4271e-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="4271e-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="4271e-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="4271e-122">datetime</span><span class="sxs-lookup"><span data-stu-id="4271e-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="4271e-123">Únicamente para uso interno.</span><span class="sxs-lookup"><span data-stu-id="4271e-123">For internal use only.</span></span>  <br/> |
   

