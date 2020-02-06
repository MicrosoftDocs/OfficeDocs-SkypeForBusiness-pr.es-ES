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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene la configuración no admitida de un servidor de chat persistente, en una fila.
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814628"
---
# <a name="tblconfig"></a><span data-ttu-id="b24ec-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="b24ec-103">tblConfig</span></span>
 
<span data-ttu-id="b24ec-104">tblConfig contiene la configuración no admitida de un servidor de chat persistente, en una fila.</span><span class="sxs-lookup"><span data-stu-id="b24ec-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="b24ec-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="b24ec-105">**Columns**</span></span>

|<span data-ttu-id="b24ec-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b24ec-106">**Column**</span></span>|<span data-ttu-id="b24ec-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b24ec-107">**Type**</span></span>|<span data-ttu-id="b24ec-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b24ec-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b24ec-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="b24ec-109">configLabel</span></span>  <br/> |<span data-ttu-id="b24ec-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="b24ec-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="b24ec-111">Contiene "pool".</span><span class="sxs-lookup"><span data-stu-id="b24ec-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="b24ec-112">configContent</span><span class="sxs-lookup"><span data-stu-id="b24ec-112">configContent</span></span>  <br/> |<span data-ttu-id="b24ec-113">nvarchar (Max)</span><span class="sxs-lookup"><span data-stu-id="b24ec-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="b24ec-114">Contenido de configuración.</span><span class="sxs-lookup"><span data-stu-id="b24ec-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="b24ec-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="b24ec-115">configPoolID</span></span>  <br/> |<span data-ttu-id="b24ec-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="b24ec-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="b24ec-117">IDENTIFICADOR único de la instancia de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b24ec-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="b24ec-118">**Clave**</span><span class="sxs-lookup"><span data-stu-id="b24ec-118">**Key**</span></span>

|<span data-ttu-id="b24ec-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b24ec-119">**Column**</span></span>|<span data-ttu-id="b24ec-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b24ec-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b24ec-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="b24ec-121">configLabel</span></span>  <br/> |<span data-ttu-id="b24ec-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="b24ec-122">Primary key.</span></span>  <br/> |
   

