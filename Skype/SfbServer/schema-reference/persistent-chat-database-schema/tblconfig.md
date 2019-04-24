---
title: tblConfig
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: la tabla tblConfig contiene algunos configuración de servidor de Chat persistente no admitida, en una fila.
ms.openlocfilehash: 9d28c0506b905975e2a72eeb83605fe4e32e7cfd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213070"
---
# <a name="tblconfig"></a><span data-ttu-id="95248-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="95248-103">tblConfig</span></span>
 
<span data-ttu-id="95248-104">la tabla tblConfig contiene algunos configuración de servidor de Chat persistente no admitida, en una fila.</span><span class="sxs-lookup"><span data-stu-id="95248-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="95248-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="95248-105">**Columns**</span></span>

|<span data-ttu-id="95248-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="95248-106">**Column**</span></span>|<span data-ttu-id="95248-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="95248-107">**Type**</span></span>|<span data-ttu-id="95248-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="95248-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="95248-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="95248-109">configLabel</span></span>  <br/> |<span data-ttu-id="95248-110">nvarchar (255), no es nulo</span><span class="sxs-lookup"><span data-stu-id="95248-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="95248-111">Contiene "grupo".</span><span class="sxs-lookup"><span data-stu-id="95248-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="95248-112">configContent</span><span class="sxs-lookup"><span data-stu-id="95248-112">configContent</span></span>  <br/> |<span data-ttu-id="95248-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="95248-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="95248-114">Contenido de configuración.</span><span class="sxs-lookup"><span data-stu-id="95248-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="95248-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="95248-115">configPoolID</span></span>  <br/> |<span data-ttu-id="95248-116">GUID, no es nulo</span><span class="sxs-lookup"><span data-stu-id="95248-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="95248-117">Identificador único de la instancia de base de datos.</span><span class="sxs-lookup"><span data-stu-id="95248-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="95248-118">**Clave**</span><span class="sxs-lookup"><span data-stu-id="95248-118">**Key**</span></span>

|<span data-ttu-id="95248-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="95248-119">**Column**</span></span>|<span data-ttu-id="95248-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="95248-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="95248-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="95248-121">configLabel</span></span>  <br/> |<span data-ttu-id="95248-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="95248-122">Primary key.</span></span>  <br/> |
   

