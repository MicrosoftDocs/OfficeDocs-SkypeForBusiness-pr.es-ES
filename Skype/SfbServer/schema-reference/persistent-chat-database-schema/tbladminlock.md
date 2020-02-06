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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814698"
---
# <a name="tbladminlock"></a><span data-ttu-id="1d0bb-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="1d0bb-103">tblAdminLock</span></span>
 
<span data-ttu-id="1d0bb-104">tblAdminLock contiene el bloqueo de administrador necesario para ejecutar algunos comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="1d0bb-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="1d0bb-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="1d0bb-105">**Columns**</span></span>

|<span data-ttu-id="1d0bb-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1d0bb-106">**Column**</span></span>|<span data-ttu-id="1d0bb-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1d0bb-107">**Type**</span></span>|<span data-ttu-id="1d0bb-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1d0bb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d0bb-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="1d0bb-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="1d0bb-110">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="1d0bb-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="1d0bb-111">Bloquear la fecha y la hora de expiración.</span><span class="sxs-lookup"><span data-stu-id="1d0bb-111">Lock expiration date and time.</span></span> <span data-ttu-id="1d0bb-112">El propietario puede extender este valor de forma periódica.</span><span class="sxs-lookup"><span data-stu-id="1d0bb-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="1d0bb-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="1d0bb-113">lockServerID</span></span>  <br/> |<span data-ttu-id="1d0bb-114">int, not null</span><span class="sxs-lookup"><span data-stu-id="1d0bb-114">int, not null</span></span>  <br/> |<span data-ttu-id="1d0bb-115">IDENTIFICADOR del servidor que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1d0bb-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="1d0bb-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="1d0bb-116">lockActorID</span></span>  <br/> |<span data-ttu-id="1d0bb-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="1d0bb-117">int, not null</span></span>  <br/> |<span data-ttu-id="1d0bb-118">IDENTIFICADOR de la entidad de identidad que posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1d0bb-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

