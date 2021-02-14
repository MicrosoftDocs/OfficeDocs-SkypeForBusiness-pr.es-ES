---
title: Tabla ClientVersions en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La tabla ClientVersions es una tabla de apoyo que almacena una lista de los distintos versiones y tipos de clientes que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.
ms.openlocfilehash: 9f72a640fa294a51e483f496cad9913177dfcd2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813320"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3bc83-104">Tabla ClientVersions en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="3bc83-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3bc83-p102">La tabla ClientVersions es una tabla de apoyo que almacena una lista de los distintos versiones y tipos de clientes que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="3bc83-p102">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="3bc83-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3bc83-107">**Column**</span></span>|<span data-ttu-id="3bc83-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="3bc83-108">**Data Type**</span></span>|<span data-ttu-id="3bc83-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="3bc83-109">**Key/Index**</span></span>|<span data-ttu-id="3bc83-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="3bc83-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3bc83-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="3bc83-111">**VersionId**</span></span> <br/> |<span data-ttu-id="3bc83-112">**int**</span><span class="sxs-lookup"><span data-stu-id="3bc83-112">**int**</span></span> <br/> |<span data-ttu-id="3bc83-113">Principal</span><span class="sxs-lookup"><span data-stu-id="3bc83-113">Primary</span></span>  <br/> |<span data-ttu-id="3bc83-114">Número único que identifica esta versión y este tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="3bc83-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="3bc83-115">**Versión**</span><span class="sxs-lookup"><span data-stu-id="3bc83-115">**Version**</span></span> <br/> |<span data-ttu-id="3bc83-116">**nvarchar(256)**</span><span class="sxs-lookup"><span data-stu-id="3bc83-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="3bc83-117">Nombre de la versión.</span><span class="sxs-lookup"><span data-stu-id="3bc83-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="3bc83-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="3bc83-118">**ClientType**</span></span> <br/> |<span data-ttu-id="3bc83-119">entero</span><span class="sxs-lookup"><span data-stu-id="3bc83-119">int</span></span>  <br/> ||<span data-ttu-id="3bc83-120">Especifica el tipo de cliente usado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="3bc83-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="3bc83-121">Vea la [tabla UserAgentDef](useragentdef.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3bc83-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="3bc83-122">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3bc83-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

