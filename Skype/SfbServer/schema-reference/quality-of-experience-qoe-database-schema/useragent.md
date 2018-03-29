---
title: Tabla UserAgent
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La tabla UserAgent es un auxiliar que almacena una lista de los distintos agentes de usuario que han participado en las sesiones que se registran en la base de datos. Cada registro de la tabla representa a un agente de usuario
ms.openlocfilehash: 5b9bcc35fbad3d20a006410aeb3538b6f5daa77e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="useragent-table"></a><span data-ttu-id="cda41-104">Tabla UserAgent</span><span class="sxs-lookup"><span data-stu-id="cda41-104">UserAgent table</span></span>
 
<span data-ttu-id="cda41-105">La tabla UserAgent es un auxiliar que almacena una lista de los distintos agentes de usuario que han participado en las sesiones que se registran en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cda41-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="cda41-106">Cada registro de la tabla representa a un agente de usuario</span><span class="sxs-lookup"><span data-stu-id="cda41-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="cda41-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="cda41-107">**Column**</span></span>|<span data-ttu-id="cda41-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="cda41-108">**Data Type**</span></span>|<span data-ttu-id="cda41-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="cda41-109">**Key/Index**</span></span>|<span data-ttu-id="cda41-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="cda41-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cda41-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="cda41-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="cda41-112">int</span><span class="sxs-lookup"><span data-stu-id="cda41-112">int</span></span>  <br/> |<span data-ttu-id="cda41-113">Primary</span><span class="sxs-lookup"><span data-stu-id="cda41-113">Primary</span></span>  <br/> |<span data-ttu-id="cda41-114">Número único que identifica a este agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="cda41-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="cda41-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="cda41-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="cda41-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cda41-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cda41-117">Único</span><span class="sxs-lookup"><span data-stu-id="cda41-117">Unique</span></span>  <br/> |<span data-ttu-id="cda41-118">Cadena de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="cda41-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="cda41-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="cda41-119">**UAType**</span></span> <br/> |<span data-ttu-id="cda41-120">smallint</span><span class="sxs-lookup"><span data-stu-id="cda41-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="cda41-121">1 es el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="cda41-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="cda41-122">es de 2 A / V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="cda41-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="cda41-123">4 es Skype para el negocio.</span><span class="sxs-lookup"><span data-stu-id="cda41-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="cda41-124">8 es el teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="cda41-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="cda41-125">16 es la consola Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="cda41-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="cda41-126">32 es la herramienta de validación de implementación (TVP).</span><span class="sxs-lookup"><span data-stu-id="cda41-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="cda41-127">64 es Skype para Business Server en equipos Macintosh.</span><span class="sxs-lookup"><span data-stu-id="cda41-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="cda41-128">128 es Skype para operador de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="cda41-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="cda41-129">256 es servicio de anuncio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="cda41-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="cda41-130">Operador automático de conferencia es de 512.</span><span class="sxs-lookup"><span data-stu-id="cda41-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="cda41-131">1024 es la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="cda41-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="cda41-132">2048 está fuera de Control de voz.</span><span class="sxs-lookup"><span data-stu-id="cda41-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

