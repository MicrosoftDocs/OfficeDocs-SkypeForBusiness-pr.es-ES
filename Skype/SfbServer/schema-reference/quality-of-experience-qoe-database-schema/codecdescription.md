---
title: Tabla CodecDescription
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
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La tabla CodecDescription asigna identificadores de códec únicos a su códec correspondiente. Los códecs se usan para codificar las señales digitales de transmisión y difusión y, después, descodificar esas señales para la reproducción. Esta tabla se introdujo en Microsoft Lync Server 2013
ms.openlocfilehash: 53410b1bdf4875bd66a80c107dc56c5316fc30a3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810368"
---
# <a name="codecdescription-table"></a><span data-ttu-id="fd7dc-105">Tabla CodecDescription</span><span class="sxs-lookup"><span data-stu-id="fd7dc-105">CodecDescription table</span></span>
 
<span data-ttu-id="fd7dc-106">La tabla CodecDescription asigna identificadores de códec únicos a su códec correspondiente.</span><span class="sxs-lookup"><span data-stu-id="fd7dc-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="fd7dc-107">Los códecs se usan para codificar las señales digitales de transmisión y difusión y, después, descodificar esas señales para la reproducción.</span><span class="sxs-lookup"><span data-stu-id="fd7dc-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="fd7dc-108">Esta tabla se introdujo en Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd7dc-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="fd7dc-109">**Columna**</span><span class="sxs-lookup"><span data-stu-id="fd7dc-109">**Column**</span></span>|<span data-ttu-id="fd7dc-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="fd7dc-110">**Data Type**</span></span>|<span data-ttu-id="fd7dc-111">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="fd7dc-111">**Key/Index**</span></span>|<span data-ttu-id="fd7dc-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="fd7dc-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd7dc-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="fd7dc-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="fd7dc-114">smallint</span><span class="sxs-lookup"><span data-stu-id="fd7dc-114">smallint</span></span>  <br/> |<span data-ttu-id="fd7dc-115">Primary</span><span class="sxs-lookup"><span data-stu-id="fd7dc-115">Primary</span></span>  <br/> |<span data-ttu-id="fd7dc-116">Identificador único asignado al códec.</span><span class="sxs-lookup"><span data-stu-id="fd7dc-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="fd7dc-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="fd7dc-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="fd7dc-118">VARCHAR (256)</span><span class="sxs-lookup"><span data-stu-id="fd7dc-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="fd7dc-119">Solo</span><span class="sxs-lookup"><span data-stu-id="fd7dc-119">Unique</span></span>  <br/> |<span data-ttu-id="fd7dc-120">Descripción única del códec correspondiente al CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="fd7dc-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

