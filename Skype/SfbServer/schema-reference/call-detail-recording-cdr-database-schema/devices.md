---
title: Tabla de dispositivos en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabla de dispositivos es una tabla de soporte. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).
ms.openlocfilehash: c7a5a5933d4fe2e465faf039a8ac2ed2a65fa563
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="84b8b-104">Tabla de dispositivos en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="84b8b-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="84b8b-105">La tabla de dispositivos es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="84b8b-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="84b8b-106">Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="84b8b-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="84b8b-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="84b8b-107">**Column**</span></span>|<span data-ttu-id="84b8b-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="84b8b-108">**Data Type**</span></span>|<span data-ttu-id="84b8b-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="84b8b-109">**Key/Index**</span></span>|<span data-ttu-id="84b8b-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="84b8b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="84b8b-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="84b8b-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="84b8b-112">int</span><span class="sxs-lookup"><span data-stu-id="84b8b-112">int</span></span>  <br/> |<span data-ttu-id="84b8b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="84b8b-113">Primary</span></span>  <br/> |<span data-ttu-id="84b8b-114">Número único que identifica la versión del hardware.</span><span class="sxs-lookup"><span data-stu-id="84b8b-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="84b8b-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="84b8b-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="84b8b-116">int</span><span class="sxs-lookup"><span data-stu-id="84b8b-116">int</span></span>  <br/> |<span data-ttu-id="84b8b-117">Externa</span><span class="sxs-lookup"><span data-stu-id="84b8b-117">Foreign</span></span>  <br/> |<span data-ttu-id="84b8b-118">Fabricante de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84b8b-118">Manufacturer of this device.</span></span> <span data-ttu-id="84b8b-119">Consulte la [tabla de fabricantes en Skype para Business Server 2015](manufacturers.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="84b8b-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="84b8b-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="84b8b-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="84b8b-121">int</span><span class="sxs-lookup"><span data-stu-id="84b8b-121">int</span></span>  <br/> |<span data-ttu-id="84b8b-122">Externa</span><span class="sxs-lookup"><span data-stu-id="84b8b-122">Foreign</span></span>  <br/> |<span data-ttu-id="84b8b-123">Versión de hardware de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84b8b-123">Hardware version of this device.</span></span> <span data-ttu-id="84b8b-124">Consulte la [tabla HardwareVersions en Skype para Business Server 2015](hardwareversions.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="84b8b-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="84b8b-125">**Dirección MAC**</span><span class="sxs-lookup"><span data-stu-id="84b8b-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="84b8b-126">bigint</span><span class="sxs-lookup"><span data-stu-id="84b8b-126">bigint</span></span>  <br/> ||<span data-ttu-id="84b8b-127">Dirección MAC</span><span class="sxs-lookup"><span data-stu-id="84b8b-127">MAC Address</span></span>  <br/> |
   

