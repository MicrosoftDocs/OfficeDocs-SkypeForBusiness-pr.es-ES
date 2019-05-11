---
title: Detalles de la vista QoE
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Las vistas tratan los escenarios más comunes para devolver los datos de la base de datos SQL QoE. Se recomienda vistas usadas para generación de informes personalizados en lugar de obteniendo acceso directamente a las tablas de base de datos; Esto es debido a que las vistas son más probables mantener la compatibilidad con versiones futuras con versiones anteriores.
ms.openlocfilehash: 2726900a1fc31c6e69571123c87137b3291a507e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924867"
---
# <a name="qoe-view-details"></a><span data-ttu-id="0eb0c-104">Detalles de la vista QoE</span><span class="sxs-lookup"><span data-stu-id="0eb0c-104">QoE view details</span></span>
 
<span data-ttu-id="0eb0c-105">Las vistas tratan los escenarios más comunes para devolver los datos de la base de datos SQL QoE.</span><span class="sxs-lookup"><span data-stu-id="0eb0c-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="0eb0c-106">Se recomienda vistas usadas para generación de informes personalizados en lugar de obteniendo acceso directamente a las tablas de base de datos; Esto es debido a que las vistas son más probables mantener la compatibilidad con versiones futuras con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="0eb0c-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="0eb0c-107">**Nombre de la vista**</span><span class="sxs-lookup"><span data-stu-id="0eb0c-107">**View Name**</span></span>|<span data-ttu-id="0eb0c-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0eb0c-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="0eb0c-109">Vista AudioStreamDetail</span><span class="sxs-lookup"><span data-stu-id="0eb0c-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="0eb0c-110">Almacena información acerca de cada secuencia de audio en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0eb0c-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="0eb0c-111">Vista MediaLine</span><span class="sxs-lookup"><span data-stu-id="0eb0c-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="0eb0c-112">Almacena información acerca de cada línea de medios en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0eb0c-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="0eb0c-113">Normalmente, una sesión de audio contiene una línea de medios de audio.</span><span class="sxs-lookup"><span data-stu-id="0eb0c-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="0eb0c-114">Uno de audio y vídeo (A / V) sesión normalmente contiene una línea de medios de audio y una única línea de medios de vídeo. Sin embargo, la sesión puede contener dos líneas de medios de vídeo si se usa un dispositivo para conferencias o si se usa la vista de galería.</span><span class="sxs-lookup"><span data-stu-id="0eb0c-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="0eb0c-115">Vista NetworkConfigurationSettings</span><span class="sxs-lookup"><span data-stu-id="0eb0c-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="0eb0c-116">Almacena información acerca de la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="0eb0c-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="0eb0c-117">Vista de sesión</span><span class="sxs-lookup"><span data-stu-id="0eb0c-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="0eb0c-118">Almacena información acerca de las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0eb0c-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="0eb0c-119">Vista UserAgent</span><span class="sxs-lookup"><span data-stu-id="0eb0c-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="0eb0c-120">Almacena información acerca de los agentes de usuario que han participado en las sesiones que tienen registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0eb0c-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="0eb0c-121">Vista VideoStreamDetail</span><span class="sxs-lookup"><span data-stu-id="0eb0c-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="0eb0c-122">Almacena información acerca de cada secuencia de vídeo en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0eb0c-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

