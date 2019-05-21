---
title: Tabla dirección IP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La tabla direcciónIP asigna direcciones IP a los identificadores de dirección IP únicos que se usan en otras partes de la base de datos de la calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 74d74636b7183d1369db85c363997460a434d8f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294925"
---
# <a name="ipaddress-table"></a><span data-ttu-id="9071f-104">Tabla dirección IP</span><span class="sxs-lookup"><span data-stu-id="9071f-104">IPAddress table</span></span>
 
<span data-ttu-id="9071f-105">La tabla direcciónIP asigna direcciones IP a los identificadores de dirección IP únicos que se usan en otras partes de la base de datos de la calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="9071f-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="9071f-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9071f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="9071f-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9071f-107">**Column**</span></span>|<span data-ttu-id="9071f-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9071f-108">**Data Type**</span></span>|<span data-ttu-id="9071f-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="9071f-109">**Key/Index**</span></span>|<span data-ttu-id="9071f-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="9071f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9071f-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="9071f-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="9071f-112">int</span><span class="sxs-lookup"><span data-stu-id="9071f-112">int</span></span>  <br/> |<span data-ttu-id="9071f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9071f-113">Primary</span></span>  <br/> |<span data-ttu-id="9071f-114">Identificador único de la dirección IP especificada.</span><span class="sxs-lookup"><span data-stu-id="9071f-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="9071f-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="9071f-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="9071f-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="9071f-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="9071f-117">Solo</span><span class="sxs-lookup"><span data-stu-id="9071f-117">Unique</span></span>  <br/> |<span data-ttu-id="9071f-118">Dirección IP única (por ejemplo, 189.168.1.1) que se asigna a la IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="9071f-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="9071f-119">Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="9071f-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

