---
title: Ver detalles de la calidad de la experiencia
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Vistas de cubren los escenarios más comunes para devolver los datos de la base de datos SQL QoE. Se recomienda vistas utilizadas para generar informes personalizados en lugar de obtener acceso directo a las tablas de la base de datos; eso es porque las vistas son más propensos a mantener la compatibilidad con versiones futuras al revés.
ms.openlocfilehash: 72fe0a1cd4bd3319bbb6907a23bda0932b3ef619
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="qoe-view-details"></a><span data-ttu-id="873f7-104">Ver detalles de la calidad de la experiencia</span><span class="sxs-lookup"><span data-stu-id="873f7-104">QoE view details</span></span>
 
<span data-ttu-id="873f7-105">Vistas de cubren los escenarios más comunes para devolver los datos de la base de datos SQL QoE.</span><span class="sxs-lookup"><span data-stu-id="873f7-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="873f7-106">Se recomienda vistas utilizadas para generar informes personalizados en lugar de obtener acceso directo a las tablas de la base de datos; eso es porque las vistas son más propensos a mantener la compatibilidad con versiones futuras al revés.</span><span class="sxs-lookup"><span data-stu-id="873f7-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="873f7-107">**Nombre de la vista**</span><span class="sxs-lookup"><span data-stu-id="873f7-107">**View Name**</span></span>|<span data-ttu-id="873f7-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="873f7-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="873f7-109">Vista de AudioStreamDetail</span><span class="sxs-lookup"><span data-stu-id="873f7-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="873f7-110">Almacena información acerca de cada secuencia de audio en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="873f7-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="873f7-111">Vista de MediaLine</span><span class="sxs-lookup"><span data-stu-id="873f7-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="873f7-112">Almacena información acerca de cada línea de medios en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="873f7-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="873f7-113">Una sesión de audio normalmente contiene una línea de audio multimedia.</span><span class="sxs-lookup"><span data-stu-id="873f7-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="873f7-114">Uno de audio y vídeo (A / V) sesión normalmente contiene una línea de media audio y una línea de vídeo; Sin embargo, la sesión puede contener dos líneas de vídeo si se utiliza un dispositivo de conferencias o si se utiliza la vista Galería.</span><span class="sxs-lookup"><span data-stu-id="873f7-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="873f7-115">Vista de NetworkConfigurationSettings</span><span class="sxs-lookup"><span data-stu-id="873f7-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="873f7-116">Almacena información acerca de la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="873f7-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="873f7-117">Vista de sesión</span><span class="sxs-lookup"><span data-stu-id="873f7-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="873f7-118">Almacena información acerca de las sesiones que tengan registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="873f7-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="873f7-119">UserAgent vista</span><span class="sxs-lookup"><span data-stu-id="873f7-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="873f7-120">Almacena información acerca de los agentes de usuario que han participado en sesiones que tengan registros en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="873f7-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="873f7-121">Vista de VideoStreamDetail</span><span class="sxs-lookup"><span data-stu-id="873f7-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="873f7-122">Almacena información acerca de cada secuencia de vídeo en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="873f7-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

