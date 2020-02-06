---
title: Detalles de la vista QoE
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Las vistas cubren los escenarios más comunes para devolver datos desde la base de datos SQL de calidad. Se recomienda usar vistas para crear informes personalizados en lugar de obtener acceso directamente a las tablas de la base de datos; Esto se debe a que las vistas tienen más probabilidades de mantener la compatibilidad con versiones futuras.
ms.openlocfilehash: d207c2cff86c398fed62023b30d193e974cbca7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807178"
---
# <a name="qoe-view-details"></a><span data-ttu-id="7a4ba-104">Detalles de la vista QoE</span><span class="sxs-lookup"><span data-stu-id="7a4ba-104">QoE view details</span></span>
 
<span data-ttu-id="7a4ba-105">Las vistas cubren los escenarios más comunes para devolver datos desde la base de datos SQL de calidad.</span><span class="sxs-lookup"><span data-stu-id="7a4ba-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="7a4ba-106">Se recomienda usar vistas para crear informes personalizados en lugar de obtener acceso directamente a las tablas de la base de datos; Esto se debe a que las vistas tienen más probabilidades de mantener la compatibilidad con versiones futuras.</span><span class="sxs-lookup"><span data-stu-id="7a4ba-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="7a4ba-107">**Nombre de la vista**</span><span class="sxs-lookup"><span data-stu-id="7a4ba-107">**View Name**</span></span>|<span data-ttu-id="7a4ba-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7a4ba-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7a4ba-109">Vista AudioStreamDetail</span><span class="sxs-lookup"><span data-stu-id="7a4ba-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="7a4ba-110">Almacena información sobre cada secuencia de audio de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a4ba-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="7a4ba-111">Vista MediaLine</span><span class="sxs-lookup"><span data-stu-id="7a4ba-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="7a4ba-112">Almacena información sobre cada línea de medios de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a4ba-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="7a4ba-113">Una sesión de audio normalmente contiene una línea multimedia de audio.</span><span class="sxs-lookup"><span data-stu-id="7a4ba-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="7a4ba-114">Una sesión de audio y vídeo (A/V) normalmente contiene una línea de medio de audio y una línea de medio de vídeo; sin embargo, la sesión podría contener dos líneas multimedia de vídeo si se usa un dispositivo de conferencia o si se usa la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="7a4ba-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="7a4ba-115">Vista NetworkConfigurationSettings</span><span class="sxs-lookup"><span data-stu-id="7a4ba-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="7a4ba-116">Almacena información sobre la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="7a4ba-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="7a4ba-117">Vista de sesión</span><span class="sxs-lookup"><span data-stu-id="7a4ba-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="7a4ba-118">Almacena información sobre las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a4ba-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="7a4ba-119">Vista UserAgent</span><span class="sxs-lookup"><span data-stu-id="7a4ba-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="7a4ba-120">Almacena información sobre los agentes de usuario implicados en las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a4ba-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="7a4ba-121">Vista VideoStreamDetail</span><span class="sxs-lookup"><span data-stu-id="7a4ba-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="7a4ba-122">Almacena información sobre cada secuencia de vídeo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7a4ba-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

