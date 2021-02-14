---
title: Tabla Device
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
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La tabla Dispositivo es una tabla auxiliar que almacena información sobre los diversos dispositivos de captura o presentación. Cada registro de la tabla representa un dispositivo.
ms.openlocfilehash: 818458e41c71398f3df11ac9a47eeee0841c6dca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814750"
---
# <a name="device-table"></a><span data-ttu-id="9e674-104">Tabla Device</span><span class="sxs-lookup"><span data-stu-id="9e674-104">Device table</span></span>
 
<span data-ttu-id="9e674-p102">La tabla Dispositivo es una tabla auxiliar que almacena información sobre los diversos dispositivos de captura o presentación. Cada registro de la tabla representa un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9e674-p102">The Device table is a supporting table that stores information about the various capture or render devices. Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="9e674-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9e674-107">**Column**</span></span>|<span data-ttu-id="9e674-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9e674-108">**Data Type**</span></span>|<span data-ttu-id="9e674-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="9e674-109">**Key/Index**</span></span>|<span data-ttu-id="9e674-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="9e674-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9e674-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="9e674-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="9e674-112">entero</span><span class="sxs-lookup"><span data-stu-id="9e674-112">int</span></span>  <br/> |<span data-ttu-id="9e674-113">Principal</span><span class="sxs-lookup"><span data-stu-id="9e674-113">Primary</span></span>  <br/> |<span data-ttu-id="9e674-114">Número único que identifica este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9e674-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="9e674-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="9e674-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="9e674-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9e674-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9e674-117">DeviceName + DeviceType son únicos</span><span class="sxs-lookup"><span data-stu-id="9e674-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="9e674-118">Nombre del dispositivo</span><span class="sxs-lookup"><span data-stu-id="9e674-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="9e674-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="9e674-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="9e674-120">bit</span><span class="sxs-lookup"><span data-stu-id="9e674-120">bit</span></span>  <br/> |<span data-ttu-id="9e674-121">DeviceName + DeviceType son únicos</span><span class="sxs-lookup"><span data-stu-id="9e674-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="9e674-p103">Tipo de dispositivo. 1 es un dispositivo de captura, 0 es un dispositivo de presentación.</span><span class="sxs-lookup"><span data-stu-id="9e674-p103">Device type. 1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

