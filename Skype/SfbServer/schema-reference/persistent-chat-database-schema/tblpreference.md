---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene las preferencias de cliente de los usuarios. Esto suele ser usado por clientes anteriores a Lync 2013.
ms.openlocfilehash: 96cd017dd67a05f3240269f5bdcbd23f30fffd28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815910"
---
# <a name="tblpreference"></a><span data-ttu-id="65315-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="65315-104">tblPreference</span></span>

<span data-ttu-id="65315-105">tblPreference contiene las preferencias de cliente de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="65315-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="65315-106">Esto suele ser usado por clientes anteriores a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="65315-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="65315-107">**Columns**</span><span class="sxs-lookup"><span data-stu-id="65315-107">**Columns**</span></span>


| <span data-ttu-id="65315-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="65315-108">**Column**</span></span>            | <span data-ttu-id="65315-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="65315-109">**Type**</span></span>                        | <span data-ttu-id="65315-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="65315-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="65315-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="65315-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="65315-112">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="65315-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="65315-113">Etiqueta con un formato como: \<user sip uri\></span><span class="sxs-lookup"><span data-stu-id="65315-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="65315-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="65315-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="65315-115">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="65315-115">int, not null</span></span>  <br/>            | <span data-ttu-id="65315-116">Número secuencial (por etiqueta) para el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="65315-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="65315-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="65315-117">prefContent</span></span>  <br/>    | <span data-ttu-id="65315-118">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="65315-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="65315-119">Contenido codificado.</span><span class="sxs-lookup"><span data-stu-id="65315-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="65315-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="65315-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="65315-121">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="65315-121">int, not null</span></span>  <br/>            | <span data-ttu-id="65315-122">Identificador de la entidad de seguridad que ha actualizado la preferencia.</span><span class="sxs-lookup"><span data-stu-id="65315-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="65315-123">**Clave**</span><span class="sxs-lookup"><span data-stu-id="65315-123">**Key**</span></span>

|<span data-ttu-id="65315-124">**Columna**</span><span class="sxs-lookup"><span data-stu-id="65315-124">**Column**</span></span>|<span data-ttu-id="65315-125">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="65315-125">**Description**</span></span>|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |<span data-ttu-id="65315-126">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="65315-126">Primary key.</span></span>  <br/> |


