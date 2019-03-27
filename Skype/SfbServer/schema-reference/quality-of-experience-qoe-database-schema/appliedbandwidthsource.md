---
title: Tabla AppliedBandwidthSource
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: En la tabla AppliedBandwidthSource es una tabla de apoyo. Cada registro representa una fuente.
ms.openlocfilehash: 2fed25b6ca2218cb8b7300507b5c8258b2c29798
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899788"
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="91ed8-104">Tabla AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="91ed8-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="91ed8-105">En la tabla AppliedBandwidthSource es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="91ed8-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="91ed8-106">Cada registro representa una fuente.</span><span class="sxs-lookup"><span data-stu-id="91ed8-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="91ed8-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="91ed8-107">**Column**</span></span>|<span data-ttu-id="91ed8-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="91ed8-108">**Data Type**</span></span>|<span data-ttu-id="91ed8-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="91ed8-109">**Key/Index**</span></span>|<span data-ttu-id="91ed8-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="91ed8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="91ed8-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="91ed8-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="91ed8-112">int</span><span class="sxs-lookup"><span data-stu-id="91ed8-112">int</span></span>  <br/> |<span data-ttu-id="91ed8-113">Primary</span><span class="sxs-lookup"><span data-stu-id="91ed8-113">Primary</span></span>  <br/> |<span data-ttu-id="91ed8-114">Número único que identifica el origen.</span><span class="sxs-lookup"><span data-stu-id="91ed8-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="91ed8-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="91ed8-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="91ed8-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="91ed8-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="91ed8-117">Único</span><span class="sxs-lookup"><span data-stu-id="91ed8-117">Unique</span></span>  <br/> |<span data-ttu-id="91ed8-118">Éste es el origen de la punta de ancho de banda que se imponen.</span><span class="sxs-lookup"><span data-stu-id="91ed8-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="91ed8-119">Describe el límite de ancho de banda procedencia (por ejemplo, "Servidor de directivas de", "Activar el servidor" o "Modalidad").</span><span class="sxs-lookup"><span data-stu-id="91ed8-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

