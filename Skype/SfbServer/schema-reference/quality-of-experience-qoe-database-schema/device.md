---
title: Tabla Device
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: En la tabla de dispositivo es una tabla de apoyo que almacena información acerca de la captura diversos o dispositivos de presentación. Cada registro de la tabla representa un dispositivo.
ms.openlocfilehash: 0b3c27708cd8e9d1b02914e6f2cba414e353609c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920029"
---
# <a name="device-table"></a><span data-ttu-id="84f9d-104">Tabla Device</span><span class="sxs-lookup"><span data-stu-id="84f9d-104">Device table</span></span>
 
<span data-ttu-id="84f9d-105">En la tabla de dispositivo es una tabla de apoyo que almacena información acerca de la captura diversos o dispositivos de presentación.</span><span class="sxs-lookup"><span data-stu-id="84f9d-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="84f9d-106">Cada registro de la tabla representa un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84f9d-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="84f9d-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="84f9d-107">**Column**</span></span>|<span data-ttu-id="84f9d-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="84f9d-108">**Data Type**</span></span>|<span data-ttu-id="84f9d-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="84f9d-109">**Key/Index**</span></span>|<span data-ttu-id="84f9d-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="84f9d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="84f9d-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="84f9d-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="84f9d-112">int</span><span class="sxs-lookup"><span data-stu-id="84f9d-112">int</span></span>  <br/> |<span data-ttu-id="84f9d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="84f9d-113">Primary</span></span>  <br/> |<span data-ttu-id="84f9d-114">Número único que identifica este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84f9d-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="84f9d-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="84f9d-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="84f9d-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="84f9d-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="84f9d-117">DeviceName + DeviceType son únicos</span><span class="sxs-lookup"><span data-stu-id="84f9d-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="84f9d-118">Nombre del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84f9d-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="84f9d-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="84f9d-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="84f9d-120">bit</span><span class="sxs-lookup"><span data-stu-id="84f9d-120">bit</span></span>  <br/> |<span data-ttu-id="84f9d-121">DeviceName + DeviceType son únicos</span><span class="sxs-lookup"><span data-stu-id="84f9d-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="84f9d-122">Tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84f9d-122">Device type.</span></span> <span data-ttu-id="84f9d-123">1 es un dispositivo de captura, 0 es un dispositivo de presentación.</span><span class="sxs-lookup"><span data-stu-id="84f9d-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

