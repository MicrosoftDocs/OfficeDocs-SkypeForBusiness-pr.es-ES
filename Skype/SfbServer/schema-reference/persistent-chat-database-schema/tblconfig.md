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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898940"
---
# <a name="tblconfig"></a><span data-ttu-id="23cab-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="23cab-103">tblConfig</span></span>
 
<span data-ttu-id="23cab-104">la tabla tblConfig contiene algunos configuración de servidor de Chat persistente no admitida, en una fila.</span><span class="sxs-lookup"><span data-stu-id="23cab-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="23cab-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="23cab-105">**Columns**</span></span>

|<span data-ttu-id="23cab-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="23cab-106">**Column**</span></span>|<span data-ttu-id="23cab-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="23cab-107">**Type**</span></span>|<span data-ttu-id="23cab-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="23cab-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="23cab-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="23cab-109">configLabel</span></span>  <br/> |<span data-ttu-id="23cab-110">nvarchar (255), no es nulo</span><span class="sxs-lookup"><span data-stu-id="23cab-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="23cab-111">Contiene "grupo".</span><span class="sxs-lookup"><span data-stu-id="23cab-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="23cab-112">configContent</span><span class="sxs-lookup"><span data-stu-id="23cab-112">configContent</span></span>  <br/> |<span data-ttu-id="23cab-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="23cab-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="23cab-114">Contenido de configuración.</span><span class="sxs-lookup"><span data-stu-id="23cab-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="23cab-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="23cab-115">configPoolID</span></span>  <br/> |<span data-ttu-id="23cab-116">GUID, no es nulo</span><span class="sxs-lookup"><span data-stu-id="23cab-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="23cab-117">Identificador único de la instancia de base de datos.</span><span class="sxs-lookup"><span data-stu-id="23cab-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="23cab-118">**Clave**</span><span class="sxs-lookup"><span data-stu-id="23cab-118">**Key**</span></span>

|<span data-ttu-id="23cab-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="23cab-119">**Column**</span></span>|<span data-ttu-id="23cab-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="23cab-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="23cab-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="23cab-121">configLabel</span></span>  <br/> |<span data-ttu-id="23cab-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="23cab-122">Primary key.</span></span>  <br/> |
   

