---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295527"
---
# <a name="tbladminlock"></a><span data-ttu-id="ee43e-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="ee43e-103">tblAdminLock</span></span>
 
<span data-ttu-id="ee43e-104">tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="ee43e-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="ee43e-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="ee43e-105">**Columns**</span></span>

|<span data-ttu-id="ee43e-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ee43e-106">**Column**</span></span>|<span data-ttu-id="ee43e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ee43e-107">**Type**</span></span>|<span data-ttu-id="ee43e-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ee43e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ee43e-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="ee43e-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="ee43e-110">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="ee43e-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="ee43e-111">Bloquear la fecha y la hora de expiración.</span><span class="sxs-lookup"><span data-stu-id="ee43e-111">Lock expiration date and time.</span></span> <span data-ttu-id="ee43e-112">El propietario puede extender este valor de forma periódica.</span><span class="sxs-lookup"><span data-stu-id="ee43e-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="ee43e-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="ee43e-113">lockServerID</span></span>  <br/> |<span data-ttu-id="ee43e-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="ee43e-114">int, not null</span></span>  <br/> |<span data-ttu-id="ee43e-115">IDENTIFICADOR del servidor que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ee43e-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="ee43e-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="ee43e-116">lockActorID</span></span>  <br/> |<span data-ttu-id="ee43e-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="ee43e-117">int, not null</span></span>  <br/> |<span data-ttu-id="ee43e-118">IDENTIFICADOR de la entidad de identidad que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ee43e-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

