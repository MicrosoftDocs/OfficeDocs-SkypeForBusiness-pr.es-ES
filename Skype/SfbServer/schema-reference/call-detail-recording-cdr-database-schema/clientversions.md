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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La tabla ClientVersions es una tabla de soporte que almacena una lista de los distintos tipos de clientes y versiones que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815408"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="99485-104">Tabla ClientVersions en Skype empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="99485-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="99485-105">La tabla ClientVersions es una tabla de soporte que almacena una lista de los distintos tipos de clientes y versiones que participaron en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="99485-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="99485-106">Cada registro de la tabla representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="99485-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="99485-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="99485-107">**Column**</span></span>|<span data-ttu-id="99485-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="99485-108">**Data Type**</span></span>|<span data-ttu-id="99485-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="99485-109">**Key/Index**</span></span>|<span data-ttu-id="99485-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="99485-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="99485-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="99485-111">**VersionId**</span></span> <br/> |<span data-ttu-id="99485-112">**int**</span><span class="sxs-lookup"><span data-stu-id="99485-112">**int**</span></span> <br/> |<span data-ttu-id="99485-113">Primary</span><span class="sxs-lookup"><span data-stu-id="99485-113">Primary</span></span>  <br/> |<span data-ttu-id="99485-114">Número único que identifica este tipo de cliente y versión.</span><span class="sxs-lookup"><span data-stu-id="99485-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="99485-115">**Versión**</span><span class="sxs-lookup"><span data-stu-id="99485-115">**Version**</span></span> <br/> |<span data-ttu-id="99485-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="99485-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="99485-117">Nombre de la versión.</span><span class="sxs-lookup"><span data-stu-id="99485-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="99485-118">**Tipocliente**</span><span class="sxs-lookup"><span data-stu-id="99485-118">**ClientType**</span></span> <br/> |<span data-ttu-id="99485-119">int</span><span class="sxs-lookup"><span data-stu-id="99485-119">int</span></span>  <br/> ||<span data-ttu-id="99485-120">Especifica el tipo de cliente usado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="99485-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="99485-121">Para obtener más información, consulte la [tabla UserAgentDef](useragentdef.md) .</span><span class="sxs-lookup"><span data-stu-id="99485-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="99485-122">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="99485-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

