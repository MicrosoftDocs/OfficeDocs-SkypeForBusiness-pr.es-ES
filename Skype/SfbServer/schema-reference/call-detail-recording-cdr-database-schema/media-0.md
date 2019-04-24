---
title: Vista de elementos multimedia
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La vista de elementos multimedia almacena información acerca de un tipo de medio utilizado en una sesión de punto a punto. Una sesión estaría representada por varios registros en la tabla, si se usa más de un tipo de medios. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 148f74117ba42849d58e4012e4e963b3ef1b7a3c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212926"
---
# <a name="media-view"></a><span data-ttu-id="815c7-105">Vista de elementos multimedia</span><span class="sxs-lookup"><span data-stu-id="815c7-105">Media view</span></span>
 
<span data-ttu-id="815c7-106">La vista de elementos multimedia almacena información acerca de un tipo de medio utilizado en una sesión de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="815c7-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="815c7-107">Una sesión estaría representada por varios registros en la tabla, si se usa más de un tipo de medios.</span><span class="sxs-lookup"><span data-stu-id="815c7-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="815c7-108">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="815c7-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="815c7-109">La vista de elementos multimedia no debe usarse para calcular la duración media de una sesión.</span><span class="sxs-lookup"><span data-stu-id="815c7-109">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="815c7-110">Esta vista contiene los detalles de señalización de intercambio de medios en una sesión.</span><span class="sxs-lookup"><span data-stu-id="815c7-110">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="815c7-111">Intercambio de medios se realiza mediante la solicitud INVITE y StartTime indica la hora en que se envió la invitación de la. El tiempo de invitar no significa necesariamente los medios de inicio de tiempo, debido a que los medios se inicia sólo después de la sesión se acepta.</span><span class="sxs-lookup"><span data-stu-id="815c7-111">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="815c7-112">La vista de elementos multimedia todas las columnas en la [vista SessionDetails](sessiondetails-0.md) contiene además de los que aparecen a continuación.</span><span class="sxs-lookup"><span data-stu-id="815c7-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="815c7-113">**Columna**</span><span class="sxs-lookup"><span data-stu-id="815c7-113">**Column**</span></span>|<span data-ttu-id="815c7-114">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="815c7-114">**Data Type**</span></span>|<span data-ttu-id="815c7-115">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="815c7-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="815c7-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="815c7-116">**Media**</span></span> <br/> |<span data-ttu-id="815c7-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="815c7-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="815c7-118">Tipo de medio.</span><span class="sxs-lookup"><span data-stu-id="815c7-118">Media type.</span></span> <span data-ttu-id="815c7-119">Consulte la [tabla MediaList](medialist.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="815c7-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="815c7-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="815c7-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="815c7-121">datetime</span><span class="sxs-lookup"><span data-stu-id="815c7-121">datetime</span></span>  <br/> |<span data-ttu-id="815c7-122">Hora en que se ha enviado una solicitud de medios.</span><span class="sxs-lookup"><span data-stu-id="815c7-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="815c7-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="815c7-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="815c7-124">datetime</span><span class="sxs-lookup"><span data-stu-id="815c7-124">datetime</span></span>  <br/> |<span data-ttu-id="815c7-125">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="815c7-125">End time of the session.</span></span>  <br/> |
   

