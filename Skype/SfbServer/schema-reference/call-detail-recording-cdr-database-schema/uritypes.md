---
title: Tabla UriTypes
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: La tabla UriTypes contiene los diferentes tipos de URI (identificador uniforme de recursos) supervisados en Skype Empresarial Server 2015.
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831690"
---
# <a name="uritypes-table"></a><span data-ttu-id="dc01a-103">Tabla UriTypes</span><span class="sxs-lookup"><span data-stu-id="dc01a-103">UriTypes table</span></span>
 
<span data-ttu-id="dc01a-104">La tabla UriTypes contiene los diferentes tipos de URI (identificador uniforme de recursos) supervisados en Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="dc01a-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="dc01a-105">Cuando se crea la base de datos de CDR, se crean dos registros para representar PhoneUri y UserUri, y los registros creados después se asignan dinámicamente UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="dc01a-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="dc01a-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="dc01a-106">**Column**</span></span>|<span data-ttu-id="dc01a-107">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="dc01a-107">**Data Type**</span></span>|<span data-ttu-id="dc01a-108">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="dc01a-108">**Key/Index**</span></span>|<span data-ttu-id="dc01a-109">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="dc01a-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dc01a-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="dc01a-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="dc01a-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="dc01a-111">tinyint</span></span>  <br/> |<span data-ttu-id="dc01a-112">Principal</span><span class="sxs-lookup"><span data-stu-id="dc01a-112">Primary</span></span>  <br/> |<span data-ttu-id="dc01a-113">Identificador único asignado a un tipo de URI.</span><span class="sxs-lookup"><span data-stu-id="dc01a-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="dc01a-114">Valores posibles: de 0 a 255</span><span class="sxs-lookup"><span data-stu-id="dc01a-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="dc01a-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="dc01a-115">**UriType**</span></span> <br/> |<span data-ttu-id="dc01a-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="dc01a-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="dc01a-117">Descripciones de diferentes tipos de URI.</span><span class="sxs-lookup"><span data-stu-id="dc01a-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="dc01a-118">Los siguientes valores están asignados previamente:</span><span class="sxs-lookup"><span data-stu-id="dc01a-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="dc01a-119">1- Uri de teléfono</span><span class="sxs-lookup"><span data-stu-id="dc01a-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="dc01a-120">0: Uri de usuario</span><span class="sxs-lookup"><span data-stu-id="dc01a-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="dc01a-121">Otros tipos posibles son:</span><span class="sxs-lookup"><span data-stu-id="dc01a-121">Other possible types include:</span></span> <br/><span data-ttu-id="dc01a-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="dc01a-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="dc01a-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="dc01a-123">conf:audio-video</span></span><br/> <span data-ttu-id="dc01a-124">conf:chat</span><span class="sxs-lookup"><span data-stu-id="dc01a-124">conf:chat</span></span><br/>    <span data-ttu-id="dc01a-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="dc01a-125">conf:focus</span></span><br/>   <span data-ttu-id="dc01a-126">mras</span><span class="sxs-lookup"><span data-stu-id="dc01a-126">mras</span></span><br/>
