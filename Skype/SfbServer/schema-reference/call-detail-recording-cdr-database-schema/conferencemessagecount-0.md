---
title: Vista ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La vista ConferenceMessageCount almacena información acerca de cuántos mensajes envió un usuario a una conferencia. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: a766e63fbca5c30cec3c3891c9ccfc2355f16d2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815388"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="fc704-104">Vista ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="fc704-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="fc704-105">La vista ConferenceMessageCount almacena información acerca de cuántos mensajes envió un usuario a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="fc704-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="fc704-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fc704-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc704-107">La vista ConferenceMessageCount contiene todas las columnas de la [vista ConferenceSessionDetails](conferencesessiondetails.md) además de las columnas que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="fc704-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="fc704-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="fc704-108">**Column**</span></span>|<span data-ttu-id="fc704-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="fc704-109">**Data Type**</span></span>|<span data-ttu-id="fc704-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="fc704-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fc704-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="fc704-111">**UserUri**</span></span> <br/> |<span data-ttu-id="fc704-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fc704-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="fc704-113">Identificador URI del usuario que envió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="fc704-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="fc704-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="fc704-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="fc704-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fc704-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fc704-116">Tipo de URI del usuario que envió los mensajes.</span><span class="sxs-lookup"><span data-stu-id="fc704-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="fc704-117">Para obtener más información, consulte la [tabla UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="fc704-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="fc704-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="fc704-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="fc704-119">identificador</span><span class="sxs-lookup"><span data-stu-id="fc704-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="fc704-120">Espacio empresarial del usuario que envió los mensajes.</span><span class="sxs-lookup"><span data-stu-id="fc704-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="fc704-121">Para obtener más información, consulte la [tabla de inquilinos](tenants.md) .</span><span class="sxs-lookup"><span data-stu-id="fc704-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="fc704-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="fc704-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="fc704-123">smallint</span><span class="sxs-lookup"><span data-stu-id="fc704-123">smallint</span></span>  <br/> |<span data-ttu-id="fc704-124">Número de mensajes enviados por el usuario durante la sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="fc704-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

