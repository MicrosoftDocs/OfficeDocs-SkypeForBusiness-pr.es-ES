---
title: Tabla DeviceDriver
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: La tabla DeviceDriver es una tabla de soporte. Cada registro representa un controlador usado por un dispositivo de captura o un dispositivo de representación.
ms.openlocfilehash: 8a502a1fc07c3541522931554064f7708b3e6187
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809718"
---
# <a name="devicedriver-table"></a><span data-ttu-id="c4a2c-104">Tabla DeviceDriver</span><span class="sxs-lookup"><span data-stu-id="c4a2c-104">DeviceDriver table</span></span>
 
<span data-ttu-id="c4a2c-105">La tabla DeviceDriver es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="c4a2c-105">The DeviceDriver table is a supporting table.</span></span> <span data-ttu-id="c4a2c-106">Cada registro representa un controlador usado por un dispositivo de captura o un dispositivo de representación.</span><span class="sxs-lookup"><span data-stu-id="c4a2c-106">Each record represents a driver used by either a capture device or render device.</span></span>
  
|<span data-ttu-id="c4a2c-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c4a2c-107">**Column**</span></span>|<span data-ttu-id="c4a2c-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="c4a2c-108">**Data Type**</span></span>|<span data-ttu-id="c4a2c-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="c4a2c-109">**Key/Index**</span></span>|<span data-ttu-id="c4a2c-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="c4a2c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c4a2c-111">**DeviceDriverKey**</span><span class="sxs-lookup"><span data-stu-id="c4a2c-111">**DeviceDriverKey**</span></span> <br/> |<span data-ttu-id="c4a2c-112">int</span><span class="sxs-lookup"><span data-stu-id="c4a2c-112">int</span></span>  <br/> |<span data-ttu-id="c4a2c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c4a2c-113">Primary</span></span>  <br/> |<span data-ttu-id="c4a2c-114">Número único que identifica este registro de controlador de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c4a2c-114">Unique number identifying this device driver record.</span></span>  <br/> |
|<span data-ttu-id="c4a2c-115">**DeviceDriver**</span><span class="sxs-lookup"><span data-stu-id="c4a2c-115">**DeviceDriver**</span></span> <br/> |<span data-ttu-id="c4a2c-116">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="c4a2c-116">varchar(256)</span></span>  <br/> |<span data-ttu-id="c4a2c-117">solo</span><span class="sxs-lookup"><span data-stu-id="c4a2c-117">unique</span></span>  <br/> |<span data-ttu-id="c4a2c-118">Nombre del controlador del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c4a2c-118">Device driver name.</span></span>  <br/> |
   

