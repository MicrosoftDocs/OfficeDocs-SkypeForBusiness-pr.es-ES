---
title: Tabla AppliedBandwidthSource
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La tabla AppliedBandwidthSource es un auxiliar. Cada registro representa una sola fuente.
ms.openlocfilehash: e15df92423a3408e3cb8ae40a0788e1f165961df
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="appliedbandwidthsource-table"></a><span data-ttu-id="7649c-104">Tabla AppliedBandwidthSource</span><span class="sxs-lookup"><span data-stu-id="7649c-104">AppliedBandwidthSource table</span></span>
 
<span data-ttu-id="7649c-105">La tabla AppliedBandwidthSource es un auxiliar.</span><span class="sxs-lookup"><span data-stu-id="7649c-105">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="7649c-106">Cada registro representa una sola fuente.</span><span class="sxs-lookup"><span data-stu-id="7649c-106">Each record represents one source.</span></span>
  
|<span data-ttu-id="7649c-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7649c-107">**Column**</span></span>|<span data-ttu-id="7649c-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="7649c-108">**Data Type**</span></span>|<span data-ttu-id="7649c-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="7649c-109">**Key/Index**</span></span>|<span data-ttu-id="7649c-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="7649c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7649c-111">**AppliedBandwidthSourceKey**</span><span class="sxs-lookup"><span data-stu-id="7649c-111">**AppliedBandwidthSourceKey**</span></span> <br/> |<span data-ttu-id="7649c-112">int</span><span class="sxs-lookup"><span data-stu-id="7649c-112">int</span></span>  <br/> |<span data-ttu-id="7649c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7649c-113">Primary</span></span>  <br/> |<span data-ttu-id="7649c-114">Número único que identifica el origen.</span><span class="sxs-lookup"><span data-stu-id="7649c-114">Unique number identifying the source.</span></span>  <br/> |
|<span data-ttu-id="7649c-115">**AppliedBandwidthSource**</span><span class="sxs-lookup"><span data-stu-id="7649c-115">**AppliedBandwidthSource**</span></span> <br/> |<span data-ttu-id="7649c-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7649c-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="7649c-117">Único</span><span class="sxs-lookup"><span data-stu-id="7649c-117">Unique</span></span>  <br/> |<span data-ttu-id="7649c-118">Éste es el origen de la tapa del ancho de banda que se impuso.</span><span class="sxs-lookup"><span data-stu-id="7649c-118">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="7649c-119">Describe el límite de ancho de banda procedencia (por ejemplo, "Servidor de directivas", "Apagar el servidor" o "Modalidad").</span><span class="sxs-lookup"><span data-stu-id="7649c-119">It describes where the bandwidth limit is coming from (for example, "Policy Server", "TURN Server", or "Modality").</span></span>  <br/> |
   

