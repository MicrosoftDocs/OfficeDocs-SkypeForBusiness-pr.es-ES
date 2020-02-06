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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La tabla UserAgent es una tabla de soporte que almacena una lista de los diversos agentes de usuario que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa un agente de usuario
ms.openlocfilehash: d0a287881a352801d237894c5b150b5a08d91fc8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805058"
---
# <a name="useragent-table"></a><span data-ttu-id="d8067-104">Tabla UserAgent</span><span class="sxs-lookup"><span data-stu-id="d8067-104">UserAgent table</span></span>
 
<span data-ttu-id="d8067-105">La tabla UserAgent es una tabla de soporte que almacena una lista de los diversos agentes de usuario que participaron en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d8067-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="d8067-106">Cada registro de la tabla representa un agente de usuario</span><span class="sxs-lookup"><span data-stu-id="d8067-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="d8067-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d8067-107">**Column**</span></span>|<span data-ttu-id="d8067-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d8067-108">**Data Type**</span></span>|<span data-ttu-id="d8067-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d8067-109">**Key/Index**</span></span>|<span data-ttu-id="d8067-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d8067-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d8067-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="d8067-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="d8067-112">int</span><span class="sxs-lookup"><span data-stu-id="d8067-112">int</span></span>  <br/> |<span data-ttu-id="d8067-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d8067-113">Primary</span></span>  <br/> |<span data-ttu-id="d8067-114">Número único que identifica a este agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="d8067-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="d8067-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="d8067-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="d8067-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d8067-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d8067-117">Solo</span><span class="sxs-lookup"><span data-stu-id="d8067-117">Unique</span></span>  <br/> |<span data-ttu-id="d8067-118">Cadena de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="d8067-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="d8067-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="d8067-119">**UAType**</span></span> <br/> |<span data-ttu-id="d8067-120">smallint</span><span class="sxs-lookup"><span data-stu-id="d8067-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="d8067-121">1 es el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d8067-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="d8067-122">2 es un servidor de conferencia A/V.</span><span class="sxs-lookup"><span data-stu-id="d8067-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="d8067-123">4 es Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d8067-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="d8067-124">8 es teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="d8067-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="d8067-125">16 es la consola de Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="d8067-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="d8067-126">32 es la herramienta de validación de implementación (DVT).</span><span class="sxs-lookup"><span data-stu-id="d8067-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="d8067-127">64 es Skype empresarial Server en equipos Macintosh.</span><span class="sxs-lookup"><span data-stu-id="d8067-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="d8067-128">128 es operador de servidor de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="d8067-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="d8067-129">256 es el servicio de anuncios de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d8067-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="d8067-130">512 es operador automático de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d8067-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="d8067-131">1024 es una aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="d8067-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="d8067-132">2048 está fuera del control de voz.</span><span class="sxs-lookup"><span data-stu-id="d8067-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

