---
title: Tabla de dirección IP
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La tabla dirección IP asigna direcciones IP a los identificadores únicos de dirección IP utilizados en la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 6372d46b69046f944ba33d4deff6d29e923a94cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="ipaddress-table"></a><span data-ttu-id="5a286-104">Tabla de dirección IP</span><span class="sxs-lookup"><span data-stu-id="5a286-104">IPAddress table</span></span>
 
<span data-ttu-id="5a286-105">La tabla dirección IP asigna direcciones IP a los identificadores únicos de dirección IP utilizados en la base de datos de calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="5a286-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="5a286-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5a286-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5a286-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5a286-107">**Column**</span></span>|<span data-ttu-id="5a286-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="5a286-108">**Data Type**</span></span>|<span data-ttu-id="5a286-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="5a286-109">**Key/Index**</span></span>|<span data-ttu-id="5a286-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="5a286-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5a286-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="5a286-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="5a286-112">int</span><span class="sxs-lookup"><span data-stu-id="5a286-112">int</span></span>  <br/> |<span data-ttu-id="5a286-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5a286-113">Primary</span></span>  <br/> |<span data-ttu-id="5a286-114">Identificador único de la dirección IP especificada.</span><span class="sxs-lookup"><span data-stu-id="5a286-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="5a286-115">**Dirección IP**</span><span class="sxs-lookup"><span data-stu-id="5a286-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="5a286-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="5a286-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="5a286-117">Único</span><span class="sxs-lookup"><span data-stu-id="5a286-117">Unique</span></span>  <br/> |<span data-ttu-id="5a286-118">Dirección IP única (por ejemplo, 189.168.1.1) que se asigna a la IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="5a286-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="5a286-119">Esto puede ser tanto una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="5a286-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

