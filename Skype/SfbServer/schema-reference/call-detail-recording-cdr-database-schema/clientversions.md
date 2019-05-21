---
title: Tabla ClientVersions en Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La tabla ClientVersions es una tabla de soporte que almacena una lista de los distintos tipos de clientes y versiones que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.
ms.openlocfilehash: b42bc79fb04ca4ce2ef88fb7c280db7bc281e23b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296514"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b9b0d-104">Tabla ClientVersions en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="b9b0d-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b9b0d-105">La tabla ClientVersions es una tabla de soporte que almacena una lista de los distintos tipos de clientes y versiones que participaron en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="b9b0d-106">Cada registro de la tabla representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="b9b0d-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b9b0d-107">**Column**</span></span>|<span data-ttu-id="b9b0d-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="b9b0d-108">**Data Type**</span></span>|<span data-ttu-id="b9b0d-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="b9b0d-109">**Key/Index**</span></span>|<span data-ttu-id="b9b0d-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="b9b0d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b9b0d-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="b9b0d-111">**VersionId**</span></span> <br/> |<span data-ttu-id="b9b0d-112">**int**</span><span class="sxs-lookup"><span data-stu-id="b9b0d-112">**int**</span></span> <br/> |<span data-ttu-id="b9b0d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b9b0d-113">Primary</span></span>  <br/> |<span data-ttu-id="b9b0d-114">Número único que identifica este tipo de cliente y versión.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="b9b0d-115">**Versión**</span><span class="sxs-lookup"><span data-stu-id="b9b0d-115">**Version**</span></span> <br/> |<span data-ttu-id="b9b0d-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="b9b0d-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="b9b0d-117">Nombre de la versión.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="b9b0d-118">**Tipocliente**</span><span class="sxs-lookup"><span data-stu-id="b9b0d-118">**ClientType**</span></span> <br/> |<span data-ttu-id="b9b0d-119">int</span><span class="sxs-lookup"><span data-stu-id="b9b0d-119">int</span></span>  <br/> ||<span data-ttu-id="b9b0d-120">Especifica el tipo de cliente usado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="b9b0d-121">Para obtener más información, consulte la [tabla UserAgentDef](useragentdef.md) .</span><span class="sxs-lookup"><span data-stu-id="b9b0d-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="b9b0d-122">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

