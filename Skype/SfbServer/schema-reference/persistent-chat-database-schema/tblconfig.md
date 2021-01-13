---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contiene algunas configuraciones no admitidas del servidor de chat persistente, en una fila.
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809740"
---
# <a name="tblconfig"></a><span data-ttu-id="ecce4-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="ecce4-103">tblConfig</span></span>
 
<span data-ttu-id="ecce4-104">tblConfig contiene algunas configuraciones no admitidas del servidor de chat persistente, en una fila.</span><span class="sxs-lookup"><span data-stu-id="ecce4-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="ecce4-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="ecce4-105">**Columns**</span></span>

|<span data-ttu-id="ecce4-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ecce4-106">**Column**</span></span>|<span data-ttu-id="ecce4-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ecce4-107">**Type**</span></span>|<span data-ttu-id="ecce4-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ecce4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ecce4-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="ecce4-109">configLabel</span></span>  <br/> |<span data-ttu-id="ecce4-110">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="ecce4-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="ecce4-111">Contiene "grupo".</span><span class="sxs-lookup"><span data-stu-id="ecce4-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="ecce4-112">configContent</span><span class="sxs-lookup"><span data-stu-id="ecce4-112">configContent</span></span>  <br/> |<span data-ttu-id="ecce4-113">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="ecce4-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="ecce4-114">Contenido de la configuración.</span><span class="sxs-lookup"><span data-stu-id="ecce4-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="ecce4-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="ecce4-115">configPoolID</span></span>  <br/> |<span data-ttu-id="ecce4-116">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="ecce4-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="ecce4-117">Identificador único de la instancia de base de datos.</span><span class="sxs-lookup"><span data-stu-id="ecce4-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="ecce4-118">**Clave**</span><span class="sxs-lookup"><span data-stu-id="ecce4-118">**Key**</span></span>

|<span data-ttu-id="ecce4-119">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ecce4-119">**Column**</span></span>|<span data-ttu-id="ecce4-120">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ecce4-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ecce4-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="ecce4-121">configLabel</span></span>  <br/> |<span data-ttu-id="ecce4-122">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="ecce4-122">Primary key.</span></span>  <br/> |
   

