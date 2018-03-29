---
title: tblConfig
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene una configuración no compatible persistente Chat Server, en una fila.
ms.openlocfilehash: 099060f0957ae21c14b285eac1b753ad0b8c1719
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblconfig"></a><span data-ttu-id="5394f-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="5394f-103">tblConfig</span></span>
 
<span data-ttu-id="5394f-104">tblConfig contiene una configuración no compatible persistente Chat Server, en una fila.</span><span class="sxs-lookup"><span data-stu-id="5394f-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="5394f-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="5394f-105">**Columns**</span></span>

|<span data-ttu-id="5394f-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5394f-106">**Column**</span></span>|<span data-ttu-id="5394f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5394f-107">**Type**</span></span>|<span data-ttu-id="5394f-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5394f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5394f-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="5394f-109">configLabel</span></span>  <br/> |<span data-ttu-id="5394f-110">nvarchar (255), no nulo</span><span class="sxs-lookup"><span data-stu-id="5394f-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="5394f-111">Contiene "grupo".</span><span class="sxs-lookup"><span data-stu-id="5394f-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="5394f-112">configContent</span><span class="sxs-lookup"><span data-stu-id="5394f-112">configContent</span></span>  <br/> |<span data-ttu-id="5394f-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="5394f-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="5394f-114">Contenido de configuración.</span><span class="sxs-lookup"><span data-stu-id="5394f-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="5394f-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="5394f-115">configPoolID</span></span>  <br/> |<span data-ttu-id="5394f-116">GUID, no nulo</span><span class="sxs-lookup"><span data-stu-id="5394f-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="5394f-117">Identificador exclusivo de la instancia de base de datos.</span><span class="sxs-lookup"><span data-stu-id="5394f-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="5394f-118">**Clave**</span><span class="sxs-lookup"><span data-stu-id="5394f-118">**Key**</span></span>

|<span data-ttu-id="5394f-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="5394f-119">**Column**</span></span>|<span data-ttu-id="5394f-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5394f-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5394f-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="5394f-121">configLabel</span></span>  <br/> |<span data-ttu-id="5394f-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="5394f-122">Primary key.</span></span>  <br/> |
   

