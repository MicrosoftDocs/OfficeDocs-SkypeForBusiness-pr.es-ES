---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType es una tabla de búsqueda estática con tipos de rol y sus conjuntos de permisos asociados.
ms.openlocfilehash: c440463d822b908a89c84eb9c85b70e9daf442be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831530"
---
# <a name="tblroletype"></a><span data-ttu-id="020c5-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="020c5-103">tblRoleType</span></span>
 
<span data-ttu-id="020c5-104">tblRoleType es una tabla de búsqueda estática con tipos de rol y sus conjuntos de permisos asociados.</span><span class="sxs-lookup"><span data-stu-id="020c5-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="020c5-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="020c5-105">**Columns**</span></span>

|<span data-ttu-id="020c5-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="020c5-106">**Column**</span></span>|<span data-ttu-id="020c5-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="020c5-107">**Type**</span></span>|<span data-ttu-id="020c5-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="020c5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="020c5-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="020c5-109">rtypeID</span></span>  <br/> |<span data-ttu-id="020c5-110">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="020c5-110">int, not null</span></span>  <br/> |<span data-ttu-id="020c5-111">Identificador del tipo de rol.</span><span class="sxs-lookup"><span data-stu-id="020c5-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="020c5-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="020c5-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="020c5-113">nvarchar (256), no NULL</span><span class="sxs-lookup"><span data-stu-id="020c5-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="020c5-p101">Descripción del tipo de rol. Existen cuatro roles disponibles:</span><span class="sxs-lookup"><span data-stu-id="020c5-p101">Role type description. There are four available roles:</span></span> <br/>  <span data-ttu-id="020c5-116">Miembro: miembro de salón de chat</span><span class="sxs-lookup"><span data-stu-id="020c5-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="020c5-117">Administrador: administrador de salón de chat</span><span class="sxs-lookup"><span data-stu-id="020c5-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="020c5-118">Miembro con voz: moderador de un salón de chat de tipo auditorio</span><span class="sxs-lookup"><span data-stu-id="020c5-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="020c5-119">Creador: puede crear salones de chat</span><span class="sxs-lookup"><span data-stu-id="020c5-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="020c5-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="020c5-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="020c5-121">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="020c5-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="020c5-p102">Conjunto de permisos del rol. Los valores usados son:</span><span class="sxs-lookup"><span data-stu-id="020c5-p102">Permission set for the role. The used bits are:</span></span> <br/>  <span data-ttu-id="020c5-124">2: True si el rol puede administrar nodos.</span><span class="sxs-lookup"><span data-stu-id="020c5-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="020c5-125">4: True si el rol puede crear nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="020c5-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="020c5-126">7: True si el rol puede unirse a un salón de chat (o salones de chat secundarios de una categoría).</span><span class="sxs-lookup"><span data-stu-id="020c5-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="020c5-127">8: True si el rol puede hablar en un salón de chat (o salones de chat secundarios de una categoría).</span><span class="sxs-lookup"><span data-stu-id="020c5-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="020c5-128">10: True si el rol puede leer el historial de chat incluso cuando no se unió a un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="020c5-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="020c5-p103">11: True si el rol puede ver el salón de chat. (Restricción adicional según factores, como ámbito y visibilidad).</span><span class="sxs-lookup"><span data-stu-id="020c5-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="020c5-131">12: True si el rol puede hablar en un salón de chat de tipo auditorio.</span><span class="sxs-lookup"><span data-stu-id="020c5-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="020c5-132">13: True si el rol puede omitir las reglas de visibilidad al ver nodos.</span><span class="sxs-lookup"><span data-stu-id="020c5-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="020c5-133">**Clave**</span><span class="sxs-lookup"><span data-stu-id="020c5-133">**Key**</span></span>

|<span data-ttu-id="020c5-134">**Columna**</span><span class="sxs-lookup"><span data-stu-id="020c5-134">**Column**</span></span>|<span data-ttu-id="020c5-135">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="020c5-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="020c5-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="020c5-136">rtypeID</span></span>  <br/> |<span data-ttu-id="020c5-137">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="020c5-137">Primary key.</span></span>  <br/> |
   

