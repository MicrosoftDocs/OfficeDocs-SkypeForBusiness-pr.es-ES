---
title: Vista multimedia
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
ms.assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
description: La vista Medios almacena información sobre un tipo de medios utilizado en una sesión punto a punto. Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 77c22246056a28cdb41a007ac0d7e2617fa00ad9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831795"
---
# <a name="media-view"></a><span data-ttu-id="032bd-105">Vista multimedia</span><span class="sxs-lookup"><span data-stu-id="032bd-105">Media view</span></span>
 
<span data-ttu-id="032bd-106">La vista Medios almacena información sobre un tipo de medios utilizado en una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="032bd-106">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="032bd-107">Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios.</span><span class="sxs-lookup"><span data-stu-id="032bd-107">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="032bd-108">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="032bd-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="032bd-p103">La vista Medios no debería utilizarse para calcular la duración de medios de una sesión. Esta vista contiene los detalles de señalización del intercambio de medios en una sesión. El intercambio de medios se realiza mediante la solicitud INVITE, y StartTime indica la hora a la que se envió la solicitud INVITE. Esta hora no implica necesariamente la hora de inicio de los medios, ya que los medios se inician solamente después de que se acepta la sesión.</span><span class="sxs-lookup"><span data-stu-id="032bd-p103">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span> 
  
<span data-ttu-id="032bd-112">La vista Multimedia contiene todas las columnas de la vista [SessionDetails](sessiondetails-0.md) además de las que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="032bd-112">The Media view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the ones listed below.</span></span>
  
|<span data-ttu-id="032bd-113">**Columna**</span><span class="sxs-lookup"><span data-stu-id="032bd-113">**Column**</span></span>|<span data-ttu-id="032bd-114">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="032bd-114">**Data Type**</span></span>|<span data-ttu-id="032bd-115">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="032bd-115">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="032bd-116">**Media**</span><span class="sxs-lookup"><span data-stu-id="032bd-116">**Media**</span></span> <br/> |<span data-ttu-id="032bd-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="032bd-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="032bd-118">Tipo de medio.</span><span class="sxs-lookup"><span data-stu-id="032bd-118">Media type.</span></span> <span data-ttu-id="032bd-119">Consulta la [tabla MediaList para](medialist.md) obtener más información.</span><span class="sxs-lookup"><span data-stu-id="032bd-119">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="032bd-120">**MediaStartTime**</span><span class="sxs-lookup"><span data-stu-id="032bd-120">**MediaStartTime**</span></span> <br/> |<span data-ttu-id="032bd-121">datetime</span><span class="sxs-lookup"><span data-stu-id="032bd-121">datetime</span></span>  <br/> |<span data-ttu-id="032bd-122">Hora a la que se envió la solicitud de medios.</span><span class="sxs-lookup"><span data-stu-id="032bd-122">Time that a media request was sent out.</span></span>  <br/> |
|<span data-ttu-id="032bd-123">**MediaEndTime**</span><span class="sxs-lookup"><span data-stu-id="032bd-123">**MediaEndTime**</span></span> <br/> |<span data-ttu-id="032bd-124">datetime</span><span class="sxs-lookup"><span data-stu-id="032bd-124">datetime</span></span>  <br/> |<span data-ttu-id="032bd-125">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="032bd-125">End time of the session.</span></span>  <br/> |
   

