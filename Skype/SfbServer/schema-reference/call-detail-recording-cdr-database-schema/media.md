---
title: Tabla Multimedia
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Cada registro representa un tipo de medios utilizado en una sesión punto a punto. Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios.
ms.openlocfilehash: ce5b5a2b312307e608367279e4e871ed03063860
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800110"
---
# <a name="media-table"></a><span data-ttu-id="099a3-104">Tabla Multimedia</span><span class="sxs-lookup"><span data-stu-id="099a3-104">Media table</span></span>
 
<span data-ttu-id="099a3-p102">Cada registro representa un tipo de medios utilizado en una sesión punto a punto. Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios.</span><span class="sxs-lookup"><span data-stu-id="099a3-p102">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="099a3-p103">No debe usarse la tabla Media para calcular la duración de los medios de una sesión. Esta tabla contiene los detalles de señalización del intercambio de medios en una sesión. El intercambio de medios se realiza mediante la solicitud INVITE, y StartTime indica la hora a la que se envió la solicitud INVITE. Esta hora no implica necesariamente la hora de inicio de los medios, ya que los medios se inician solamente después de que el participante de la sesión acepta la sesión. Por lo general, EndTime implica la hora de finalización de esta sesión.</span><span class="sxs-lookup"><span data-stu-id="099a3-p103">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="099a3-111">**Columna**</span><span class="sxs-lookup"><span data-stu-id="099a3-111">**Column**</span></span>|<span data-ttu-id="099a3-112">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="099a3-112">**Data Type**</span></span>|<span data-ttu-id="099a3-113">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="099a3-113">**Key/Index**</span></span>|<span data-ttu-id="099a3-114">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="099a3-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="099a3-115">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="099a3-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="099a3-116">datetime</span><span class="sxs-lookup"><span data-stu-id="099a3-116">datetime</span></span>  <br/> |<span data-ttu-id="099a3-117">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="099a3-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="099a3-118">Hora de la solicitud de sesión.</span><span class="sxs-lookup"><span data-stu-id="099a3-118">Time of session request.</span></span> <span data-ttu-id="099a3-119">Se usa junto con **SessionIdSeq** para identificar una sesión de manera exclusiva.</span><span class="sxs-lookup"><span data-stu-id="099a3-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="099a3-120">Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="099a3-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="099a3-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="099a3-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="099a3-122">entero</span><span class="sxs-lookup"><span data-stu-id="099a3-122">int</span></span>  <br/> |<span data-ttu-id="099a3-123">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="099a3-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="099a3-124">Número del identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="099a3-124">ID number to identify the session.</span></span> <span data-ttu-id="099a3-125">Se usa en combinación con **SessionIdTime** para identificar de forma única una sesión.</span><span class="sxs-lookup"><span data-stu-id="099a3-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="099a3-126">Consulte la [tabla Cuadros de diálogo en Skype Empresarial Server 2015](dialogs.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="099a3-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="099a3-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="099a3-127">**MediaId**</span></span> <br/> |<span data-ttu-id="099a3-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="099a3-128">tinyint</span></span>  <br/> |<span data-ttu-id="099a3-129">Principal, Exterior</span><span class="sxs-lookup"><span data-stu-id="099a3-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="099a3-130">Número único que identifica este tipo de medios.</span><span class="sxs-lookup"><span data-stu-id="099a3-130">Unique number identifying this media type.</span></span> <span data-ttu-id="099a3-131">Consulta la [tabla MediaList para](medialist.md) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="099a3-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="099a3-132">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="099a3-132">**StartTime**</span></span> <br/> |<span data-ttu-id="099a3-133">datetime</span><span class="sxs-lookup"><span data-stu-id="099a3-133">datetime</span></span>  <br/> |<span data-ttu-id="099a3-134">Principal</span><span class="sxs-lookup"><span data-stu-id="099a3-134">Primary</span></span>  <br/> |<span data-ttu-id="099a3-p107">Hora a la que se envió una solicitud de medios, no la hora de inicio real de los medios. **StartTime** incluye el tiempo de establecimiento de la sesión.</span><span class="sxs-lookup"><span data-stu-id="099a3-p107">This is the time that a media request was sent out, not the real media start time. **StartTime** includes the session setup time. </span></span><br/> |
|<span data-ttu-id="099a3-137">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="099a3-137">**EndTime**</span></span> <br/> |<span data-ttu-id="099a3-138">datetime</span><span class="sxs-lookup"><span data-stu-id="099a3-138">datetime</span></span>  <br/> ||<span data-ttu-id="099a3-139">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="099a3-139">This is the end time of the session.</span></span>  <br/> |
   

