---
title: Más información sobre Identificadores de línea de la llamada entrante y nombres para mostrar a la persona que llama
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Obtenga información sobre por qué necesita agregar a una persona autorizada que puede realizar cambios en la cuenta cuando se usa el Asistente para nuevo pedido de puerto número Local.
ms.openlocfilehash: 846abfd5b6973a02ad1a7388b45a79ec709695a0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229871"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="19137-103">Más información sobre Identificadores de línea de la llamada entrante y nombres para mostrar a la persona que llama</span><span class="sxs-lookup"><span data-stu-id="19137-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="19137-104">CallerID, tal y como normalmente se conoce, realmente consta de dos partes de identificación de cara al usuario de la información:</span><span class="sxs-lookup"><span data-stu-id="19137-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="19137-105">Un número de teléfono (normalmente conocido como CLID o llamada de línea Id.)</span><span class="sxs-lookup"><span data-stu-id="19137-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="19137-106">Llamar al nombre del usuario (que normalmente se denomina CNAM) que puede tener hasta 15 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="19137-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="19137-107">Cuando se realiza una llamada, el CLID (número de teléfono) se redirige al operador de destino (también conocido como el operador de terminación).</span><span class="sxs-lookup"><span data-stu-id="19137-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="19137-108">La información de CNAM de la llamada puede o no se pueden enrutar con la llamada como esto depende de cómo ha implementado el país CNAM (si en absoluto).</span><span class="sxs-lookup"><span data-stu-id="19137-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="19137-109">La confiabilidad de entrega CNAM con la llamada varía según el país y operadores que controlan la llamada ya sea como intermediario o un operador de terminación.</span><span class="sxs-lookup"><span data-stu-id="19137-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="19137-110">Transmisión de CLID & CNAM es responsabilidad de la compañía de terminación medida en que el operador de terminación debe admitir CLID & CNAM funcionalidad, así como proporcionar registros actualizados para los dos valores.</span><span class="sxs-lookup"><span data-stu-id="19137-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="19137-111">Microsoft proporciona confiable valores CLID cuando se originan las llamadas, pero esos valores no se mantiene intactas una vez que se pasan a través de un intermediario portadora o el operador de terminación.</span><span class="sxs-lookup"><span data-stu-id="19137-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="19137-112">Desafortunadamente, en caso de que el valor CLID se ha cambiado, se omite o truncado por el operador de intermediario o terminación, Microsoft no tiene poca o ninguna recurrir en la corrección de este tipo de problemas en la red telefónica.</span><span class="sxs-lookup"><span data-stu-id="19137-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="19137-113">Incoherencias en CNAM pueden deberse a los retrasos en el nivel intermedios o terminación operadores actualizar info CNAM en bases de datos relevantes como en el caso de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="19137-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="19137-114">En los países donde no hay ninguna base de datos relevante para CNAM, prácticas de portadora individuales también pueden causar problemas con información CNAM que llega permanecen con la llamada.</span><span class="sxs-lookup"><span data-stu-id="19137-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="19137-115">Microsoft actualmente no admite original información CNAM en países distintos de los Estados Unidos."</span><span class="sxs-lookup"><span data-stu-id="19137-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="19137-116">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="19137-116">Related topics</span></span>


