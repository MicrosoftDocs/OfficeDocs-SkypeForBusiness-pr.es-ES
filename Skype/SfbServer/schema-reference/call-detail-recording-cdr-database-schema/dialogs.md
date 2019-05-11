---
title: Tabla de cuadros de diálogo en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: En la tabla de cuadros de diálogo es una tabla de apoyo que almacena la información sobre DialogIDs para sesiones de punto a punto.
ms.openlocfilehash: 379956a2c77c60a53e702913d81b25b41dc2fc23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901132"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9e931-103">Tabla de cuadros de diálogo en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9e931-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9e931-104">En la tabla de cuadros de diálogo es una tabla de apoyo que almacena la información sobre DialogIDs para sesiones de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="9e931-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="9e931-105">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9e931-105">**Column**</span></span>|<span data-ttu-id="9e931-106">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="9e931-106">**Data Type**</span></span>|<span data-ttu-id="9e931-107">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="9e931-107">**Key/Index**</span></span>|<span data-ttu-id="9e931-108">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="9e931-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9e931-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="9e931-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="9e931-110">datetime</span><span class="sxs-lookup"><span data-stu-id="9e931-110">datetime</span></span>  <br/> |<span data-ttu-id="9e931-111">Primary</span><span class="sxs-lookup"><span data-stu-id="9e931-111">Primary</span></span>  <br/> |<span data-ttu-id="9e931-112">Tiempo de solicitud de sesión; se utiliza en forma conjunta con SessionIDSeq para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="9e931-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="9e931-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="9e931-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="9e931-114">int</span><span class="sxs-lookup"><span data-stu-id="9e931-114">int</span></span>  <br/> |<span data-ttu-id="9e931-115">Primary</span><span class="sxs-lookup"><span data-stu-id="9e931-115">Primary</span></span>  <br/> |<span data-ttu-id="9e931-116">Número de identificador para identificar la sesión.</span><span class="sxs-lookup"><span data-stu-id="9e931-116">ID number to identify the session.</span></span> <span data-ttu-id="9e931-117">Se utiliza junto con SessionIDTime para identificar de forma exclusiva una sesión.</span><span class="sxs-lookup"><span data-stu-id="9e931-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="9e931-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="9e931-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="9e931-119">int</span><span class="sxs-lookup"><span data-stu-id="9e931-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="9e931-120">Suma de comprobación de la ExternalID.</span><span class="sxs-lookup"><span data-stu-id="9e931-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="9e931-121">Este campo se usa para aumentar la velocidad de las búsquedas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9e931-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="9e931-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="9e931-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="9e931-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="9e931-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="9e931-124">En el identificador de diálogo SIP, que se almacena como un archivo binario.</span><span class="sxs-lookup"><span data-stu-id="9e931-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="9e931-125">El formato del binario es:</span><span class="sxs-lookup"><span data-stu-id="9e931-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="9e931-126">cuadro de diálogo; de etiqueta; para etiqueta</span><span class="sxs-lookup"><span data-stu-id="9e931-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="9e931-127">Estos datos pueden convertirse a formato de texto con esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="9e931-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

