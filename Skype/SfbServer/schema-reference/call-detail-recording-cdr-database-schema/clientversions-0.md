---
title: Vista ClientVersions
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vista ClientVersions almacena información acerca de los diversos tipos de cliente y las versiones que han participado en sesiones registradas en la base de datos. Cada registro en la vista representa una versión de cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: abf1436a2c3309e95bec8371b586c017e11b816d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213399"
---
# <a name="clientversions-view"></a><span data-ttu-id="e3e1b-105">Vista ClientVersions</span><span class="sxs-lookup"><span data-stu-id="e3e1b-105">ClientVersions view</span></span>
 
<span data-ttu-id="e3e1b-106">La vista ClientVersions almacena información acerca de los diversos tipos de cliente y las versiones que han participado en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e3e1b-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="e3e1b-107">Cada registro en la vista representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="e3e1b-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="e3e1b-108">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3e1b-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e3e1b-109">Pueden haber varios registros para determinadas columnas.</span><span class="sxs-lookup"><span data-stu-id="e3e1b-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="e3e1b-110">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e3e1b-110">**Column**</span></span>|<span data-ttu-id="e3e1b-111">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e3e1b-111">**Data Type**</span></span>|<span data-ttu-id="e3e1b-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="e3e1b-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3e1b-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="e3e1b-113">**VersionId**</span></span> <br/> |<span data-ttu-id="e3e1b-114">int</span><span class="sxs-lookup"><span data-stu-id="e3e1b-114">int</span></span>  <br/> |<span data-ttu-id="e3e1b-115">Número único que identifica este tipo de cliente y versión.</span><span class="sxs-lookup"><span data-stu-id="e3e1b-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="e3e1b-116">**Versión**</span><span class="sxs-lookup"><span data-stu-id="e3e1b-116">**Version**</span></span> <br/> |<span data-ttu-id="e3e1b-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e3e1b-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e3e1b-118">Representa al agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="e3e1b-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="e3e1b-119">**TipoCliente**</span><span class="sxs-lookup"><span data-stu-id="e3e1b-119">**ClientType**</span></span> <br/> |<span data-ttu-id="e3e1b-120">int</span><span class="sxs-lookup"><span data-stu-id="e3e1b-120">int</span></span>  <br/> |<span data-ttu-id="e3e1b-121">Tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="e3e1b-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="e3e1b-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="e3e1b-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="e3e1b-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="e3e1b-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="e3e1b-124">Categoría a la que pertenece el cliente.</span><span class="sxs-lookup"><span data-stu-id="e3e1b-124">Category that the client belongs to.</span></span> <span data-ttu-id="e3e1b-125">Por ejemplo, el cliente Conferencing_Attendant_1.0 pertenece a la CAA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="e3e1b-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

