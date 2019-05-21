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
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout contiene todos los servidores que procesaron un evento de cumplimiento.
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295506"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="1f4a7-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="1f4a7-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="1f4a7-104">tblComplianceFanout contiene todos los servidores que procesaron un evento de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="1f4a7-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="1f4a7-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="1f4a7-105">**Columns**</span></span>

|<span data-ttu-id="1f4a7-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1f4a7-106">**Column**</span></span>|<span data-ttu-id="1f4a7-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1f4a7-107">**Type**</span></span>|<span data-ttu-id="1f4a7-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1f4a7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1f4a7-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="1f4a7-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="1f4a7-110">int</span><span class="sxs-lookup"><span data-stu-id="1f4a7-110">int</span></span>  <br/> |<span data-ttu-id="1f4a7-111">IDENTIFICADOR de evento.</span><span class="sxs-lookup"><span data-stu-id="1f4a7-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="1f4a7-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="1f4a7-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="1f4a7-113">int</span><span class="sxs-lookup"><span data-stu-id="1f4a7-113">int</span></span>  <br/> |<span data-ttu-id="1f4a7-114">Identidad del servidor (correspondiente a la tabla tblServerIdentity. serverID).</span><span class="sxs-lookup"><span data-stu-id="1f4a7-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="1f4a7-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="1f4a7-115">**Key**</span></span>

|<span data-ttu-id="1f4a7-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1f4a7-116">**Column**</span></span>|<span data-ttu-id="1f4a7-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1f4a7-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1f4a7-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="1f4a7-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="1f4a7-119">Clave externa con la búsqueda en la tabla tblComplianceData. cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="1f4a7-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

