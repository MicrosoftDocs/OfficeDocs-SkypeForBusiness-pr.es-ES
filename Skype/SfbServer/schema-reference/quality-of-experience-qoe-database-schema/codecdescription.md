---
title: Tabla CodecDescription
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La tabla CodecDescription asigna los identificadores de códecs únicos al códec correspondiente. Los códecs se utilizan para codificar las señales digitales para la transmisión y difusión y, a continuación, descodificar esas señales para la reproducción. En esta tabla se introdujo en Microsoft Lync Server 2013
ms.openlocfilehash: 9881c802e332801d4990bf01894d5f8b68150fc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920106"
---
# <a name="codecdescription-table"></a><span data-ttu-id="73e71-105">Tabla CodecDescription</span><span class="sxs-lookup"><span data-stu-id="73e71-105">CodecDescription table</span></span>
 
<span data-ttu-id="73e71-106">La tabla CodecDescription asigna los identificadores de códecs únicos al códec correspondiente.</span><span class="sxs-lookup"><span data-stu-id="73e71-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="73e71-107">Los códecs se utilizan para codificar las señales digitales para la transmisión y difusión y, a continuación, descodificar esas señales para la reproducción.</span><span class="sxs-lookup"><span data-stu-id="73e71-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="73e71-108">En esta tabla se introdujo en Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73e71-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="73e71-109">**Columna**</span><span class="sxs-lookup"><span data-stu-id="73e71-109">**Column**</span></span>|<span data-ttu-id="73e71-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="73e71-110">**Data Type**</span></span>|<span data-ttu-id="73e71-111">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="73e71-111">**Key/Index**</span></span>|<span data-ttu-id="73e71-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="73e71-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="73e71-113">**A CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="73e71-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="73e71-114">smallint</span><span class="sxs-lookup"><span data-stu-id="73e71-114">smallint</span></span>  <br/> |<span data-ttu-id="73e71-115">Primary</span><span class="sxs-lookup"><span data-stu-id="73e71-115">Primary</span></span>  <br/> |<span data-ttu-id="73e71-116">Identificador único asignado a códec.</span><span class="sxs-lookup"><span data-stu-id="73e71-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="73e71-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="73e71-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="73e71-118">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="73e71-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="73e71-119">Único</span><span class="sxs-lookup"><span data-stu-id="73e71-119">Unique</span></span>  <br/> |<span data-ttu-id="73e71-120">Descripción única del códec correspondiente a CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="73e71-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

