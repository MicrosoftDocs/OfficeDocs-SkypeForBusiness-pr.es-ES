---
title: Tabla NetworkConnectionDetail
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La tabla NetworkConnectionDetail asigna los tipos de conexión de red a los identificadores de conexión de red utilizados en la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: cc1eb91d3c633ed9455a0476b613430dfa8e3d6b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="b8850-104">Tabla NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="b8850-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="b8850-105">La tabla NetworkConnectionDetail asigna los tipos de conexión de red a los identificadores de conexión de red utilizados en la base de datos de calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="b8850-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="b8850-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b8850-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b8850-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b8850-107">**Column**</span></span>|<span data-ttu-id="b8850-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="b8850-108">**Data Type**</span></span>|<span data-ttu-id="b8850-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="b8850-109">**Key/Index**</span></span>|<span data-ttu-id="b8850-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="b8850-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b8850-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="b8850-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="b8850-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="b8850-112">tinyint</span></span>  <br/> |<span data-ttu-id="b8850-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b8850-113">Primary</span></span>  <br/> |<span data-ttu-id="b8850-114">Identificador único para el tipo de conexión de red.</span><span class="sxs-lookup"><span data-stu-id="b8850-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="b8850-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="b8850-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="b8850-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="b8850-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="b8850-117">Único</span><span class="sxs-lookup"><span data-stu-id="b8850-117">Unique</span></span>  <br/> |<span data-ttu-id="b8850-118">Tipo de conexión de red que corresponde a la NetworkConnectionDetailKey.</span><span class="sxs-lookup"><span data-stu-id="b8850-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="b8850-119">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="b8850-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="b8850-120">0--con cable</span><span class="sxs-lookup"><span data-stu-id="b8850-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="b8850-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="b8850-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="b8850-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="b8850-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="b8850-123">3--MobileBB</span><span class="sxs-lookup"><span data-stu-id="b8850-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="b8850-124">4--los demás</span><span class="sxs-lookup"><span data-stu-id="b8850-124">4 -- Other</span></span>  <br/> <span data-ttu-id="b8850-125">5: túnel</span><span class="sxs-lookup"><span data-stu-id="b8850-125">5 -- Tunnel</span></span>  <br/> |
   

