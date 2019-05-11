---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: la tabla tblConfig contiene algunos configuración de servidor de Chat persistente no admitida, en una fila.
ms.openlocfilehash: 79cd7e2303210bb07f35fa2c6b7ecc5c86b7e8cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930025"
---
# <a name="tblconfig"></a><span data-ttu-id="3a525-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="3a525-103">tblConfig</span></span>
 
<span data-ttu-id="3a525-104">la tabla tblConfig contiene algunos configuración de servidor de Chat persistente no admitida, en una fila.</span><span class="sxs-lookup"><span data-stu-id="3a525-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="3a525-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="3a525-105">**Columns**</span></span>

|<span data-ttu-id="3a525-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3a525-106">**Column**</span></span>|<span data-ttu-id="3a525-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3a525-107">**Type**</span></span>|<span data-ttu-id="3a525-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3a525-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3a525-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="3a525-109">configLabel</span></span>  <br/> |<span data-ttu-id="3a525-110">nvarchar (255), no es nulo</span><span class="sxs-lookup"><span data-stu-id="3a525-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="3a525-111">Contiene "grupo".</span><span class="sxs-lookup"><span data-stu-id="3a525-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="3a525-112">configContent</span><span class="sxs-lookup"><span data-stu-id="3a525-112">configContent</span></span>  <br/> |<span data-ttu-id="3a525-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="3a525-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="3a525-114">Contenido de configuración.</span><span class="sxs-lookup"><span data-stu-id="3a525-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="3a525-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="3a525-115">configPoolID</span></span>  <br/> |<span data-ttu-id="3a525-116">GUID, no es nulo</span><span class="sxs-lookup"><span data-stu-id="3a525-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="3a525-117">Identificador único de la instancia de base de datos.</span><span class="sxs-lookup"><span data-stu-id="3a525-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="3a525-118">**Clave**</span><span class="sxs-lookup"><span data-stu-id="3a525-118">**Key**</span></span>

|<span data-ttu-id="3a525-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3a525-119">**Column**</span></span>|<span data-ttu-id="3a525-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3a525-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3a525-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="3a525-121">configLabel</span></span>  <br/> |<span data-ttu-id="3a525-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="3a525-122">Primary key.</span></span>  <br/> |
   

