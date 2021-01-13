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
# <a name="tblcompliancefanout"></a><span data-ttu-id="a4a07-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="a4a07-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="a4a07-104">La tabla ComplianceFanout contiene todos los servidores que han procesado un evento de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a4a07-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="a4a07-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="a4a07-105">**Columns**</span></span>

|<span data-ttu-id="a4a07-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a4a07-106">**Column**</span></span>|<span data-ttu-id="a4a07-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a4a07-107">**Type**</span></span>|<span data-ttu-id="a4a07-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a4a07-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4a07-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="a4a07-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="a4a07-110">entero</span><span class="sxs-lookup"><span data-stu-id="a4a07-110">int</span></span>  <br/> |<span data-ttu-id="a4a07-111">Id. del evento</span><span class="sxs-lookup"><span data-stu-id="a4a07-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="a4a07-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="a4a07-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="a4a07-113">entero</span><span class="sxs-lookup"><span data-stu-id="a4a07-113">int</span></span>  <br/> |<span data-ttu-id="a4a07-114">Identidad del servidor (correspondiente a la tabla ServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="a4a07-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="a4a07-115">**Clave**</span><span class="sxs-lookup"><span data-stu-id="a4a07-115">**Key**</span></span>

|<span data-ttu-id="a4a07-116">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a4a07-116">**Column**</span></span>|<span data-ttu-id="a4a07-117">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a4a07-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a4a07-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="a4a07-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="a4a07-119">Clave externa con búsqueda en la tabla ComplianceData.cmplEventID.</span><span class="sxs-lookup"><span data-stu-id="a4a07-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

