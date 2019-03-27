---
title: Tabla UriTypes
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: En la tabla UriTypes contiene los diferentes tipos URI (identificador uniforme de recursos) que se supervisan en Skype para Business Server 2015.
ms.openlocfilehash: cb9c131901a322f9d22c8d29aa52a73dc27c9ea1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899648"
---
# <a name="uritypes-table"></a><span data-ttu-id="06e33-103">Tabla UriTypes</span><span class="sxs-lookup"><span data-stu-id="06e33-103">UriTypes table</span></span>
 
<span data-ttu-id="06e33-104">En la tabla UriTypes contiene los diferentes tipos URI (identificador uniforme de recursos) que se supervisan en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="06e33-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="06e33-105">Cuando se crea la CDR DB, se crean dos registros para representar PhoneUri y UserUri, y los registros se crean después de se asignan dinámicamente UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="06e33-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="06e33-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="06e33-106">**Column**</span></span>|<span data-ttu-id="06e33-107">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="06e33-107">**Data Type**</span></span>|<span data-ttu-id="06e33-108">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="06e33-108">**Key/Index**</span></span>|<span data-ttu-id="06e33-109">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="06e33-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="06e33-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="06e33-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="06e33-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="06e33-111">tinyint</span></span>  <br/> |<span data-ttu-id="06e33-112">Primary</span><span class="sxs-lookup"><span data-stu-id="06e33-112">Primary</span></span>  <br/> |<span data-ttu-id="06e33-113">Identificador único asignado a un tipo de URI.</span><span class="sxs-lookup"><span data-stu-id="06e33-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="06e33-114">Valores posibles: de 0 a 255</span><span class="sxs-lookup"><span data-stu-id="06e33-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="06e33-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="06e33-115">**UriType**</span></span> <br/> |<span data-ttu-id="06e33-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="06e33-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="06e33-117">Descripciones de los distintos tipos URI.</span><span class="sxs-lookup"><span data-stu-id="06e33-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="06e33-118">Los siguientes valores son asignados previamente:</span><span class="sxs-lookup"><span data-stu-id="06e33-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="06e33-119">1: URI del teléfono</span><span class="sxs-lookup"><span data-stu-id="06e33-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="06e33-120">0 - URI del usuario</span><span class="sxs-lookup"><span data-stu-id="06e33-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="06e33-121">Otros tipos posibles son:</span><span class="sxs-lookup"><span data-stu-id="06e33-121">Other possible types include:</span></span> <br/><span data-ttu-id="06e33-122">conferencia:uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="06e33-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="06e33-123">conferencia:audio-vídeo</span><span class="sxs-lookup"><span data-stu-id="06e33-123">conf:audio-video</span></span><br/> <span data-ttu-id="06e33-124">conf:chat</span><span class="sxs-lookup"><span data-stu-id="06e33-124">conf:chat</span></span><br/>    <span data-ttu-id="06e33-125">conferencia:foco</span><span class="sxs-lookup"><span data-stu-id="06e33-125">conf:focus</span></span><br/>   <span data-ttu-id="06e33-126">MRAS</span><span class="sxs-lookup"><span data-stu-id="06e33-126">mras</span></span><br/>
