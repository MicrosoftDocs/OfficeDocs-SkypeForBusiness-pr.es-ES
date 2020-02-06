---
title: Tabla NetworkConnectionDetail
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La tabla NetworkConnectionDetail se asigna a los identificadores de conexión de red que se usan en otras partes de la base de datos de la calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: d91928e40f6df9db1e53140726bbf04efad586ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807508"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="a5b12-104">Tabla NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="a5b12-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="a5b12-105">La tabla NetworkConnectionDetail se asigna a los identificadores de conexión de red que se usan en otras partes de la base de datos de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="a5b12-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="a5b12-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5b12-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a5b12-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a5b12-107">**Column**</span></span>|<span data-ttu-id="a5b12-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="a5b12-108">**Data Type**</span></span>|<span data-ttu-id="a5b12-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="a5b12-109">**Key/Index**</span></span>|<span data-ttu-id="a5b12-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="a5b12-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a5b12-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="a5b12-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="a5b12-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="a5b12-112">tinyint</span></span>  <br/> |<span data-ttu-id="a5b12-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a5b12-113">Primary</span></span>  <br/> |<span data-ttu-id="a5b12-114">Identificador único del tipo de conexión de red.</span><span class="sxs-lookup"><span data-stu-id="a5b12-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="a5b12-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="a5b12-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="a5b12-116">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="a5b12-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="a5b12-117">Solo</span><span class="sxs-lookup"><span data-stu-id="a5b12-117">Unique</span></span>  <br/> |<span data-ttu-id="a5b12-118">Tipo de conexión de red que corresponde a la NetworkConnectionDetailKey.</span><span class="sxs-lookup"><span data-stu-id="a5b12-118">Network connection type that corresponds to the NetworkConnectionDetailKey.</span></span> <span data-ttu-id="a5b12-119">Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="a5b12-119">Allowed values are:</span></span>  <br/> <span data-ttu-id="a5b12-120">0: conectado</span><span class="sxs-lookup"><span data-stu-id="a5b12-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="a5b12-121">1--WiFi</span><span class="sxs-lookup"><span data-stu-id="a5b12-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="a5b12-122">2--Ethernet</span><span class="sxs-lookup"><span data-stu-id="a5b12-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="a5b12-123">3--MobileBB</span><span class="sxs-lookup"><span data-stu-id="a5b12-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="a5b12-124">4--otros</span><span class="sxs-lookup"><span data-stu-id="a5b12-124">4 -- Other</span></span>  <br/> <span data-ttu-id="a5b12-125">5--túnel</span><span class="sxs-lookup"><span data-stu-id="a5b12-125">5 -- Tunnel</span></span>  <br/> |
   

