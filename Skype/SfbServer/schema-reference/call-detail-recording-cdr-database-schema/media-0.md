---
title: Vista de elementos multimedia
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La vista multimedia almacena información sobre un tipo de medio usado en una sesión de punto a punto. Una sesión estaría representada por varios registros de la tabla, si se usa más de un tipo de medio. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 26ef344b5fade02168fb8737fe00049e44e24892
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815058"
---
# <a name="media-view"></a><span data-ttu-id="de3a0-105">Vista de elementos multimedia</span><span class="sxs-lookup"><span data-stu-id="de3a0-105">Media view</span></span>
 
<span data-ttu-id="de3a0-106">La vista multimedia almacena información sobre un tipo de medio usado en una sesión de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="de3a0-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="de3a0-107">Una sesión estaría representada por varios registros de la tabla, si se usa más de un tipo de medio.</span><span class="sxs-lookup"><span data-stu-id="de3a0-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="de3a0-108">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de3a0-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="de3a0-109">La vista de elementos multimedia no debe usarse para calcular la duración multimedia de una sesión.</span><span class="sxs-lookup"><span data-stu-id="de3a0-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="de3a0-110">Esta vista contiene los detalles de señalización de intercambio de medios en una sesión.</span><span class="sxs-lookup"><span data-stu-id="de3a0-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="de3a0-111">El intercambio de medios se realiza mediante la solicitud INVITE y StartTime indica el momento en que se envió la invitación. La hora de la invitación no significa necesariamente la hora de inicio del medio, porque los medios solo se inician una vez que se acepta la sesión.</span><span class="sxs-lookup"><span data-stu-id="de3a0-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="de3a0-112">La vista de elementos multimedia contiene todas las columnas de la [vista SessionDetails](sessiondetails-0.md) , además de las que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="de3a0-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="de3a0-113">**Columna**</span><span class="sxs-lookup"><span data-stu-id="de3a0-113">**Column**</span></span>|<span data-ttu-id="de3a0-114">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="de3a0-114">**Data Type**</span></span>|<span data-ttu-id="de3a0-115">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="de3a0-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="de3a0-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="de3a0-116">**Media**</span></span> <br/> |<span data-ttu-id="de3a0-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="de3a0-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="de3a0-118">Tipo de medio.</span><span class="sxs-lookup"><span data-stu-id="de3a0-118">Media type.</span></span> <span data-ttu-id="de3a0-119">Para obtener más información, consulte la [tabla](medialist.md) de la información.</span><span class="sxs-lookup"><span data-stu-id="de3a0-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="de3a0-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="de3a0-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="de3a0-121">datetime</span><span class="sxs-lookup"><span data-stu-id="de3a0-121">datetime</span></span>  <br/> |<span data-ttu-id="de3a0-122">Hora en que se envió una solicitud de medios.</span><span class="sxs-lookup"><span data-stu-id="de3a0-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="de3a0-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="de3a0-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="de3a0-124">datetime</span><span class="sxs-lookup"><span data-stu-id="de3a0-124">datetime</span></span>  <br/> |<span data-ttu-id="de3a0-125">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="de3a0-125">End time of the session.</span></span>  <br/> |
   

