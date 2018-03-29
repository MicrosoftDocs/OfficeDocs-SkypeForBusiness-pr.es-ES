---
title: Vista de elementos multimedia
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La vista de elementos multimedia almacena información sobre un tipo de medio utilizado en una sesión de peer-to-peer. Una sesión estaría representada por varios registros en la tabla, si se utiliza más de un tipo de medio. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 0cbcb353ec768b9d3ee66f1a10d59b5c4523acea
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="media-view"></a><span data-ttu-id="a78f6-105">Vista de elementos multimedia</span><span class="sxs-lookup"><span data-stu-id="a78f6-105">Media view</span></span>
 
<span data-ttu-id="a78f6-106">La vista de elementos multimedia almacena información sobre un tipo de medio utilizado en una sesión de peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="a78f6-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="a78f6-107">Una sesión estaría representada por varios registros en la tabla, si se utiliza más de un tipo de medio.</span><span class="sxs-lookup"><span data-stu-id="a78f6-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="a78f6-108">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a78f6-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a78f6-109">La vista de elementos multimedia no debe utilizarse para calcular la duración media de una sesión.</span><span class="sxs-lookup"><span data-stu-id="a78f6-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="a78f6-110">Esta vista contiene los detalles de señalización de intercambio de medios en una sesión.</span><span class="sxs-lookup"><span data-stu-id="a78f6-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="a78f6-111">Intercambio de medios se realiza mediante la solicitud de invitación y StartTime indica el tiempo que se ha enviado la invitación. El tiempo de invitación no significa necesariamente la media de tiempo de inicio como media se inicia después de la sesión se acepta.</span><span class="sxs-lookup"><span data-stu-id="a78f6-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="a78f6-112">La vista de elementos multimedia contiene todas las columnas en la [vista SessionDetails](sessiondetails-0.md) además los mencionados a continuación.</span><span class="sxs-lookup"><span data-stu-id="a78f6-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="a78f6-113">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a78f6-113">**Column**</span></span>|<span data-ttu-id="a78f6-114">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="a78f6-114">**Data Type**</span></span>|<span data-ttu-id="a78f6-115">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="a78f6-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a78f6-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="a78f6-116">**Media**</span></span> <br/> |<span data-ttu-id="a78f6-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a78f6-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a78f6-118">Tipo de medio.</span><span class="sxs-lookup"><span data-stu-id="a78f6-118">Media type.</span></span> <span data-ttu-id="a78f6-119">Consulte la [tabla de MediaList](medialist.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a78f6-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a78f6-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="a78f6-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="a78f6-121">datetime</span><span class="sxs-lookup"><span data-stu-id="a78f6-121">datetime</span></span>  <br/> |<span data-ttu-id="a78f6-122">Hora en que se ha enviado una solicitud de los medios de comunicación.</span><span class="sxs-lookup"><span data-stu-id="a78f6-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="a78f6-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="a78f6-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="a78f6-124">datetime</span><span class="sxs-lookup"><span data-stu-id="a78f6-124">datetime</span></span>  <br/> |<span data-ttu-id="a78f6-125">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="a78f6-125">End time of the session.</span></span>  <br/> |
   

