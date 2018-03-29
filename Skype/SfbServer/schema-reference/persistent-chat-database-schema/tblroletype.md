---
title: tblRoleType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType es una tabla de consulta estática con tipos de funciones y sus conjuntos de permisos asociados.
ms.openlocfilehash: 2a380539c547f4ba6eb911f7e5247056c59a73ca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblroletype"></a><span data-ttu-id="4d504-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="4d504-103">tblRoleType</span></span>
 
<span data-ttu-id="4d504-104">tblRoleType es una tabla de consulta estática con tipos de funciones y sus conjuntos de permisos asociados.</span><span class="sxs-lookup"><span data-stu-id="4d504-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="4d504-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="4d504-105">**Columns**</span></span>

|<span data-ttu-id="4d504-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="4d504-106">**Column**</span></span>|<span data-ttu-id="4d504-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="4d504-107">**Type**</span></span>|<span data-ttu-id="4d504-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4d504-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4d504-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="4d504-109">rtypeID</span></span>  <br/> |<span data-ttu-id="4d504-110">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="4d504-110">int, not null</span></span>  <br/> |<span data-ttu-id="4d504-111">ID de tipo de papel.</span><span class="sxs-lookup"><span data-stu-id="4d504-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="4d504-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="4d504-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="4d504-113">nvarchar (256), no nulo</span><span class="sxs-lookup"><span data-stu-id="4d504-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="4d504-114">Descripción del tipo de papel.</span><span class="sxs-lookup"><span data-stu-id="4d504-114">Role type description.</span></span> <span data-ttu-id="4d504-115">Hay cuatro roles disponibles:</span><span class="sxs-lookup"><span data-stu-id="4d504-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="4d504-116">Miembro: miembro de la sala de Chat</span><span class="sxs-lookup"><span data-stu-id="4d504-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="4d504-117">Administrador: Administrador de salón de Chat</span><span class="sxs-lookup"><span data-stu-id="4d504-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="4d504-118">Sonora: Moderador de un salón de chat de auditorio</span><span class="sxs-lookup"><span data-stu-id="4d504-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="4d504-119">Creador: Puede crear salones de chat</span><span class="sxs-lookup"><span data-stu-id="4d504-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="4d504-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="4d504-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="4d504-121">bigint, no nulo</span><span class="sxs-lookup"><span data-stu-id="4d504-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="4d504-122">Conjunto de permisos para la función.</span><span class="sxs-lookup"><span data-stu-id="4d504-122">Permission set for the role.</span></span> <span data-ttu-id="4d504-123">Los bits utilizados son:</span><span class="sxs-lookup"><span data-stu-id="4d504-123">The used bits are:</span></span> <br/>  <span data-ttu-id="4d504-124">2: true si la función puede administrar nodos.</span><span class="sxs-lookup"><span data-stu-id="4d504-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="4d504-125">4: true si la función puede crear niños nodos.</span><span class="sxs-lookup"><span data-stu-id="4d504-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="4d504-126">7: true si la función puede unirse a un salón de chat (o salones de chat de niños de una categoría).</span><span class="sxs-lookup"><span data-stu-id="4d504-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="4d504-127">8: true si la función puede conversar en un salón de chat (o hijos salones de chat de una categoría).</span><span class="sxs-lookup"><span data-stu-id="4d504-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="4d504-128">10: true si la función puede leer el historial de charla, incluso cuando no está unido a un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="4d504-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="4d504-129">11: true si la función puede ver el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="4d504-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="4d504-130">(Esto se refina por factores tales como el ámbito y visibilidad.)</span><span class="sxs-lookup"><span data-stu-id="4d504-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="4d504-131">12: true si la función puede conversar en un salón de chat de auditorio.</span><span class="sxs-lookup"><span data-stu-id="4d504-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="4d504-132">13: true si la función puede omitir las reglas de visibilidad al ver los nodos.</span><span class="sxs-lookup"><span data-stu-id="4d504-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="4d504-133">**Clave**</span><span class="sxs-lookup"><span data-stu-id="4d504-133">**Key**</span></span>

|<span data-ttu-id="4d504-134">**Columna**</span><span class="sxs-lookup"><span data-stu-id="4d504-134">**Column**</span></span>|<span data-ttu-id="4d504-135">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="4d504-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4d504-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="4d504-136">rtypeID</span></span>  <br/> |<span data-ttu-id="4d504-137">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="4d504-137">Primary key.</span></span>  <br/> |
   

