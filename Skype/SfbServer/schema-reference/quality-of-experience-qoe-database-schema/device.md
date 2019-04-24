---
title: Tabla Device
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: En la tabla de dispositivo es una tabla de apoyo que almacena información acerca de la captura diversos o dispositivos de presentación. Cada registro de la tabla representa un dispositivo.
ms.openlocfilehash: 09af6ee11ebc821d123e847fbad812479d9d7bb0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212252"
---
# <a name="device-table"></a><span data-ttu-id="ce21f-104">Tabla Device</span><span class="sxs-lookup"><span data-stu-id="ce21f-104">Device table</span></span>
 
<span data-ttu-id="ce21f-105">En la tabla de dispositivo es una tabla de apoyo que almacena información acerca de la captura diversos o dispositivos de presentación.</span><span class="sxs-lookup"><span data-stu-id="ce21f-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="ce21f-106">Cada registro de la tabla representa un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce21f-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="ce21f-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ce21f-107">**Column**</span></span>|<span data-ttu-id="ce21f-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ce21f-108">**Data Type**</span></span>|<span data-ttu-id="ce21f-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="ce21f-109">**Key/Index**</span></span>|<span data-ttu-id="ce21f-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ce21f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ce21f-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="ce21f-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="ce21f-112">int</span><span class="sxs-lookup"><span data-stu-id="ce21f-112">int</span></span>  <br/> |<span data-ttu-id="ce21f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ce21f-113">Primary</span></span>  <br/> |<span data-ttu-id="ce21f-114">Número único que identifica este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce21f-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="ce21f-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="ce21f-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="ce21f-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ce21f-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ce21f-117">DeviceName + DeviceType son únicos</span><span class="sxs-lookup"><span data-stu-id="ce21f-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="ce21f-118">Nombre del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce21f-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="ce21f-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="ce21f-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="ce21f-120">bit</span><span class="sxs-lookup"><span data-stu-id="ce21f-120">bit</span></span>  <br/> |<span data-ttu-id="ce21f-121">DeviceName + DeviceType son únicos</span><span class="sxs-lookup"><span data-stu-id="ce21f-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="ce21f-122">Tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ce21f-122">Device type.</span></span> <span data-ttu-id="ce21f-123">1 es un dispositivo de captura, 0 es un dispositivo de presentación.</span><span class="sxs-lookup"><span data-stu-id="ce21f-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

