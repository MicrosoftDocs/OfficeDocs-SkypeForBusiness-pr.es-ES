---
title: Tabla UriTypes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La tabla UriTypes contiene los diferentes tipos URI (identificador uniforme de recursos) supervisados en Skype empresarial Server 2015.
ms.openlocfilehash: 5ad8e1d0432aff3278f897fbe82d3759ad3c95e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295751"
---
# <a name="uritypes-table"></a><span data-ttu-id="51c8a-103">Tabla UriTypes</span><span class="sxs-lookup"><span data-stu-id="51c8a-103">UriTypes table</span></span>
 
<span data-ttu-id="51c8a-104">La tabla UriTypes contiene los diferentes tipos URI (identificador uniforme de recursos) supervisados en Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="51c8a-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="51c8a-105">Cuando se crea la base de la BD de CDR, se crean dos registros para representar PhoneUri y UserUri, y los registros creados después de que se hayan asignado de forma dinámica UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="51c8a-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="51c8a-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="51c8a-106">**Column**</span></span>|<span data-ttu-id="51c8a-107">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="51c8a-107">**Data Type**</span></span>|<span data-ttu-id="51c8a-108">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="51c8a-108">**Key/Index**</span></span>|<span data-ttu-id="51c8a-109">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="51c8a-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="51c8a-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="51c8a-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="51c8a-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="51c8a-111">tinyint</span></span>  <br/> |<span data-ttu-id="51c8a-112">Primary</span><span class="sxs-lookup"><span data-stu-id="51c8a-112">Primary</span></span>  <br/> |<span data-ttu-id="51c8a-113">Identificador único asignado a un tipo de URI.</span><span class="sxs-lookup"><span data-stu-id="51c8a-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="51c8a-114">Valores posibles: 0 a 255</span><span class="sxs-lookup"><span data-stu-id="51c8a-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="51c8a-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="51c8a-115">**UriType**</span></span> <br/> |<span data-ttu-id="51c8a-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="51c8a-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="51c8a-117">Descripciones de los distintos tipos de URI.</span><span class="sxs-lookup"><span data-stu-id="51c8a-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="51c8a-118">Los valores siguientes se han asignado previamente:</span><span class="sxs-lookup"><span data-stu-id="51c8a-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="51c8a-119">URI de 1 teléfono</span><span class="sxs-lookup"><span data-stu-id="51c8a-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="51c8a-120">0: URI de usuario</span><span class="sxs-lookup"><span data-stu-id="51c8a-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="51c8a-121">Otros tipos posibles son:</span><span class="sxs-lookup"><span data-stu-id="51c8a-121">Other possible types include:</span></span> <br/><span data-ttu-id="51c8a-122">conferencia:uso compartido de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="51c8a-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="51c8a-123">conferencia:audio-vídeo</span><span class="sxs-lookup"><span data-stu-id="51c8a-123">conf:audio-video</span></span><br/> <span data-ttu-id="51c8a-124">conf: chat</span><span class="sxs-lookup"><span data-stu-id="51c8a-124">conf:chat</span></span><br/>    <span data-ttu-id="51c8a-125">conferencia:foco</span><span class="sxs-lookup"><span data-stu-id="51c8a-125">conf:focus</span></span><br/>   <span data-ttu-id="51c8a-126">mras</span><span class="sxs-lookup"><span data-stu-id="51c8a-126">mras</span></span><br/>
