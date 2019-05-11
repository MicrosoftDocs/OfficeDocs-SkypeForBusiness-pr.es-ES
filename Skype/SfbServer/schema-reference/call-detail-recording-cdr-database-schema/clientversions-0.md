---
title: Vista ClientVersions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vista ClientVersions almacena información acerca de los diversos tipos de cliente y las versiones que han participado en sesiones registradas en la base de datos. Cada registro en la vista representa una versión de cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: cc4024a7e2644a177eb6962c8fdc7078fd6b397d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901525"
---
# <a name="clientversions-view"></a><span data-ttu-id="c9640-105">Vista ClientVersions</span><span class="sxs-lookup"><span data-stu-id="c9640-105">ClientVersions view</span></span>
 
<span data-ttu-id="c9640-106">La vista ClientVersions almacena información acerca de los diversos tipos de cliente y las versiones que han participado en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c9640-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="c9640-107">Cada registro en la vista representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="c9640-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="c9640-108">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9640-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9640-109">Pueden haber varios registros para determinadas columnas.</span><span class="sxs-lookup"><span data-stu-id="c9640-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="c9640-110">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c9640-110">**Column**</span></span>|<span data-ttu-id="c9640-111">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="c9640-111">**Data Type**</span></span>|<span data-ttu-id="c9640-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="c9640-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9640-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="c9640-113">**VersionId**</span></span> <br/> |<span data-ttu-id="c9640-114">int</span><span class="sxs-lookup"><span data-stu-id="c9640-114">int</span></span>  <br/> |<span data-ttu-id="c9640-115">Número único que identifica este tipo de cliente y versión.</span><span class="sxs-lookup"><span data-stu-id="c9640-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="c9640-116">**Versión**</span><span class="sxs-lookup"><span data-stu-id="c9640-116">**Version**</span></span> <br/> |<span data-ttu-id="c9640-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c9640-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c9640-118">Representa al agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="c9640-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="c9640-119">**TipoCliente**</span><span class="sxs-lookup"><span data-stu-id="c9640-119">**ClientType**</span></span> <br/> |<span data-ttu-id="c9640-120">int</span><span class="sxs-lookup"><span data-stu-id="c9640-120">int</span></span>  <br/> |<span data-ttu-id="c9640-121">Tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="c9640-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="c9640-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="c9640-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="c9640-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="c9640-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="c9640-124">Categoría a la que pertenece el cliente.</span><span class="sxs-lookup"><span data-stu-id="c9640-124">Category that the client belongs to.</span></span> <span data-ttu-id="c9640-125">Por ejemplo, el cliente Conferencing_Attendant_1.0 pertenece a la CAA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="c9640-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

