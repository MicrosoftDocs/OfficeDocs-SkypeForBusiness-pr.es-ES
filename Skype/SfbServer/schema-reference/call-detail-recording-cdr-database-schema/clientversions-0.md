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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: La vista ClientVersions almacena información sobre los diversos tipos y versiones de los clientes que participaron en sesiones registradas en la base de datos. Cada registro de la vista representa una versión de cliente. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815418"
---
# <a name="clientversions-view"></a><span data-ttu-id="04ead-105">Vista ClientVersions</span><span class="sxs-lookup"><span data-stu-id="04ead-105">ClientVersions view</span></span>
 
<span data-ttu-id="04ead-106">La vista ClientVersions almacena información sobre los diversos tipos y versiones de los clientes que participaron en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="04ead-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="04ead-107">Cada registro de la vista representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="04ead-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="04ead-108">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="04ead-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="04ead-109">Es posible que haya varios registros para determinadas columnas.</span><span class="sxs-lookup"><span data-stu-id="04ead-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="04ead-110">**Columna**</span><span class="sxs-lookup"><span data-stu-id="04ead-110">**Column**</span></span>|<span data-ttu-id="04ead-111">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="04ead-111">**Data Type**</span></span>|<span data-ttu-id="04ead-112">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="04ead-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="04ead-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="04ead-113">**VersionId**</span></span> <br/> |<span data-ttu-id="04ead-114">int</span><span class="sxs-lookup"><span data-stu-id="04ead-114">int</span></span>  <br/> |<span data-ttu-id="04ead-115">Número único que identifica este tipo de cliente y versión.</span><span class="sxs-lookup"><span data-stu-id="04ead-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="04ead-116">**Versión**</span><span class="sxs-lookup"><span data-stu-id="04ead-116">**Version**</span></span> <br/> |<span data-ttu-id="04ead-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="04ead-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="04ead-118">Representa el agente de usuario.</span><span class="sxs-lookup"><span data-stu-id="04ead-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="04ead-119">**Tipocliente**</span><span class="sxs-lookup"><span data-stu-id="04ead-119">**ClientType**</span></span> <br/> |<span data-ttu-id="04ead-120">int</span><span class="sxs-lookup"><span data-stu-id="04ead-120">int</span></span>  <br/> |<span data-ttu-id="04ead-121">Tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="04ead-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="04ead-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="04ead-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="04ead-123">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="04ead-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="04ead-124">Categoría a la que pertenece el cliente.</span><span class="sxs-lookup"><span data-stu-id="04ead-124">Category that the client belongs to.</span></span> <span data-ttu-id="04ead-125">Por ejemplo, el cliente Conferencing_Attendant_1.0 pertenece a la CAA de ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="04ead-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

