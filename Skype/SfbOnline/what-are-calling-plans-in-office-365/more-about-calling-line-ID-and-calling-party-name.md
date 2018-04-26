---
title: Más información sobre identificador de línea llama y llamar a nombre de entidad
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Obtenga información acerca de por qué necesita agregar a una persona autorizada que puede realizar cambios en la cuenta cuando se utiliza el Asistente para nuevo pedido de puerto número Local.
ms.openlocfilehash: 1174ba5837bb91c3251232ab48fa63c343425ac1
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="28828-103">Más información sobre identificador de línea llama y llamar a nombre de entidad</span><span class="sxs-lookup"><span data-stu-id="28828-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="28828-104">CallerID, como normalmente se conoce, consta realmente de dos partes identificables de cara al usuario de información:</span><span class="sxs-lookup"><span data-stu-id="28828-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="28828-105">Un número de teléfono (normalmente conocido como CLID o llamar a la línea Id.)</span><span class="sxs-lookup"><span data-stu-id="28828-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="28828-106">Nombre del fabricante (normalmente denominado CNAM) que puede tener hasta 15 caracteres de longitud que llama.</span><span class="sxs-lookup"><span data-stu-id="28828-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="28828-107">Cuando se realiza una llamada, el CLID (número de teléfono) se enruta al portador del destino (también conocido como el portador de terminación).</span><span class="sxs-lookup"><span data-stu-id="28828-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="28828-108">La información de CNAM de la llamada puede o no se pueden enrutar a la llamada como esto depende de cómo el país ha implementado CNAM (si).</span><span class="sxs-lookup"><span data-stu-id="28828-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="28828-109">La confiabilidad de entrega CNAM con la llamada varía dependiendo del país y los transportistas que controlan la llamada como un intermediario o una compañía de terminación.</span><span class="sxs-lookup"><span data-stu-id="28828-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="28828-110">Transmisión CLID & CNAM es responsabilidad terminación del portador de la medida en que el transportista terminación debe admitir funcionalidad CLID & CNAM así como proporcionar registros actualizados para ambos valores.</span><span class="sxs-lookup"><span data-stu-id="28828-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="28828-111">Microsoft proporciona confiablemente valores CLID cuando origina llamadas, pero dichos valores no se mantiene intactos cuando pasan a través de un intermediario portador o la portadora de terminación.</span><span class="sxs-lookup"><span data-stu-id="28828-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="28828-112">Por desgracia, en caso de que el valor CLID se cambia, se omite o truncado por el transportista intermediario o terminación, Microsoft no tiene poco a ningún recurso en la corrección de este tipo de problemas en la red telefónica pública.</span><span class="sxs-lookup"><span data-stu-id="28828-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="28828-113">Incoherencias en el CNAM pueden deberse a retrasos en la terminación o intermedios portadores actualizar info CNAM en bases de datos autorizados como en el caso de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="28828-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="28828-114">En los países donde no existe ninguna base de datos autorizado para CNAM, prácticas de portadora individuales también pueden causar problemas con información CNAM que lleguen intactos a la llamada.</span><span class="sxs-lookup"><span data-stu-id="28828-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="28828-115">Microsoft actualmente no admite información de origen CNAM en países distintos de EE."</span><span class="sxs-lookup"><span data-stu-id="28828-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="28828-116">See also</span><span class="sxs-lookup"><span data-stu-id="28828-116">Related topics</span></span>


