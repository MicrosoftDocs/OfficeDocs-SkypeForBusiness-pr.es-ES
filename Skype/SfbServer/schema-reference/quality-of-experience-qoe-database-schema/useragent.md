---
title: Tabla UserAgent
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
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La tabla UserAgent es una tabla auxiliar que almacena una lista de los distintos agentes de usuario que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un agente de usuario
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799940"
---
# <a name="useragent-table"></a><span data-ttu-id="1d5c5-104">Tabla UserAgent</span><span class="sxs-lookup"><span data-stu-id="1d5c5-104">UserAgent table</span></span>
 
<span data-ttu-id="1d5c5-105">La tabla UserAgent es una tabla auxiliar que almacena una lista de los distintos agentes de usuario que han participado en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d5c5-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="1d5c5-106">Cada registro de la tabla representa un agente de usuario</span><span class="sxs-lookup"><span data-stu-id="1d5c5-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="1d5c5-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1d5c5-107">**Column**</span></span>|<span data-ttu-id="1d5c5-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="1d5c5-108">**Data Type**</span></span>|<span data-ttu-id="1d5c5-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="1d5c5-109">**Key/Index**</span></span>|<span data-ttu-id="1d5c5-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="1d5c5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1d5c5-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="1d5c5-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="1d5c5-112">entero</span><span class="sxs-lookup"><span data-stu-id="1d5c5-112">int</span></span>  <br/> |<span data-ttu-id="1d5c5-113">Principal</span><span class="sxs-lookup"><span data-stu-id="1d5c5-113">Primary</span></span>  <br/> |<span data-ttu-id="1d5c5-114">Número único que identifica este agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="1d5c5-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="1d5c5-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="1d5c5-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="1d5c5-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1d5c5-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1d5c5-117">Única</span><span class="sxs-lookup"><span data-stu-id="1d5c5-117">Unique</span></span>  <br/> |<span data-ttu-id="1d5c5-118">Cadena de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="1d5c5-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="1d5c5-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="1d5c5-119">**UAType**</span></span> <br/> |<span data-ttu-id="1d5c5-120">smallint</span><span class="sxs-lookup"><span data-stu-id="1d5c5-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="1d5c5-121">1 es el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="1d5c5-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="1d5c5-122">2 es un servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="1d5c5-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="1d5c5-123">4 es Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="1d5c5-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="1d5c5-124">8 es teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="1d5c5-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="1d5c5-125">16 es Live Meeting Console.</span><span class="sxs-lookup"><span data-stu-id="1d5c5-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="1d5c5-126">32 es la Herramienta de validación de implementación (DVT).</span><span class="sxs-lookup"><span data-stu-id="1d5c5-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="1d5c5-127">64 es Skype Empresarial Server en equipos Macintosh.</span><span class="sxs-lookup"><span data-stu-id="1d5c5-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="1d5c5-128">128 es el Operador de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="1d5c5-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="1d5c5-129">256 es el servicio de anuncio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="1d5c5-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="1d5c5-130">512 es el número de conferencias Operador automático.</span><span class="sxs-lookup"><span data-stu-id="1d5c5-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="1d5c5-131">1024 es una aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="1d5c5-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="1d5c5-132">2048 es Fuera del control de voz.</span><span class="sxs-lookup"><span data-stu-id="1d5c5-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

