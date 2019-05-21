---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene la configuración no admitida de un servidor de chat persistente, en una fila.
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295457"
---
# <a name="tblconfig"></a><span data-ttu-id="b35a7-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="b35a7-103">tblConfig</span></span>
 
<span data-ttu-id="b35a7-104">tblConfig contiene la configuración no admitida de un servidor de chat persistente, en una fila.</span><span class="sxs-lookup"><span data-stu-id="b35a7-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="b35a7-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="b35a7-105">**Columns**</span></span>

|<span data-ttu-id="b35a7-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b35a7-106">**Column**</span></span>|<span data-ttu-id="b35a7-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b35a7-107">**Type**</span></span>|<span data-ttu-id="b35a7-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b35a7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b35a7-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="b35a7-109">configLabel</span></span>  <br/> |<span data-ttu-id="b35a7-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="b35a7-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="b35a7-111">Contiene "pool".</span><span class="sxs-lookup"><span data-stu-id="b35a7-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="b35a7-112">configContent</span><span class="sxs-lookup"><span data-stu-id="b35a7-112">configContent</span></span>  <br/> |<span data-ttu-id="b35a7-113">nvarchar (Max)</span><span class="sxs-lookup"><span data-stu-id="b35a7-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="b35a7-114">Contenido de configuración.</span><span class="sxs-lookup"><span data-stu-id="b35a7-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="b35a7-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="b35a7-115">configPoolID</span></span>  <br/> |<span data-ttu-id="b35a7-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="b35a7-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="b35a7-117">IDENTIFICADOR único de la instancia de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b35a7-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="b35a7-118">**Clave**</span><span class="sxs-lookup"><span data-stu-id="b35a7-118">**Key**</span></span>

|<span data-ttu-id="b35a7-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b35a7-119">**Column**</span></span>|<span data-ttu-id="b35a7-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b35a7-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b35a7-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="b35a7-121">configLabel</span></span>  <br/> |<span data-ttu-id="b35a7-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="b35a7-122">Primary key.</span></span>  <br/> |
   

