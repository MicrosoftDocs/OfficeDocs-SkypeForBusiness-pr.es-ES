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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212631"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="a2c31-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="a2c31-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="a2c31-104">la tabla Compliancefanout contiene todos los servidores que procesan un evento de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a2c31-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="a2c31-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="a2c31-105">**Columns**</span></span>

|<span data-ttu-id="a2c31-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a2c31-106">**Column**</span></span>|<span data-ttu-id="a2c31-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a2c31-107">**Type**</span></span>|<span data-ttu-id="a2c31-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a2c31-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a2c31-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="a2c31-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="a2c31-110">int</span><span class="sxs-lookup"><span data-stu-id="a2c31-110">int</span></span>  <br/> |<span data-ttu-id="a2c31-111">Identificador de evento.</span><span class="sxs-lookup"><span data-stu-id="a2c31-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="a2c31-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="a2c31-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="a2c31-113">int</span><span class="sxs-lookup"><span data-stu-id="a2c31-113">int</span></span>  <br/> |<span data-ttu-id="a2c31-114">Identidad del servidor (correspondiente a la tabla tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="a2c31-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="a2c31-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="a2c31-115">**Key**</span></span>

|<span data-ttu-id="a2c31-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a2c31-116">**Column**</span></span>|<span data-ttu-id="a2c31-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a2c31-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a2c31-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="a2c31-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="a2c31-119">Clave externa con búsqueda en la tabla Compliancedata.cmpleventid.</span><span class="sxs-lookup"><span data-stu-id="a2c31-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

