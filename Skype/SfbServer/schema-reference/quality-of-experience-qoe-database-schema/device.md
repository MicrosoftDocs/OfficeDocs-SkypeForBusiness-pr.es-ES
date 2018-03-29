---
title: Tabla Device
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La tabla del dispositivo es una tabla de soporte que almacena información acerca de la captura de diferentes o representar los dispositivos. Cada registro de la tabla representa un dispositivo.
ms.openlocfilehash: 346ea171b9a0c1b7a874b65a68b582c4167c57fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="device-table"></a><span data-ttu-id="6be0a-104">Tabla Device</span><span class="sxs-lookup"><span data-stu-id="6be0a-104">Device table</span></span>
 
<span data-ttu-id="6be0a-105">La tabla del dispositivo es una tabla de soporte que almacena información acerca de la captura de diferentes o representar los dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6be0a-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="6be0a-106">Cada registro de la tabla representa un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6be0a-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="6be0a-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="6be0a-107">**Column**</span></span>|<span data-ttu-id="6be0a-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6be0a-108">**Data Type**</span></span>|<span data-ttu-id="6be0a-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="6be0a-109">**Key/Index**</span></span>|<span data-ttu-id="6be0a-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="6be0a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6be0a-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="6be0a-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="6be0a-112">int</span><span class="sxs-lookup"><span data-stu-id="6be0a-112">int</span></span>  <br/> |<span data-ttu-id="6be0a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6be0a-113">Primary</span></span>  <br/> |<span data-ttu-id="6be0a-114">Número único que identifica este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6be0a-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="6be0a-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="6be0a-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="6be0a-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6be0a-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6be0a-117">DeviceName + DeviceType es único</span><span class="sxs-lookup"><span data-stu-id="6be0a-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="6be0a-118">Nombre de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6be0a-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="6be0a-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="6be0a-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="6be0a-120">bit</span><span class="sxs-lookup"><span data-stu-id="6be0a-120">bit</span></span>  <br/> |<span data-ttu-id="6be0a-121">DeviceName + DeviceType es único</span><span class="sxs-lookup"><span data-stu-id="6be0a-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="6be0a-122">Tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6be0a-122">Device type.</span></span> <span data-ttu-id="6be0a-123">1 es un dispositivo de captura, 0 es un dispositivo de representación.</span><span class="sxs-lookup"><span data-stu-id="6be0a-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

