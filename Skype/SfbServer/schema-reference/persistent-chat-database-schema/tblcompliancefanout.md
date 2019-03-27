---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: la tabla Compliancefanout contiene todos los servidores que procesan un evento de cumplimiento.
ms.openlocfilehash: 7f24b1a78dab16b43036734e21d5a8a9b876ca7a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874062"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="1720f-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="1720f-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="1720f-104">la tabla Compliancefanout contiene todos los servidores que procesan un evento de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="1720f-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="1720f-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="1720f-105">**Columns**</span></span>

|<span data-ttu-id="1720f-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1720f-106">**Column**</span></span>|<span data-ttu-id="1720f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1720f-107">**Type**</span></span>|<span data-ttu-id="1720f-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1720f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1720f-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="1720f-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="1720f-110">int</span><span class="sxs-lookup"><span data-stu-id="1720f-110">int</span></span>  <br/> |<span data-ttu-id="1720f-111">Identificador de evento.</span><span class="sxs-lookup"><span data-stu-id="1720f-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="1720f-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="1720f-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="1720f-113">int</span><span class="sxs-lookup"><span data-stu-id="1720f-113">int</span></span>  <br/> |<span data-ttu-id="1720f-114">Identidad del servidor (correspondiente a la tabla tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="1720f-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="1720f-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="1720f-115">**Key**</span></span>

|<span data-ttu-id="1720f-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1720f-116">**Column**</span></span>|<span data-ttu-id="1720f-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1720f-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1720f-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="1720f-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="1720f-119">Clave externa con búsqueda en la tabla Compliancedata.cmpleventid.</span><span class="sxs-lookup"><span data-stu-id="1720f-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

