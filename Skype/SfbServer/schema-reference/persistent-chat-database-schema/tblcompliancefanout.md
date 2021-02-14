---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: La tabla ComplianceFanout contiene todos los servidores que han procesado un evento de cumplimiento.
ms.openlocfilehash: 75e232cd464a2199b490e555c0fab79ded119c94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809800"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="9845b-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="9845b-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="9845b-104">La tabla ComplianceFanout contiene todos los servidores que han procesado un evento de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9845b-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="9845b-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="9845b-105">**Columns**</span></span>

|<span data-ttu-id="9845b-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9845b-106">**Column**</span></span>|<span data-ttu-id="9845b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9845b-107">**Type**</span></span>|<span data-ttu-id="9845b-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9845b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9845b-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="9845b-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="9845b-110">entero</span><span class="sxs-lookup"><span data-stu-id="9845b-110">int</span></span>  <br/> |<span data-ttu-id="9845b-111">Id. del evento</span><span class="sxs-lookup"><span data-stu-id="9845b-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="9845b-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="9845b-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="9845b-113">entero</span><span class="sxs-lookup"><span data-stu-id="9845b-113">int</span></span>  <br/> |<span data-ttu-id="9845b-114">Identidad del servidor (correspondiente a la tabla ServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="9845b-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="9845b-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9845b-115">**Key**</span></span>

|<span data-ttu-id="9845b-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9845b-116">**Column**</span></span>|<span data-ttu-id="9845b-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9845b-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9845b-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="9845b-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="9845b-119">Clave externa con búsqueda en la tabla ComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="9845b-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

