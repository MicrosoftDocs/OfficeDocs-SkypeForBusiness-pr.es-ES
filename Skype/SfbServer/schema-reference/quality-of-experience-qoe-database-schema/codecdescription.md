---
title: Tabla CodecDescription
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: La tabla CodecDescription asigna identificadores de códec únicos a sus códecs correspondientes. Los códecs se utilizan para codificar señales digitales para la transmisión y la difusión, así como para la posterior descodificación de dichas señales para su reproducción. Esta tabla se introdujo en Microsoft Lync Server 2013
ms.openlocfilehash: 95ba2218ff20aa6c67de6f60d6966916b6648a58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831350"
---
# <a name="codecdescription-table"></a><span data-ttu-id="c3b8f-105">Tabla CodecDescription</span><span class="sxs-lookup"><span data-stu-id="c3b8f-105">CodecDescription table</span></span>
 
<span data-ttu-id="c3b8f-106">La tabla CodecDescription asigna identificadores de códec únicos a sus códecs correspondientes.</span><span class="sxs-lookup"><span data-stu-id="c3b8f-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="c3b8f-107">Los códecs se utilizan para codificar señales digitales para la transmisión y la difusión, así como para la posterior descodificación de dichas señales para su reproducción.</span><span class="sxs-lookup"><span data-stu-id="c3b8f-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="c3b8f-108">Esta tabla se introdujo en Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3b8f-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="c3b8f-109">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c3b8f-109">**Column**</span></span>|<span data-ttu-id="c3b8f-110">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="c3b8f-110">**Data Type**</span></span>|<span data-ttu-id="c3b8f-111">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="c3b8f-111">**Key/Index**</span></span>|<span data-ttu-id="c3b8f-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="c3b8f-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c3b8f-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="c3b8f-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="c3b8f-114">smallint</span><span class="sxs-lookup"><span data-stu-id="c3b8f-114">smallint</span></span>  <br/> |<span data-ttu-id="c3b8f-115">Principal</span><span class="sxs-lookup"><span data-stu-id="c3b8f-115">Primary</span></span>  <br/> |<span data-ttu-id="c3b8f-116">Identificador único asignado a códec.</span><span class="sxs-lookup"><span data-stu-id="c3b8f-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="c3b8f-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="c3b8f-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="c3b8f-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="c3b8f-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="c3b8f-119">Única</span><span class="sxs-lookup"><span data-stu-id="c3b8f-119">Unique</span></span>  <br/> |<span data-ttu-id="c3b8f-120">Descripción única del códec que corresponde a CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="c3b8f-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

