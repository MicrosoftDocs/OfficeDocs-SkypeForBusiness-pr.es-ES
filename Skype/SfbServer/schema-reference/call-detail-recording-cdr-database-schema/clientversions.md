---
title: Tabla ClientVersions en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La tabla ClientVersions es una tabla de apoyo que almacena una lista de los distintos tipos de cliente y las versiones que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.
ms.openlocfilehash: df80e907359297c9cdb518562fdeea54d31a2a47
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213385"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5316c-104">Tabla ClientVersions en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5316c-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5316c-105">La tabla ClientVersions es una tabla de apoyo que almacena una lista de los distintos tipos de cliente y las versiones que han participado en sesiones registradas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5316c-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="5316c-106">Cada registro de la tabla representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="5316c-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="5316c-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5316c-107">**Column**</span></span>|<span data-ttu-id="5316c-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="5316c-108">**Data Type**</span></span>|<span data-ttu-id="5316c-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="5316c-109">**Key/Index**</span></span>|<span data-ttu-id="5316c-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="5316c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5316c-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="5316c-111">**VersionId**</span></span> <br/> |<span data-ttu-id="5316c-112">**int**</span><span class="sxs-lookup"><span data-stu-id="5316c-112">**int**</span></span> <br/> |<span data-ttu-id="5316c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="5316c-113">Primary</span></span>  <br/> |<span data-ttu-id="5316c-114">Número único que identifica este tipo de cliente y versión.</span><span class="sxs-lookup"><span data-stu-id="5316c-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="5316c-115">**Versión**</span><span class="sxs-lookup"><span data-stu-id="5316c-115">**Version**</span></span> <br/> |<span data-ttu-id="5316c-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="5316c-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="5316c-117">Nombre de la versión.</span><span class="sxs-lookup"><span data-stu-id="5316c-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="5316c-118">**TipoCliente**</span><span class="sxs-lookup"><span data-stu-id="5316c-118">**ClientType**</span></span> <br/> |<span data-ttu-id="5316c-119">int</span><span class="sxs-lookup"><span data-stu-id="5316c-119">int</span></span>  <br/> ||<span data-ttu-id="5316c-120">Especifica el tipo de cliente utilizado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="5316c-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="5316c-121">Consulte la [tabla UserAgentDef](useragentdef.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5316c-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="5316c-122">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5316c-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

