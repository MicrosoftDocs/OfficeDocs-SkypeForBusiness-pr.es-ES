---
title: Tabla UserAgent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: En la tabla UserAgent es una tabla de apoyo que almacena una lista de los distintos agentes de usuario que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa a un agente de usuario
ms.openlocfilehash: 17cb395569e8a634925be27705b878b104a3b70a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893107"
---
# <a name="useragent-table"></a><span data-ttu-id="d153e-104">Tabla UserAgent</span><span class="sxs-lookup"><span data-stu-id="d153e-104">UserAgent table</span></span>
 
<span data-ttu-id="d153e-105">En la tabla UserAgent es una tabla de apoyo que almacena una lista de los distintos agentes de usuario que han participado en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d153e-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="d153e-106">Cada registro de la tabla representa a un agente de usuario</span><span class="sxs-lookup"><span data-stu-id="d153e-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="d153e-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d153e-107">**Column**</span></span>|<span data-ttu-id="d153e-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d153e-108">**Data Type**</span></span>|<span data-ttu-id="d153e-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="d153e-109">**Key/Index**</span></span>|<span data-ttu-id="d153e-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d153e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d153e-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="d153e-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="d153e-112">int</span><span class="sxs-lookup"><span data-stu-id="d153e-112">int</span></span>  <br/> |<span data-ttu-id="d153e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d153e-113">Primary</span></span>  <br/> |<span data-ttu-id="d153e-114">Número único que identifica a este agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="d153e-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="d153e-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="d153e-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="d153e-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d153e-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d153e-117">Único</span><span class="sxs-lookup"><span data-stu-id="d153e-117">Unique</span></span>  <br/> |<span data-ttu-id="d153e-118">Cadena de agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="d153e-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="d153e-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="d153e-119">**UAType**</span></span> <br/> |<span data-ttu-id="d153e-120">smallint</span><span class="sxs-lookup"><span data-stu-id="d153e-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="d153e-121">1 es el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d153e-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="d153e-122">2 es / servidor de conferencia A/v.</span><span class="sxs-lookup"><span data-stu-id="d153e-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="d153e-123">4 es Skype para la empresa.</span><span class="sxs-lookup"><span data-stu-id="d153e-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="d153e-124">8 es teléfono IP.</span><span class="sxs-lookup"><span data-stu-id="d153e-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="d153e-125">16 es consola de Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="d153e-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="d153e-126">32 es la herramienta de validación de implementación (DVT).</span><span class="sxs-lookup"><span data-stu-id="d153e-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="d153e-127">64 es Skype para Business Server en equipos Macintosh.</span><span class="sxs-lookup"><span data-stu-id="d153e-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="d153e-128">128 es Skype para Business Server Attendant.</span><span class="sxs-lookup"><span data-stu-id="d153e-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="d153e-129">256 es el servicio de anuncio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d153e-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="d153e-130">512 es operador automático de conferencia.</span><span class="sxs-lookup"><span data-stu-id="d153e-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="d153e-131">1024 es la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="d153e-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="d153e-132">2048 es Control de voz externa.</span><span class="sxs-lookup"><span data-stu-id="d153e-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

