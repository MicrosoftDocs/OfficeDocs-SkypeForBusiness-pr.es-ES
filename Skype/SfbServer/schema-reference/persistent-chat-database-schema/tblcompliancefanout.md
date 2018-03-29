---
title: tblComplianceFanout
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contiene todos los servidores que se procesan un evento de conformidad.
ms.openlocfilehash: f9141a6f7144c20d8039756387a889cc25cc8f50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="06024-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="06024-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="06024-104">tblComplianceFanout contiene todos los servidores que se procesan un evento de conformidad.</span><span class="sxs-lookup"><span data-stu-id="06024-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="06024-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="06024-105">**Columns**</span></span>

|<span data-ttu-id="06024-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="06024-106">**Column**</span></span>|<span data-ttu-id="06024-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="06024-107">**Type**</span></span>|<span data-ttu-id="06024-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="06024-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="06024-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="06024-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="06024-110">int</span><span class="sxs-lookup"><span data-stu-id="06024-110">int</span></span>  <br/> |<span data-ttu-id="06024-111">ID de evento.</span><span class="sxs-lookup"><span data-stu-id="06024-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="06024-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="06024-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="06024-113">int</span><span class="sxs-lookup"><span data-stu-id="06024-113">int</span></span>  <br/> |<span data-ttu-id="06024-114">Identidad del servidor (correspondiente a la tabla de tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="06024-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="06024-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="06024-115">**Key**</span></span>

|<span data-ttu-id="06024-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="06024-116">**Column**</span></span>|<span data-ttu-id="06024-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="06024-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="06024-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="06024-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="06024-119">Clave externa con la búsqueda en la tabla tblComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="06024-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

