---
title: Tabla dispositivos de Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabla dispositivos es una tabla de soporte. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296381"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="26df8-104">Tabla dispositivos de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="26df8-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="26df8-105">La tabla dispositivos es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="26df8-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="26df8-106">Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="26df8-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="26df8-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="26df8-107">**Column**</span></span>|<span data-ttu-id="26df8-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="26df8-108">**Data Type**</span></span>|<span data-ttu-id="26df8-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="26df8-109">**Key/Index**</span></span>|<span data-ttu-id="26df8-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="26df8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="26df8-111">**ID**</span><span class="sxs-lookup"><span data-stu-id="26df8-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="26df8-112">int</span><span class="sxs-lookup"><span data-stu-id="26df8-112">int</span></span>  <br/> |<span data-ttu-id="26df8-113">Primary</span><span class="sxs-lookup"><span data-stu-id="26df8-113">Primary</span></span>  <br/> |<span data-ttu-id="26df8-114">Número único que identifica esta versión de hardware.</span><span class="sxs-lookup"><span data-stu-id="26df8-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="26df8-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="26df8-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="26df8-116">int</span><span class="sxs-lookup"><span data-stu-id="26df8-116">int</span></span>  <br/> |<span data-ttu-id="26df8-117">Extranjero</span><span class="sxs-lookup"><span data-stu-id="26df8-117">Foreign</span></span>  <br/> |<span data-ttu-id="26df8-118">Fabricante de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="26df8-118">Manufacturer of this device.</span></span> <span data-ttu-id="26df8-119">Para obtener más información, consulte la [tabla de fabricantes en Skype empresarial Server 2015](manufacturers.md) .</span><span class="sxs-lookup"><span data-stu-id="26df8-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="26df8-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="26df8-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="26df8-121">int</span><span class="sxs-lookup"><span data-stu-id="26df8-121">int</span></span>  <br/> |<span data-ttu-id="26df8-122">Extranjero</span><span class="sxs-lookup"><span data-stu-id="26df8-122">Foreign</span></span>  <br/> |<span data-ttu-id="26df8-123">Versión de hardware de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="26df8-123">Hardware version of this device.</span></span> <span data-ttu-id="26df8-124">Para obtener más información, consulte la [tabla HardwareVersions en Skype empresarial Server 2015](hardwareversions.md) .</span><span class="sxs-lookup"><span data-stu-id="26df8-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="26df8-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="26df8-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="26df8-126">BIGINT</span><span class="sxs-lookup"><span data-stu-id="26df8-126">bigint</span></span>  <br/> ||<span data-ttu-id="26df8-127">Dirección MAC</span><span class="sxs-lookup"><span data-stu-id="26df8-127">MAC Address</span></span>  <br/> |
   

