---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: la tabla Compliancefanout contiene todos los servidores que procesan un evento de cumplimiento.
ms.openlocfilehash: 002ffe3fd825dd90a5223dca06316ff3a60fddd9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929927"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="78ab2-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="78ab2-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="78ab2-104">la tabla Compliancefanout contiene todos los servidores que procesan un evento de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="78ab2-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="78ab2-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="78ab2-105">**Columns**</span></span>

|<span data-ttu-id="78ab2-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="78ab2-106">**Column**</span></span>|<span data-ttu-id="78ab2-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="78ab2-107">**Type**</span></span>|<span data-ttu-id="78ab2-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="78ab2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="78ab2-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="78ab2-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="78ab2-110">int</span><span class="sxs-lookup"><span data-stu-id="78ab2-110">int</span></span>  <br/> |<span data-ttu-id="78ab2-111">Identificador de evento.</span><span class="sxs-lookup"><span data-stu-id="78ab2-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="78ab2-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="78ab2-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="78ab2-113">int</span><span class="sxs-lookup"><span data-stu-id="78ab2-113">int</span></span>  <br/> |<span data-ttu-id="78ab2-114">Identidad del servidor (correspondiente a la tabla tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="78ab2-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="78ab2-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="78ab2-115">**Key**</span></span>

|<span data-ttu-id="78ab2-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="78ab2-116">**Column**</span></span>|<span data-ttu-id="78ab2-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="78ab2-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="78ab2-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="78ab2-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="78ab2-119">Clave externa con búsqueda en la tabla Compliancedata.cmpleventid.</span><span class="sxs-lookup"><span data-stu-id="78ab2-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

