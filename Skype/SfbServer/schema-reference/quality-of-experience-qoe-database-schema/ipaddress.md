---
title: Tabla IPAddress
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La tabla IPAddress asigna direcciones IP a los identificadores de dirección IP únicos que se usan en otras partes de la base de datos de calidad de la experiencia. Esta tabla se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 31334c553641088a5b77d0bb24517791e5f84ebe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802780"
---
# <a name="ipaddress-table"></a><span data-ttu-id="7510e-104">Tabla IPAddress</span><span class="sxs-lookup"><span data-stu-id="7510e-104">IPAddress table</span></span>
 
<span data-ttu-id="7510e-105">La tabla IPAddress asigna direcciones IP a los identificadores de dirección IP únicos que se usan en otras partes de la base de datos de calidad de la experiencia.</span><span class="sxs-lookup"><span data-stu-id="7510e-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="7510e-106">Esta tabla se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7510e-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="7510e-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7510e-107">**Column**</span></span>|<span data-ttu-id="7510e-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="7510e-108">**Data Type**</span></span>|<span data-ttu-id="7510e-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="7510e-109">**Key/Index**</span></span>|<span data-ttu-id="7510e-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="7510e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7510e-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="7510e-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="7510e-112">entero</span><span class="sxs-lookup"><span data-stu-id="7510e-112">int</span></span>  <br/> |<span data-ttu-id="7510e-113">Principal</span><span class="sxs-lookup"><span data-stu-id="7510e-113">Primary</span></span>  <br/> |<span data-ttu-id="7510e-114">Identificador único de la dirección IP especificada.</span><span class="sxs-lookup"><span data-stu-id="7510e-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="7510e-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="7510e-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="7510e-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="7510e-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="7510e-117">Única</span><span class="sxs-lookup"><span data-stu-id="7510e-117">Unique</span></span>  <br/> |<span data-ttu-id="7510e-p103">Dirección IP única (por ejemplo, 189.168.1.1) que se asigna a IpAddressKey. Puede ser una dirección IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="7510e-p103">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey. This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

