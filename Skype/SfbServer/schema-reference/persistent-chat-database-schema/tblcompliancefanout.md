---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contiene todos los servidores que procesaron un evento de cumplimiento.
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814658"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="d5fe3-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="d5fe3-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="d5fe3-104">tblComplianceFanout contiene todos los servidores que procesaron un evento de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="d5fe3-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="d5fe3-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="d5fe3-105">**Columns**</span></span>

|<span data-ttu-id="d5fe3-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d5fe3-106">**Column**</span></span>|<span data-ttu-id="d5fe3-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d5fe3-107">**Type**</span></span>|<span data-ttu-id="d5fe3-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d5fe3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d5fe3-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="d5fe3-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="d5fe3-110">int</span><span class="sxs-lookup"><span data-stu-id="d5fe3-110">int</span></span>  <br/> |<span data-ttu-id="d5fe3-111">IDENTIFICADOR de evento.</span><span class="sxs-lookup"><span data-stu-id="d5fe3-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="d5fe3-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="d5fe3-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="d5fe3-113">int</span><span class="sxs-lookup"><span data-stu-id="d5fe3-113">int</span></span>  <br/> |<span data-ttu-id="d5fe3-114">Identidad del servidor (correspondiente a la tabla tblServerIdentity. serverID).</span><span class="sxs-lookup"><span data-stu-id="d5fe3-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="d5fe3-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d5fe3-115">**Key**</span></span>

|<span data-ttu-id="d5fe3-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d5fe3-116">**Column**</span></span>|<span data-ttu-id="d5fe3-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d5fe3-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d5fe3-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="d5fe3-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="d5fe3-119">Clave externa con la búsqueda en la tabla tblComplianceData. cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="d5fe3-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

