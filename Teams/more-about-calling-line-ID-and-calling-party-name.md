---
title: Más información sobre Identificadores de línea de la llamada entrante y nombres para mostrar a la persona que llama
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Obtenga información sobre por qué necesita agregar a una persona autorizada que pueda realizar cambios en la cuenta al usar el Asistente para nueva portabilidad de número local.
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255403"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="0d367-103">Más información sobre Identificadores de línea de la llamada entrante y nombres para mostrar a la persona que llama</span><span class="sxs-lookup"><span data-stu-id="0d367-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="0d367-104">El identificador de llamada, como se suele denominar, se compone realmente de dos partes de información identificables hacia el usuario:</span><span class="sxs-lookup"><span data-stu-id="0d367-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="0d367-105">Un número de teléfono (generalmente denominado ID de línea de llamada o CLID)</span><span class="sxs-lookup"><span data-stu-id="0d367-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="0d367-106">Nombre del usuario que llama (generalmente conocido como CNAM), que puede tener hasta 15 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="0d367-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="0d367-107">Cuando se realiza una llamada, el CLID (número de teléfono) se enruta al operador de destino (también conocido como el operador de terminación).</span><span class="sxs-lookup"><span data-stu-id="0d367-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="0d367-108">La información CNAM de la llamada se puede o no enrutar con la llamada, ya que esto depende de cómo el país haya implementado el CNAM (si es necesario).</span><span class="sxs-lookup"><span data-stu-id="0d367-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="0d367-109">La confiabilidad de la entrega CNAM con la llamada varía según el país y los operadores que se encargan de la llamada, ya sea como transportista intermedio o de terminación.</span><span class="sxs-lookup"><span data-stu-id="0d367-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="0d367-110">Clid & transmisión CNAM es la responsabilidad del operador de terminación en la medida en que el operador de terminación debe admitir la funcionalidad CNAM de CLID & y proporcionar registros actualizados para ambos valores.</span><span class="sxs-lookup"><span data-stu-id="0d367-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="0d367-111">Microsoft proporciona valores CLID de forma fiable al crear llamadas, pero es posible que estos valores no se mantengan intactos cuando pasen por un operador intermedio o el operador de terminación.</span><span class="sxs-lookup"><span data-stu-id="0d367-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="0d367-112">Desafortunadamente, en el caso de que el valor de CLID cambie, se oja o truncará por el operador intermedio o de terminación, Microsoft tendrá poco o ningún recurso para corregir estos problemas en la red telefónica pública.</span><span class="sxs-lookup"><span data-stu-id="0d367-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="0d367-113">Las incoherencias en CNAM pueden deberse a retrasos en los operadores intermedios o de terminación que actualizan información CNAM en bases de datos relevantes como en el caso de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="0d367-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="0d367-114">En los países donde no hay ninguna base de datos relevante para CNAM, las prácticas de operadores individuales también pueden causar problemas con la información CNAM que llega intacta con la llamada.</span><span class="sxs-lookup"><span data-stu-id="0d367-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="0d367-115">Actualmente, Microsoft no admite información CNAM originada en países que no son Estados Unidos".</span><span class="sxs-lookup"><span data-stu-id="0d367-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="0d367-116">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0d367-116">Related topics</span></span>


