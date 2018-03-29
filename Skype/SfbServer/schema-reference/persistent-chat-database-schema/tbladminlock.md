---
title: tblAdminLock
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contiene el bloqueo del administrador que se necesita para ejecutar algunos comandos de administrador.
ms.openlocfilehash: 919ead84ed9baab859e1e85eb2f30f5ff6902531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tbladminlock"></a><span data-ttu-id="9708b-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="9708b-103">tblAdminLock</span></span>
 
<span data-ttu-id="9708b-104">tblAdminLock contiene el bloqueo del administrador que se necesita para ejecutar algunos comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="9708b-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="9708b-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="9708b-105">**Columns**</span></span>

|<span data-ttu-id="9708b-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9708b-106">**Column**</span></span>|<span data-ttu-id="9708b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9708b-107">**Type**</span></span>|<span data-ttu-id="9708b-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9708b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9708b-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="9708b-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="9708b-110">fecha y hora, no nulo</span><span class="sxs-lookup"><span data-stu-id="9708b-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="9708b-111">Bloqueo de fecha de vencimiento y la hora.</span><span class="sxs-lookup"><span data-stu-id="9708b-111">Lock expiration date and time.</span></span> <span data-ttu-id="9708b-112">El propietario puede extender este valor periódicamente.</span><span class="sxs-lookup"><span data-stu-id="9708b-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="9708b-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="9708b-113">lockServerID</span></span>  <br/> |<span data-ttu-id="9708b-114">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="9708b-114">int, not null</span></span>  <br/> |<span data-ttu-id="9708b-115">Id. del servidor que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9708b-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="9708b-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="9708b-116">lockActorID</span></span>  <br/> |<span data-ttu-id="9708b-117">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="9708b-117">int, not null</span></span>  <br/> |<span data-ttu-id="9708b-118">Identificador de la entidad de seguridad que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9708b-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

