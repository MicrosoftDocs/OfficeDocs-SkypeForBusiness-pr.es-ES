---
title: Tabla Device
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La tabla de dispositivos es una tabla de soporte que almacena información sobre los diversos dispositivos de captura o de representación. Cada registro de la tabla representa un dispositivo.
ms.openlocfilehash: a73deac9bec6ce4515eaffc256179b10d1f27106
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295009"
---
# <a name="device-table"></a><span data-ttu-id="d5587-104">Tabla Device</span><span class="sxs-lookup"><span data-stu-id="d5587-104">Device table</span></span>
 
<span data-ttu-id="d5587-105">La tabla de dispositivos es una tabla de soporte que almacena información sobre los diversos dispositivos de captura o de representación.</span><span class="sxs-lookup"><span data-stu-id="d5587-105">The Device table is a supporting table that stores information about the various capture or render devices.</span></span> <span data-ttu-id="d5587-106">Cada registro de la tabla representa un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5587-106">Each record in the table represents one device.</span></span>
  
|<span data-ttu-id="d5587-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d5587-107">**Column**</span></span>|<span data-ttu-id="d5587-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d5587-108">**Data Type**</span></span>|<span data-ttu-id="d5587-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d5587-109">**Key/Index**</span></span>|<span data-ttu-id="d5587-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d5587-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d5587-111">**DeviceKey**</span><span class="sxs-lookup"><span data-stu-id="d5587-111">**DeviceKey**</span></span> <br/> |<span data-ttu-id="d5587-112">int</span><span class="sxs-lookup"><span data-stu-id="d5587-112">int</span></span>  <br/> |<span data-ttu-id="d5587-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d5587-113">Primary</span></span>  <br/> |<span data-ttu-id="d5587-114">Número único que identifica este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5587-114">Unique number identifying this device.</span></span>  <br/> |
|<span data-ttu-id="d5587-115">**DeviceName**</span><span class="sxs-lookup"><span data-stu-id="d5587-115">**DeviceName**</span></span> <br/> |<span data-ttu-id="d5587-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d5587-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d5587-117">DeviceName + DeviceType es único</span><span class="sxs-lookup"><span data-stu-id="d5587-117">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="d5587-118">Nombre del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5587-118">Device name.</span></span>  <br/> |
|<span data-ttu-id="d5587-119">**DeviceType**</span><span class="sxs-lookup"><span data-stu-id="d5587-119">**DeviceType**</span></span> <br/> |<span data-ttu-id="d5587-120">bit</span><span class="sxs-lookup"><span data-stu-id="d5587-120">bit</span></span>  <br/> |<span data-ttu-id="d5587-121">DeviceName + DeviceType es único</span><span class="sxs-lookup"><span data-stu-id="d5587-121">DeviceName + DeviceType is unique</span></span>  <br/> |<span data-ttu-id="d5587-122">Tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d5587-122">Device type.</span></span> <span data-ttu-id="d5587-123">1 es un dispositivo de captura, 0 es un dispositivo de representación.</span><span class="sxs-lookup"><span data-stu-id="d5587-123">1 is a capture device, 0 is a render device.</span></span>  <br/> |
   

