---
title: Tabla UriTypes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: En la tabla UriTypes contiene los diferentes tipos URI (identificador uniforme de recursos) que se supervisan en Skype para Business Server 2015.
ms.openlocfilehash: 72704715ff5e5fd3a354b75b0aa6baff45ecea54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930272"
---
# <a name="uritypes-table"></a><span data-ttu-id="2b015-103">Tabla UriTypes</span><span class="sxs-lookup"><span data-stu-id="2b015-103">UriTypes table</span></span>
 
<span data-ttu-id="2b015-104">En la tabla UriTypes contiene los diferentes tipos URI (identificador uniforme de recursos) que se supervisan en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2b015-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="2b015-105">Cuando se crea la CDR DB, se crean dos registros para representar PhoneUri y UserUri, y los registros se crean después de se asignan dinámicamente UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="2b015-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="2b015-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2b015-106">**Column**</span></span>|<span data-ttu-id="2b015-107">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="2b015-107">**Data Type**</span></span>|<span data-ttu-id="2b015-108">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="2b015-108">**Key/Index**</span></span>|<span data-ttu-id="2b015-109">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="2b015-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b015-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="2b015-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="2b015-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="2b015-111">tinyint</span></span>  <br/> |<span data-ttu-id="2b015-112">Primary</span><span class="sxs-lookup"><span data-stu-id="2b015-112">Primary</span></span>  <br/> |<span data-ttu-id="2b015-113">Identificador único asignado a un tipo de URI.</span><span class="sxs-lookup"><span data-stu-id="2b015-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="2b015-114">Valores posibles: de 0 a 255</span><span class="sxs-lookup"><span data-stu-id="2b015-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="2b015-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="2b015-115">**UriType**</span></span> <br/> |<span data-ttu-id="2b015-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2b015-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="2b015-117">Descripciones de los distintos tipos URI.</span><span class="sxs-lookup"><span data-stu-id="2b015-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="2b015-118">Los siguientes valores son asignados previamente:</span><span class="sxs-lookup"><span data-stu-id="2b015-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="2b015-119">1: URI del teléfono</span><span class="sxs-lookup"><span data-stu-id="2b015-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="2b015-120">0 - URI del usuario</span><span class="sxs-lookup"><span data-stu-id="2b015-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="2b015-121">Otros tipos posibles son:</span><span class="sxs-lookup"><span data-stu-id="2b015-121">Other possible types include:</span></span> <br/><span data-ttu-id="2b015-122">conferencia:uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="2b015-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="2b015-123">conferencia:audio-vídeo</span><span class="sxs-lookup"><span data-stu-id="2b015-123">conf:audio-video</span></span><br/> <span data-ttu-id="2b015-124">conf:chat</span><span class="sxs-lookup"><span data-stu-id="2b015-124">conf:chat</span></span><br/>    <span data-ttu-id="2b015-125">conferencia:foco</span><span class="sxs-lookup"><span data-stu-id="2b015-125">conf:focus</span></span><br/>   <span data-ttu-id="2b015-126">MRAS</span><span class="sxs-lookup"><span data-stu-id="2b015-126">mras</span></span><br/>
