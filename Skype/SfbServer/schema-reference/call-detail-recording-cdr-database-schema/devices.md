---
title: Tabla de dispositivos en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: En la tabla de dispositivos es una tabla de apoyo. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).
ms.openlocfilehash: f770f19fb94bf25bdb4c13e74dc41e05f6674788
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213168"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6e4c1-104">Tabla de dispositivos en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6e4c1-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6e4c1-105">En la tabla de dispositivos es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="6e4c1-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="6e4c1-106">Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="6e4c1-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="6e4c1-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="6e4c1-107">**Column**</span></span>|<span data-ttu-id="6e4c1-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6e4c1-108">**Data Type**</span></span>|<span data-ttu-id="6e4c1-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="6e4c1-109">**Key/Index**</span></span>|<span data-ttu-id="6e4c1-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="6e4c1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6e4c1-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="6e4c1-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="6e4c1-112">int</span><span class="sxs-lookup"><span data-stu-id="6e4c1-112">int</span></span>  <br/> |<span data-ttu-id="6e4c1-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6e4c1-113">Primary</span></span>  <br/> |<span data-ttu-id="6e4c1-114">Número único que identifica esta versión de hardware.</span><span class="sxs-lookup"><span data-stu-id="6e4c1-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="6e4c1-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="6e4c1-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="6e4c1-116">int</span><span class="sxs-lookup"><span data-stu-id="6e4c1-116">int</span></span>  <br/> |<span data-ttu-id="6e4c1-117">Externa</span><span class="sxs-lookup"><span data-stu-id="6e4c1-117">Foreign</span></span>  <br/> |<span data-ttu-id="6e4c1-118">Fabricante de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6e4c1-118">Manufacturer of this device.</span></span> <span data-ttu-id="6e4c1-119">Consulte la [tabla de los fabricantes de Skype para Business Server 2015](manufacturers.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6e4c1-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6e4c1-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="6e4c1-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="6e4c1-121">int</span><span class="sxs-lookup"><span data-stu-id="6e4c1-121">int</span></span>  <br/> |<span data-ttu-id="6e4c1-122">Externa</span><span class="sxs-lookup"><span data-stu-id="6e4c1-122">Foreign</span></span>  <br/> |<span data-ttu-id="6e4c1-123">Versión de hardware de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6e4c1-123">Hardware version of this device.</span></span> <span data-ttu-id="6e4c1-124">Consulte la [tabla HardwareVersions en Skype para Business Server 2015](hardwareversions.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6e4c1-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6e4c1-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="6e4c1-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="6e4c1-126">bigint</span><span class="sxs-lookup"><span data-stu-id="6e4c1-126">bigint</span></span>  <br/> ||<span data-ttu-id="6e4c1-127">Dirección MAC</span><span class="sxs-lookup"><span data-stu-id="6e4c1-127">MAC Address</span></span>  <br/> |
   

