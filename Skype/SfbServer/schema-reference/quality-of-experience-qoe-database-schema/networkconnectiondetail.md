---
title: Tabla NetworkConnectionDetail
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La tabla NetworkConnectionDetail asigna los tipos de conexión de red a los identificadores de conexión de red usados en otra parte de la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806310"
---
# <a name="networkconnectiondetail-table"></a><span data-ttu-id="94ecc-104">Tabla NetworkConnectionDetail</span><span class="sxs-lookup"><span data-stu-id="94ecc-104">NetworkConnectionDetail table</span></span>
 
<span data-ttu-id="94ecc-105">La tabla NetworkConnectionDetail asigna los tipos de conexión de red a los identificadores de conexión de red usados en otra parte de la base de datos de calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="94ecc-105">The NetworkConnectionDetail table maps network connection types to the network connection identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="94ecc-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94ecc-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="94ecc-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="94ecc-107">**Column**</span></span>|<span data-ttu-id="94ecc-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="94ecc-108">**Data Type**</span></span>|<span data-ttu-id="94ecc-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="94ecc-109">**Key/Index**</span></span>|<span data-ttu-id="94ecc-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="94ecc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="94ecc-111">**NetworkConnectionDetailKey**</span><span class="sxs-lookup"><span data-stu-id="94ecc-111">**NetworkConnectionDetailKey**</span></span> <br/> |<span data-ttu-id="94ecc-112">tinyint</span><span class="sxs-lookup"><span data-stu-id="94ecc-112">tinyint</span></span>  <br/> |<span data-ttu-id="94ecc-113">Principal</span><span class="sxs-lookup"><span data-stu-id="94ecc-113">Primary</span></span>  <br/> |<span data-ttu-id="94ecc-114">Identificador único del tipo de conexión de red.</span><span class="sxs-lookup"><span data-stu-id="94ecc-114">Unique identifier for the network connection type.</span></span>  <br/> |
|<span data-ttu-id="94ecc-115">**NetworkConnectionDetail**</span><span class="sxs-lookup"><span data-stu-id="94ecc-115">**NetworkConnectionDetail**</span></span> <br/> |<span data-ttu-id="94ecc-116">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="94ecc-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="94ecc-117">Única</span><span class="sxs-lookup"><span data-stu-id="94ecc-117">Unique</span></span>  <br/> |<span data-ttu-id="94ecc-p103">Tipo de conexión de red que se corresponde con NetworkConnectionDetailKey. Los valores permitidos son:</span><span class="sxs-lookup"><span data-stu-id="94ecc-p103">Network connection type that corresponds to the NetworkConnectionDetailKey. Allowed values are:</span></span>  <br/> <span data-ttu-id="94ecc-120">0: cableada</span><span class="sxs-lookup"><span data-stu-id="94ecc-120">0 -- Wired</span></span>  <br/> <span data-ttu-id="94ecc-121">1: Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="94ecc-121">1 -- WiFi</span></span>  <br/> <span data-ttu-id="94ecc-122">2: Ethernet</span><span class="sxs-lookup"><span data-stu-id="94ecc-122">2 -- Ethernet</span></span>  <br/> <span data-ttu-id="94ecc-123">3-- MobileBB</span><span class="sxs-lookup"><span data-stu-id="94ecc-123">3 -- MobileBB</span></span>  <br/> <span data-ttu-id="94ecc-124">4 -- Otros</span><span class="sxs-lookup"><span data-stu-id="94ecc-124">4 -- Other</span></span>  <br/> <span data-ttu-id="94ecc-125">5-- Túnel</span><span class="sxs-lookup"><span data-stu-id="94ecc-125">5 -- Tunnel</span></span>  <br/> |
   

