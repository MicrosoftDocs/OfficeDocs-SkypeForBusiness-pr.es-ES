---
title: Tabla Devices en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabla Dispositivos es una tabla de apoyo. Cada registro almacena información sobre un dispositivo (teléfono de escritorio).
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831820"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c9825-104">Tabla Devices en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="c9825-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c9825-105">La tabla Dispositivos es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="c9825-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="c9825-106">Cada registro almacena información sobre un dispositivo (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="c9825-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="c9825-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c9825-107">**Column**</span></span>|<span data-ttu-id="c9825-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="c9825-108">**Data Type**</span></span>|<span data-ttu-id="c9825-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="c9825-109">**Key/Index**</span></span>|<span data-ttu-id="c9825-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="c9825-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c9825-111">**DeviceId**</span><span class="sxs-lookup"><span data-stu-id="c9825-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="c9825-112">entero</span><span class="sxs-lookup"><span data-stu-id="c9825-112">int</span></span>  <br/> |<span data-ttu-id="c9825-113">Principal</span><span class="sxs-lookup"><span data-stu-id="c9825-113">Primary</span></span>  <br/> |<span data-ttu-id="c9825-114">Número único que identifica esta versión de hardware.</span><span class="sxs-lookup"><span data-stu-id="c9825-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="c9825-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="c9825-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="c9825-116">entero</span><span class="sxs-lookup"><span data-stu-id="c9825-116">int</span></span>  <br/> |<span data-ttu-id="c9825-117">Externo</span><span class="sxs-lookup"><span data-stu-id="c9825-117">Foreign</span></span>  <br/> |<span data-ttu-id="c9825-118">Fabricante de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c9825-118">Manufacturer of this device.</span></span> <span data-ttu-id="c9825-119">Consulte la [tabla Fabricantes de Skype Empresarial Server 2015](manufacturers.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c9825-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c9825-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="c9825-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="c9825-121">entero</span><span class="sxs-lookup"><span data-stu-id="c9825-121">int</span></span>  <br/> |<span data-ttu-id="c9825-122">Externo</span><span class="sxs-lookup"><span data-stu-id="c9825-122">Foreign</span></span>  <br/> |<span data-ttu-id="c9825-123">Versión de hardware de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c9825-123">Hardware version of this device.</span></span> <span data-ttu-id="c9825-124">Consulte la [tabla HardwareVersions en Skype Empresarial Server 2015](hardwareversions.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c9825-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c9825-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="c9825-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="c9825-126">bigint</span><span class="sxs-lookup"><span data-stu-id="c9825-126">bigint</span></span>  <br/> ||<span data-ttu-id="c9825-127">Dirección MAC</span><span class="sxs-lookup"><span data-stu-id="c9825-127">MAC Address</span></span>  <br/> |
   

