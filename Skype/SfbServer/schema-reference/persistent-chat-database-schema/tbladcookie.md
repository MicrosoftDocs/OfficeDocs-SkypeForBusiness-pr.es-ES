---
title: tblADCookie
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie contiene las cookies de sincronización de protocolo ligero de acceso a directorios (LDAP) actuales.
ms.openlocfilehash: bc2c0657caa66a0420bc493bf4b688a2a081db36
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tbladcookie"></a><span data-ttu-id="f1bb5-103">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="f1bb5-103">tblADCookie</span></span>
 
<span data-ttu-id="f1bb5-104">tblADCookie contiene las cookies de sincronización de protocolo ligero de acceso a directorios (LDAP) actuales.</span><span class="sxs-lookup"><span data-stu-id="f1bb5-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>
  
<span data-ttu-id="f1bb5-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="f1bb5-105">**Columns**</span></span>

|<span data-ttu-id="f1bb5-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="f1bb5-106">**Column**</span></span>|<span data-ttu-id="f1bb5-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f1bb5-107">**Type**</span></span>|<span data-ttu-id="f1bb5-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f1bb5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f1bb5-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f1bb5-109">prinGuid</span></span>  <br/> |<span data-ttu-id="f1bb5-110">GUID, no nulo</span><span class="sxs-lookup"><span data-stu-id="f1bb5-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="f1bb5-111">GUID principal del dominio que se está supervisando.</span><span class="sxs-lookup"><span data-stu-id="f1bb5-111">Principal GUID of the domain being monitored.</span></span>  <br/> |
|<span data-ttu-id="f1bb5-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="f1bb5-112">prinDCHost</span></span>  <br/> |<span data-ttu-id="f1bb5-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="f1bb5-113">nvarchar (255)</span></span>  <br/> |<span data-ttu-id="f1bb5-114">Nombre de dominio completo (FQDN) del controlador de dominio actual utilizado para Active Sync de servicios de directorio de dominio. Tiene valor informativo.</span><span class="sxs-lookup"><span data-stu-id="f1bb5-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span>  <br/> |
|<span data-ttu-id="f1bb5-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="f1bb5-115">adcContent</span></span>  <br/> |<span data-ttu-id="f1bb5-116">imagen (binario)</span><span class="sxs-lookup"><span data-stu-id="f1bb5-116">image (binary)</span></span>  <br/> |<span data-ttu-id="f1bb5-117">Cookie de sincronización del directorio activo.</span><span class="sxs-lookup"><span data-stu-id="f1bb5-117">Active Directory Sync cookie.</span></span>  <br/> |
|<span data-ttu-id="f1bb5-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="f1bb5-118">lastUpdated</span></span>  <br/> |<span data-ttu-id="f1bb5-119">datetime</span><span class="sxs-lookup"><span data-stu-id="f1bb5-119">datetime</span></span>  <br/> |<span data-ttu-id="f1bb5-120">Marca de hora con la hora de actualización de fila.</span><span class="sxs-lookup"><span data-stu-id="f1bb5-120">Time stamp with the row update time.</span></span>  <br/> |
|<span data-ttu-id="f1bb5-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="f1bb5-121">lockedUntil</span></span>  <br/> |<span data-ttu-id="f1bb5-122">datetime</span><span class="sxs-lookup"><span data-stu-id="f1bb5-122">datetime</span></span>  <br/> |<span data-ttu-id="f1bb5-123">Tiempo hasta que la fila está bloqueada para cambios.</span><span class="sxs-lookup"><span data-stu-id="f1bb5-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="f1bb5-124">Esto forma parte de un mecanismo de interbloqueo de software que asegura que sólo uno de los servicios de chat no la sincronización de directorio activo a la vez.</span><span class="sxs-lookup"><span data-stu-id="f1bb5-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span>  <br/> |
   
<span data-ttu-id="f1bb5-125">**Claves**</span><span class="sxs-lookup"><span data-stu-id="f1bb5-125">**Keys**</span></span>

|<span data-ttu-id="f1bb5-126">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="f1bb5-126">**Column(s)**</span></span>|<span data-ttu-id="f1bb5-127">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f1bb5-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f1bb5-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f1bb5-128">prinGuid</span></span>  <br/> |<span data-ttu-id="f1bb5-129">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="f1bb5-129">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f1bb5-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="f1bb5-130">prinGuid</span></span>  <br/> |<span data-ttu-id="f1bb5-131">Clave externa con la búsqueda en la tabla Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="f1bb5-131">Foreign key with lookup in Principal.prinGuid table.</span></span>  <br/> |
   

