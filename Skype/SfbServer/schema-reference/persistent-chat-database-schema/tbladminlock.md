---
title: tblAdminLock
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: la tabla tblAdminLock contiene el bloqueo de administrador que se necesita para ejecutar algunos comandos de administrador.
ms.openlocfilehash: bf7537b7d1081bd415ff2e8fe3615864c71f593a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212666"
---
# <a name="tbladminlock"></a><span data-ttu-id="60bf6-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="60bf6-103">tblAdminLock</span></span>
 
<span data-ttu-id="60bf6-104">la tabla tblAdminLock contiene el bloqueo de administrador que se necesita para ejecutar algunos comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="60bf6-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="60bf6-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="60bf6-105">**Columns**</span></span>

|<span data-ttu-id="60bf6-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="60bf6-106">**Column**</span></span>|<span data-ttu-id="60bf6-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="60bf6-107">**Type**</span></span>|<span data-ttu-id="60bf6-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="60bf6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="60bf6-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="60bf6-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="60bf6-110">DateTime, no es nulo</span><span class="sxs-lookup"><span data-stu-id="60bf6-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="60bf6-111">Bloqueo de la fecha de caducidad y la hora.</span><span class="sxs-lookup"><span data-stu-id="60bf6-111">Lock expiration date and time.</span></span> <span data-ttu-id="60bf6-112">El propietario puede ampliar este valor periódicamente.</span><span class="sxs-lookup"><span data-stu-id="60bf6-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="60bf6-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="60bf6-113">lockServerID</span></span>  <br/> |<span data-ttu-id="60bf6-114">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="60bf6-114">int, not null</span></span>  <br/> |<span data-ttu-id="60bf6-115">Identificador del servidor que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="60bf6-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="60bf6-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="60bf6-116">lockActorID</span></span>  <br/> |<span data-ttu-id="60bf6-117">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="60bf6-117">int, not null</span></span>  <br/> |<span data-ttu-id="60bf6-118">Identificador de la entidad de seguridad que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="60bf6-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

