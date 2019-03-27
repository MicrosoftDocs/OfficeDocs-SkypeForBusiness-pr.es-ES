---
title: Tabla NetworkConnectionDetail
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: En la tabla NetworkConnectionDetail asigna tipos de conexión de red a los identificadores de conexión de red que se usan en la base de datos de calidad de la experiencia. En esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 6df2511c2dfee0158b4633be5dfa8549639cfc6d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889059"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="d5bf5-104">Tabla NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="d5bf5-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="d5bf5-105">En la tabla NetworkConnectionDetail asigna tipos de conexión de red a los identificadores de conexión de red que se usan en la base de datos de calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="d5bf5-106">En esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d5bf5-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d5bf5-107">**Column**</span></span>|<span data-ttu-id="d5bf5-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d5bf5-108">**Data Type**</span></span>|<span data-ttu-id="d5bf5-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d5bf5-109">**Key/Index**</span></span>|<span data-ttu-id="d5bf5-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d5bf5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d5bf5-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="d5bf5-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="d5bf5-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="d5bf5-112">tinyint</span></span>  <br/> |<span data-ttu-id="d5bf5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d5bf5-113">Primary</span></span>  <br/> |<span data-ttu-id="d5bf5-114">Identificador único para el tipo de conexión de red.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="d5bf5-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="d5bf5-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="d5bf5-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d5bf5-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="d5bf5-117">Único</span><span class="sxs-lookup"><span data-stu-id="d5bf5-117">Unique</span></span>  <br/> |<span data-ttu-id="d5bf5-118">Tipo de conexión de red que corresponde a la NetworkConnectionDetailKey.</span><span class="sxs-lookup"><span data-stu-id="d5bf5-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="d5bf5-119">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="d5bf5-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="d5bf5-120">0--con cable</span><span class="sxs-lookup"><span data-stu-id="d5bf5-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="d5bf5-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="d5bf5-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="d5bf5-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="d5bf5-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="d5bf5-123">3--MobileBB</span><span class="sxs-lookup"><span data-stu-id="d5bf5-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="d5bf5-124">4--otros</span><span class="sxs-lookup"><span data-stu-id="d5bf5-124">4 -- Other</span></span>  <br/> <span data-ttu-id="d5bf5-125">5--túnel</span><span class="sxs-lookup"><span data-stu-id="d5bf5-125">5 -- Tunnel</span></span>  <br/> |
   

