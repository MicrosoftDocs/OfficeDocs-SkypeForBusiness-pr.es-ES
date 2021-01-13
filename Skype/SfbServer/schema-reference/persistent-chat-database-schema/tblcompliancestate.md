---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contiene información de estado de cumplimiento sobre todo el grupo de servidores.
ms.openlocfilehash: 82c775b315976b0e5b112c476a41a8f5adc6a24c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809730"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="fcb6d-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="fcb6d-103">tblComplianceState</span></span>
 
<span data-ttu-id="fcb6d-104">tblComplianceState contiene información de estado de cumplimiento sobre todo el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="fcb6d-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="fcb6d-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="fcb6d-105">**Columns**</span></span>

|<span data-ttu-id="fcb6d-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="fcb6d-106">**Column**</span></span>|<span data-ttu-id="fcb6d-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fcb6d-107">**Type**</span></span>|<span data-ttu-id="fcb6d-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="fcb6d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fcb6d-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="fcb6d-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="fcb6d-110">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="fcb6d-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="fcb6d-111">ID del último evento de cumplimiento procesado.</span><span class="sxs-lookup"><span data-stu-id="fcb6d-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="fcb6d-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="fcb6d-112">activeServerID</span></span>  <br/> |<span data-ttu-id="fcb6d-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="fcb6d-113">int, not null</span></span>  <br/> |<span data-ttu-id="fcb6d-114">Identificador del servidor de cumplimiento que contiene el bloqueo exclusivo en la base de datos o, si no lo hay, -1.</span><span class="sxs-lookup"><span data-stu-id="fcb6d-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="fcb6d-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="fcb6d-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="fcb6d-116">datetime2, not null</span><span class="sxs-lookup"><span data-stu-id="fcb6d-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="fcb6d-117">Fecha y hora de expiración del bloqueo (si activeServerID no es -1).</span><span class="sxs-lookup"><span data-stu-id="fcb6d-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

