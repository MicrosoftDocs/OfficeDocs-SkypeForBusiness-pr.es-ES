---
title: Tabla ClientVersions en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: La tabla ClientVersions es una tabla de soporte que almacena una lista de los distintos tipos de cliente y versiones que han participado en las sesiones que se registran en la base de datos. Cada registro de la tabla representa una versión de cliente.
ms.openlocfilehash: 488c7f4211eacb6fc496d6198258c119641ebd14
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0d724-104">Tabla ClientVersions en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0d724-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0d724-105">La tabla ClientVersions es una tabla de soporte que almacena una lista de los distintos tipos de cliente y versiones que han participado en las sesiones que se registran en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0d724-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="0d724-106">Cada registro de la tabla representa una versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="0d724-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="0d724-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="0d724-107">**Column**</span></span>|<span data-ttu-id="0d724-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0d724-108">**Data Type**</span></span>|<span data-ttu-id="0d724-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="0d724-109">**Key/Index**</span></span>|<span data-ttu-id="0d724-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="0d724-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0d724-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="0d724-111">**VersionId**</span></span> <br/> |<span data-ttu-id="0d724-112">**int**</span><span class="sxs-lookup"><span data-stu-id="0d724-112">**int**</span></span> <br/> |<span data-ttu-id="0d724-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0d724-113">Primary</span></span>  <br/> |<span data-ttu-id="0d724-114">Número único que identifica este tipo de cliente y versión.</span><span class="sxs-lookup"><span data-stu-id="0d724-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="0d724-115">**Versión**</span><span class="sxs-lookup"><span data-stu-id="0d724-115">**Version**</span></span> <br/> |<span data-ttu-id="0d724-116">**nvarchar (256)**</span><span class="sxs-lookup"><span data-stu-id="0d724-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="0d724-117">Nombre de la versión.</span><span class="sxs-lookup"><span data-stu-id="0d724-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="0d724-118">**TipoCliente**</span><span class="sxs-lookup"><span data-stu-id="0d724-118">**ClientType**</span></span> <br/> |<span data-ttu-id="0d724-119">int</span><span class="sxs-lookup"><span data-stu-id="0d724-119">int</span></span>  <br/> ||<span data-ttu-id="0d724-120">Especifica el tipo de cliente utilizado en la sesión.</span><span class="sxs-lookup"><span data-stu-id="0d724-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="0d724-121">Consulte la [tabla de UserAgentDef](useragentdef.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0d724-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="0d724-122">Este campo se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d724-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

