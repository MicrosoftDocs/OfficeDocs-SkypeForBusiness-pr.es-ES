---
title: tblPreference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contiene las preferencias de cliente de los usuarios. Por lo general, esto se usa en los clientes anteriores a Lync 2013.
ms.openlocfilehash: c76c62ec453ab1a152738cb16d76e5c5394a2a98
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375946"
---
# <a name="tblpreference"></a><span data-ttu-id="45800-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="45800-104">tblPreference</span></span>

<span data-ttu-id="45800-105">tblPreference contiene las preferencias de cliente de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="45800-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="45800-106">Por lo general, esto se usa en los clientes anteriores a Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="45800-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="45800-107">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="45800-107">**Columns**</span></span>


| <span data-ttu-id="45800-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="45800-108">**Column**</span></span>            | <span data-ttu-id="45800-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="45800-109">**Type**</span></span>                        | <span data-ttu-id="45800-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="45800-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="45800-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="45800-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="45800-112">nvarchar (255), no es nulo</span><span class="sxs-lookup"><span data-stu-id="45800-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="45800-113">Etiqueta con un formato como: \<uri de sip del usuario\></span><span class="sxs-lookup"><span data-stu-id="45800-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="45800-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="45800-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="45800-115">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="45800-115">int, not null</span></span>  <br/>            | <span data-ttu-id="45800-116">Número secuencial (por etiqueta) para el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="45800-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="45800-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="45800-117">prefContent</span></span>  <br/>    | <span data-ttu-id="45800-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="45800-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="45800-119">Contenido codificado.</span><span class="sxs-lookup"><span data-stu-id="45800-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="45800-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="45800-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="45800-121">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="45800-121">int, not null</span></span>  <br/>            | <span data-ttu-id="45800-122">Identificador de la entidad de seguridad que se ha actualizado la preferencia.</span><span class="sxs-lookup"><span data-stu-id="45800-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="45800-123">**Clave**</span><span class="sxs-lookup"><span data-stu-id="45800-123">**Key**</span></span>

|<span data-ttu-id="45800-124">**Columna**</span><span class="sxs-lookup"><span data-stu-id="45800-124">**Column**</span></span>|<span data-ttu-id="45800-125">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="45800-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="45800-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="45800-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="45800-127">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="45800-127">Primary key.</span></span>  <br/> |


