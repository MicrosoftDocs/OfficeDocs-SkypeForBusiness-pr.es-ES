---
title: Tabla UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La tabla UserAgent es una tabla de soporte que almacena una lista de los diversos agentes de usuario que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa un agente de usuario
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294589"
---
# <a name="useragent-table"></a><span data-ttu-id="61cc4-104">Tabla UserAgent</span><span class="sxs-lookup"><span data-stu-id="61cc4-104">UserAgent table</span></span>
 
<span data-ttu-id="61cc4-105">La tabla UserAgent es una tabla de soporte que almacena una lista de los diversos agentes de usuario que participaron en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="61cc4-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="61cc4-106">Cada registro de la tabla representa un agente de usuario</span><span class="sxs-lookup"><span data-stu-id="61cc4-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="61cc4-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="61cc4-107">**Column**</span></span>|<span data-ttu-id="61cc4-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="61cc4-108">**Data Type**</span></span>|<span data-ttu-id="61cc4-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="61cc4-109">**Key/Index**</span></span>|<span data-ttu-id="61cc4-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="61cc4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61cc4-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="61cc4-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="61cc4-112">int</span><span class="sxs-lookup"><span data-stu-id="61cc4-112">int</span></span>  <br/> |<span data-ttu-id="61cc4-113">Primary</span><span class="sxs-lookup"><span data-stu-id="61cc4-113">Primary</span></span>  <br/> |<span data-ttu-id="61cc4-114">Número único que identifica a este agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="61cc4-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="61cc4-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="61cc4-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="61cc4-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="61cc4-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="61cc4-117">Solo</span><span class="sxs-lookup"><span data-stu-id="61cc4-117">Unique</span></span>  <br/> |<span data-ttu-id="61cc4-118">Cadena de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="61cc4-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="61cc4-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="61cc4-119">**UAType**</span></span> <br/> |<span data-ttu-id="61cc4-120">smallint</span><span class="sxs-lookup"><span data-stu-id="61cc4-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="61cc4-121">1 es el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="61cc4-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="61cc4-122">2 es un servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="61cc4-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="61cc4-123">4 es Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="61cc4-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="61cc4-124">8 es teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="61cc4-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="61cc4-125">16 es la consola de Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="61cc4-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="61cc4-126">32 es la herramienta de validación de implementación (DVT).</span><span class="sxs-lookup"><span data-stu-id="61cc4-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="61cc4-127">64 es Skype empresarial Server en equipos Macintosh.</span><span class="sxs-lookup"><span data-stu-id="61cc4-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="61cc4-128">128 es operador de servidor de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="61cc4-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="61cc4-129">256 es el servicio de anuncios de conferencia.</span><span class="sxs-lookup"><span data-stu-id="61cc4-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="61cc4-130">512 es operador automático de conferencia.</span><span class="sxs-lookup"><span data-stu-id="61cc4-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="61cc4-131">1024 es una aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="61cc4-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="61cc4-132">2048 está fuera del control de voz.</span><span class="sxs-lookup"><span data-stu-id="61cc4-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

