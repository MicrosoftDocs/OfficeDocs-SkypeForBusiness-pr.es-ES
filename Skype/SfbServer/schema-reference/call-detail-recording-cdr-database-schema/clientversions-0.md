---
title: Vista de ClientVersions
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vista ClientVersions almacena información acerca de los diversos tipos de cliente y versiones que han participado en las sesiones que se registran en la base de datos. Cada registro de la vista representa una versión de cliente. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 0906e35d0912684c9aeb169017b5df0a53202c50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-view"></a><span data-ttu-id="0391d-105">Vista de ClientVersions</span><span class="sxs-lookup"><span data-stu-id="0391d-105">ClientVersions view</span></span>
 
<span data-ttu-id="0391d-106">La vista ClientVersions almacena información acerca de los diversos tipos de cliente y versiones que han participado en las sesiones que se registran en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0391d-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="0391d-107">Cada registro de la vista representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="0391d-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="0391d-108">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0391d-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0391d-109">Pueden haber varios registros para ciertas columnas.</span><span class="sxs-lookup"><span data-stu-id="0391d-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="0391d-110">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0391d-110">**Column**</span></span>|<span data-ttu-id="0391d-111">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0391d-111">**Data Type**</span></span>|<span data-ttu-id="0391d-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="0391d-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0391d-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="0391d-113">**VersionId**</span></span> <br/> |<span data-ttu-id="0391d-114">int</span><span class="sxs-lookup"><span data-stu-id="0391d-114">int</span></span>  <br/> |<span data-ttu-id="0391d-115">Número único que identifica este tipo de cliente y versión.</span><span class="sxs-lookup"><span data-stu-id="0391d-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="0391d-116">**Versión**</span><span class="sxs-lookup"><span data-stu-id="0391d-116">**Version**</span></span> <br/> |<span data-ttu-id="0391d-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0391d-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0391d-118">Representa al agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="0391d-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="0391d-119">**TipoCliente**</span><span class="sxs-lookup"><span data-stu-id="0391d-119">**ClientType**</span></span> <br/> |<span data-ttu-id="0391d-120">int</span><span class="sxs-lookup"><span data-stu-id="0391d-120">int</span></span>  <br/> |<span data-ttu-id="0391d-121">Tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="0391d-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="0391d-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="0391d-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="0391d-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="0391d-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="0391d-124">Categoría a la que pertenece el cliente.</span><span class="sxs-lookup"><span data-stu-id="0391d-124">Category that the client belongs to.</span></span> <span data-ttu-id="0391d-125">Por ejemplo, el cliente que pertenece el CAA ClientCategory Conferencing_Attendant_1.0.</span><span class="sxs-lookup"><span data-stu-id="0391d-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

