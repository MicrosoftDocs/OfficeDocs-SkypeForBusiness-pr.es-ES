---
title: Tabla AppliedBandwidthSource
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: En la tabla AppliedBandwidthSource es una tabla de apoyo. Cada registro representa una fuente.
ms.openlocfilehash: 49e4fd4b2c2543399d073d5d03e8cccad8b0038e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924853"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="dc0f8-104">Tabla AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="dc0f8-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="dc0f8-105">En la tabla AppliedBandwidthSource es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="dc0f8-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="dc0f8-106">Cada registro representa una fuente.</span><span class="sxs-lookup"><span data-stu-id="dc0f8-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="dc0f8-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="dc0f8-107">**Column**</span></span>|<span data-ttu-id="dc0f8-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="dc0f8-108">**Data Type**</span></span>|<span data-ttu-id="dc0f8-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="dc0f8-109">**Key/Index**</span></span>|<span data-ttu-id="dc0f8-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="dc0f8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dc0f8-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="dc0f8-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="dc0f8-112">int</span><span class="sxs-lookup"><span data-stu-id="dc0f8-112">int</span></span>  <br/> |<span data-ttu-id="dc0f8-113">Primary</span><span class="sxs-lookup"><span data-stu-id="dc0f8-113">Primary</span></span>  <br/> |<span data-ttu-id="dc0f8-114">Número único que identifica el origen.</span><span class="sxs-lookup"><span data-stu-id="dc0f8-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="dc0f8-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="dc0f8-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="dc0f8-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="dc0f8-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="dc0f8-117">Único</span><span class="sxs-lookup"><span data-stu-id="dc0f8-117">Unique</span></span>  <br/> |<span data-ttu-id="dc0f8-118">Éste es el origen de la punta de ancho de banda que se imponen.</span><span class="sxs-lookup"><span data-stu-id="dc0f8-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="dc0f8-119">Describe el límite de ancho de banda procedencia (por ejemplo, "Servidor de directivas de", "Activar el servidor" o "Modalidad").</span><span class="sxs-lookup"><span data-stu-id="dc0f8-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

