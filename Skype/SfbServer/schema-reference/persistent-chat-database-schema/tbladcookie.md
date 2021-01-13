---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contiene las cookies actuales de sincronización del Protocolo ligero de acceso a directorios (LDAP).
ms.openlocfilehash: 78a477399da811e674bb5a4493e61100acdd4782
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814760"
---
# <a name="tbladcookie"></a><span data-ttu-id="e8c28-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="e8c28-103">tblADCookie</span></span>
 
<span data-ttu-id="e8c28-104">tblADCookie contiene las cookies actuales de sincronización del Protocolo ligero de acceso a directorios (LDAP).</span><span class="sxs-lookup"><span data-stu-id="e8c28-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="e8c28-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e8c28-105">**Columns**</span></span>

|<span data-ttu-id="e8c28-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e8c28-106">**Column**</span></span>|<span data-ttu-id="e8c28-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e8c28-107">**Type**</span></span>|<span data-ttu-id="e8c28-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e8c28-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e8c28-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e8c28-109">prinGuid</span></span>  <br/> |<span data-ttu-id="e8c28-110">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="e8c28-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="e8c28-111">GUID de entidad de seguridad del dominio supervisado.</span><span class="sxs-lookup"><span data-stu-id="e8c28-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="e8c28-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="e8c28-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="e8c28-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="e8c28-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="e8c28-114">Nombre de dominio completo (FQDN) del controlador de dominio actual usado para la sincronización de servicios de dominio de Active Directory. Tiene un valor informativo.</span><span class="sxs-lookup"><span data-stu-id="e8c28-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="e8c28-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="e8c28-115">adcContent</span></span>  <br/> |<span data-ttu-id="e8c28-116">imagen (binario)</span><span class="sxs-lookup"><span data-stu-id="e8c28-116">image (binary)</span></span>  <br/> |<span data-ttu-id="e8c28-117">Cookie de sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e8c28-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="e8c28-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="e8c28-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="e8c28-119">datetime</span><span class="sxs-lookup"><span data-stu-id="e8c28-119">datetime</span></span>  <br/> |<span data-ttu-id="e8c28-120">Marca de tiempo con la hora de actualización de la fila.</span><span class="sxs-lookup"><span data-stu-id="e8c28-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="e8c28-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="e8c28-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="e8c28-122">datetime</span><span class="sxs-lookup"><span data-stu-id="e8c28-122">datetime</span></span>  <br/> |<span data-ttu-id="e8c28-p101">Fecha/hora en que finalizará el bloqueo de la fila para efectuar cambios. Esto forma parte del mecanismo de bloqueo de software que garantiza que solo uno de los servicios de chat realice una sincronización de Active Directory por vez.</span><span class="sxs-lookup"><span data-stu-id="e8c28-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="e8c28-125">**Keys**</span><span class="sxs-lookup"><span data-stu-id="e8c28-125">**Keys**</span></span>

|<span data-ttu-id="e8c28-126">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="e8c28-126">**Column(s)**</span></span>|<span data-ttu-id="e8c28-127">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e8c28-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e8c28-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e8c28-128">prinGuid</span></span>  <br/> |<span data-ttu-id="e8c28-129">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="e8c28-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e8c28-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="e8c28-130">prinGuid</span></span>  <br/> |<span data-ttu-id="e8c28-131">Clave externa con búsqueda en la tabla Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="e8c28-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

