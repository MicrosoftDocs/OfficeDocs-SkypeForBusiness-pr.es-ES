---
title: Tabla CodecDescription
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La tabla CodecDescription asigna identificadores de códec único su códec correspondiente. Los códecs se utilizan para codificar las señales digitales para la transmisión y difusión y después descifran las señales para la reproducción. Esta tabla se introdujo en Microsoft Lync Server 2013
ms.openlocfilehash: 49dea2867ef7614fab3015efbd24e6ec47da8c55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="codecdescription-table"></a><span data-ttu-id="a26a7-105">Tabla CodecDescription</span><span class="sxs-lookup"><span data-stu-id="a26a7-105">CodecDescription table</span></span>
 
<span data-ttu-id="a26a7-106">La tabla CodecDescription asigna identificadores de códec único su códec correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a26a7-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="a26a7-107">Los códecs se utilizan para codificar las señales digitales para la transmisión y difusión y después descifran las señales para la reproducción.</span><span class="sxs-lookup"><span data-stu-id="a26a7-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="a26a7-108">Esta tabla se introdujo en Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a26a7-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="a26a7-109">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a26a7-109">**Column**</span></span>|<span data-ttu-id="a26a7-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="a26a7-110">**Data Type**</span></span>|<span data-ttu-id="a26a7-111">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="a26a7-111">**Key/Index**</span></span>|<span data-ttu-id="a26a7-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="a26a7-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a26a7-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="a26a7-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="a26a7-114">smallint</span><span class="sxs-lookup"><span data-stu-id="a26a7-114">smallint</span></span>  <br/> |<span data-ttu-id="a26a7-115">Primary</span><span class="sxs-lookup"><span data-stu-id="a26a7-115">Primary</span></span>  <br/> |<span data-ttu-id="a26a7-116">Identificador único asignado al códec.</span><span class="sxs-lookup"><span data-stu-id="a26a7-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="a26a7-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="a26a7-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="a26a7-118">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="a26a7-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="a26a7-119">Único</span><span class="sxs-lookup"><span data-stu-id="a26a7-119">Unique</span></span>  <br/> |<span data-ttu-id="a26a7-120">Descripción única del códec correspondiente a la CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="a26a7-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

