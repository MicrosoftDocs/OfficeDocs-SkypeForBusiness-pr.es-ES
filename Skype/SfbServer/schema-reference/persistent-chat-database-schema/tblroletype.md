---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType es una tabla de búsqueda estática con tipos de roles y sus conjuntos de permisos asociados.
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812908"
---
# <a name="tblroletype"></a><span data-ttu-id="aabee-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="aabee-103">tblRoleType</span></span>
 
<span data-ttu-id="aabee-104">tblRoleType es una tabla de búsqueda estática con tipos de roles y sus conjuntos de permisos asociados.</span><span class="sxs-lookup"><span data-stu-id="aabee-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="aabee-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="aabee-105">**Columns**</span></span>

|<span data-ttu-id="aabee-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="aabee-106">**Column**</span></span>|<span data-ttu-id="aabee-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="aabee-107">**Type**</span></span>|<span data-ttu-id="aabee-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="aabee-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aabee-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="aabee-109">rtypeID</span></span>  <br/> |<span data-ttu-id="aabee-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="aabee-110">int, not null</span></span>  <br/> |<span data-ttu-id="aabee-111">IDENTIFICADOR de tipo de rol.</span><span class="sxs-lookup"><span data-stu-id="aabee-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="aabee-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="aabee-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="aabee-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="aabee-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="aabee-114">Descripción de tipo de rol.</span><span class="sxs-lookup"><span data-stu-id="aabee-114">Role type description.</span></span> <span data-ttu-id="aabee-115">Hay cuatro roles disponibles:</span><span class="sxs-lookup"><span data-stu-id="aabee-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="aabee-116">Miembro: miembro del salón de chat</span><span class="sxs-lookup"><span data-stu-id="aabee-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="aabee-117">Administrador: administrador del salón de chat</span><span class="sxs-lookup"><span data-stu-id="aabee-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="aabee-118">Voz: moderador de un salón de chat de Auditorio</span><span class="sxs-lookup"><span data-stu-id="aabee-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="aabee-119">Creador: puede crear salones de chat</span><span class="sxs-lookup"><span data-stu-id="aabee-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="aabee-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="aabee-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="aabee-121">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="aabee-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="aabee-122">Conjunto de permisos para el rol.</span><span class="sxs-lookup"><span data-stu-id="aabee-122">Permission set for the role.</span></span> <span data-ttu-id="aabee-123">Los bits utilizados son:</span><span class="sxs-lookup"><span data-stu-id="aabee-123">The used bits are:</span></span> <br/>  <span data-ttu-id="aabee-124">2: verdadero si el rol puede administrar nodos.</span><span class="sxs-lookup"><span data-stu-id="aabee-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="aabee-125">4: true si el rol puede crear nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="aabee-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="aabee-126">7: verdadero si el rol puede unirse a un salón de chat (o a salones de chat de niños de una categoría).</span><span class="sxs-lookup"><span data-stu-id="aabee-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="aabee-127">8: verdadero si el rol puede chatear en un salón de chat (o en los salones de chat de los niños de una categoría).</span><span class="sxs-lookup"><span data-stu-id="aabee-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="aabee-128">10: verdadero si el rol puede leer el historial de chats incluso cuando no está unido a un salón de chat.</span><span class="sxs-lookup"><span data-stu-id="aabee-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="aabee-129">11: verdadero si el rol puede ver el salón de chat.</span><span class="sxs-lookup"><span data-stu-id="aabee-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="aabee-130">(Esto se ha refinado con factores como el alcance y la visibilidad).</span><span class="sxs-lookup"><span data-stu-id="aabee-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="aabee-131">12: verdadero si el rol puede chatear en un salón de chat de Auditorio.</span><span class="sxs-lookup"><span data-stu-id="aabee-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="aabee-132">13: verdadero si el rol puede omitir las reglas de visibilidad al ver los nodos.</span><span class="sxs-lookup"><span data-stu-id="aabee-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="aabee-133">**Clave**</span><span class="sxs-lookup"><span data-stu-id="aabee-133">**Key**</span></span>

|<span data-ttu-id="aabee-134">**Columna**</span><span class="sxs-lookup"><span data-stu-id="aabee-134">**Column**</span></span>|<span data-ttu-id="aabee-135">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="aabee-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aabee-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="aabee-136">rtypeID</span></span>  <br/> |<span data-ttu-id="aabee-137">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="aabee-137">Primary key.</span></span>  <br/> |
   

