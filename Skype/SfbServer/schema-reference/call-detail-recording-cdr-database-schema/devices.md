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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabla dispositivos es una tabla de soporte. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815288"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ee2d6-104">Tabla dispositivos de Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="ee2d6-104">Devices table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ee2d6-105">La tabla dispositivos es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-105">The Devices table is a supporting table.</span></span> <span data-ttu-id="ee2d6-106">Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).</span><span class="sxs-lookup"><span data-stu-id="ee2d6-106">Each record stores information about one device (desk phone).</span></span>
  
|<span data-ttu-id="ee2d6-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ee2d6-107">**Column**</span></span>|<span data-ttu-id="ee2d6-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ee2d6-108">**Data Type**</span></span>|<span data-ttu-id="ee2d6-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="ee2d6-109">**Key/Index**</span></span>|<span data-ttu-id="ee2d6-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ee2d6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ee2d6-111">**ID**</span><span class="sxs-lookup"><span data-stu-id="ee2d6-111">**DeviceId**</span></span> <br/> |<span data-ttu-id="ee2d6-112">int</span><span class="sxs-lookup"><span data-stu-id="ee2d6-112">int</span></span>  <br/> |<span data-ttu-id="ee2d6-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ee2d6-113">Primary</span></span>  <br/> |<span data-ttu-id="ee2d6-114">Número único que identifica esta versión de hardware.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-114">Unique number identifying this hardware version.</span></span>  <br/> |
|<span data-ttu-id="ee2d6-115">**ManufacturerId**</span><span class="sxs-lookup"><span data-stu-id="ee2d6-115">**ManufacturerId**</span></span> <br/> |<span data-ttu-id="ee2d6-116">int</span><span class="sxs-lookup"><span data-stu-id="ee2d6-116">int</span></span>  <br/> |<span data-ttu-id="ee2d6-117">Extranjero</span><span class="sxs-lookup"><span data-stu-id="ee2d6-117">Foreign</span></span>  <br/> |<span data-ttu-id="ee2d6-118">Fabricante de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-118">Manufacturer of this device.</span></span> <span data-ttu-id="ee2d6-119">Para obtener más información, consulte la [tabla de fabricantes en Skype empresarial Server 2015](manufacturers.md) .</span><span class="sxs-lookup"><span data-stu-id="ee2d6-119">See the [Manufacturers table in Skype for Business Server 2015](manufacturers.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ee2d6-120">**HardwareVersionId**</span><span class="sxs-lookup"><span data-stu-id="ee2d6-120">**HardwareVersionId**</span></span> <br/> |<span data-ttu-id="ee2d6-121">int</span><span class="sxs-lookup"><span data-stu-id="ee2d6-121">int</span></span>  <br/> |<span data-ttu-id="ee2d6-122">Extranjero</span><span class="sxs-lookup"><span data-stu-id="ee2d6-122">Foreign</span></span>  <br/> |<span data-ttu-id="ee2d6-123">Versión de hardware de este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ee2d6-123">Hardware version of this device.</span></span> <span data-ttu-id="ee2d6-124">Para obtener más información, consulte la [tabla HardwareVersions en Skype empresarial Server 2015](hardwareversions.md) .</span><span class="sxs-lookup"><span data-stu-id="ee2d6-124">See the [HardwareVersions table in Skype for Business Server 2015](hardwareversions.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ee2d6-125">**MacAddress**</span><span class="sxs-lookup"><span data-stu-id="ee2d6-125">**MacAddress**</span></span> <br/> |<span data-ttu-id="ee2d6-126">BIGINT</span><span class="sxs-lookup"><span data-stu-id="ee2d6-126">bigint</span></span>  <br/> ||<span data-ttu-id="ee2d6-127">Dirección MAC</span><span class="sxs-lookup"><span data-stu-id="ee2d6-127">MAC Address</span></span>  <br/> |
   

