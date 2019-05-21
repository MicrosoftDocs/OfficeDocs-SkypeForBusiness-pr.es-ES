---
title: Vista ClientVersions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vista ClientVersions almacena información sobre los diversos tipos y versiones de los clientes que participaron en sesiones registradas en la base de datos. Cada registro de la vista representa una versión de cliente. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296542"
---
# <a name="clientversions-view"></a><span data-ttu-id="ac52b-105">Vista ClientVersions</span><span class="sxs-lookup"><span data-stu-id="ac52b-105">ClientVersions view</span></span>
 
<span data-ttu-id="ac52b-106">La vista ClientVersions almacena información sobre los diversos tipos y versiones de los clientes que participaron en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ac52b-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ac52b-107">Cada registro de la vista representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="ac52b-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="ac52b-108">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ac52b-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ac52b-109">Es posible que haya varios registros para determinadas columnas.</span><span class="sxs-lookup"><span data-stu-id="ac52b-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="ac52b-110">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ac52b-110">**Column**</span></span>|<span data-ttu-id="ac52b-111">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="ac52b-111">**Data Type**</span></span>|<span data-ttu-id="ac52b-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ac52b-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ac52b-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="ac52b-113">**VersionId**</span></span> <br/> |<span data-ttu-id="ac52b-114">int</span><span class="sxs-lookup"><span data-stu-id="ac52b-114">int</span></span>  <br/> |<span data-ttu-id="ac52b-115">Número único que identifica este tipo de cliente y versión.</span><span class="sxs-lookup"><span data-stu-id="ac52b-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="ac52b-116">**Versión**</span><span class="sxs-lookup"><span data-stu-id="ac52b-116">**Version**</span></span> <br/> |<span data-ttu-id="ac52b-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ac52b-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ac52b-118">Representa el agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="ac52b-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="ac52b-119">**Tipocliente**</span><span class="sxs-lookup"><span data-stu-id="ac52b-119">**ClientType**</span></span> <br/> |<span data-ttu-id="ac52b-120">int</span><span class="sxs-lookup"><span data-stu-id="ac52b-120">int</span></span>  <br/> |<span data-ttu-id="ac52b-121">Tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="ac52b-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="ac52b-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="ac52b-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="ac52b-123">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ac52b-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="ac52b-124">Categoría a la que pertenece el cliente.</span><span class="sxs-lookup"><span data-stu-id="ac52b-124">Category that the client belongs to.</span></span> <span data-ttu-id="ac52b-125">Por ejemplo, la Conferencing_Attendant_ de cliente 1.0 pertenece a la CAA de ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="ac52b-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

