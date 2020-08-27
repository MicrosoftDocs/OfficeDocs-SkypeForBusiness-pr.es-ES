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
description: Obtenga información sobre por qué necesita agregar una persona autorizada que pueda realizar cambios en la cuenta cuando use el Asistente para la solicitud de portabilidad de nuevo número local.
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255403"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="993a5-103">Más información sobre Identificadores de línea de la llamada entrante y nombres para mostrar a la persona que llama</span><span class="sxs-lookup"><span data-stu-id="993a5-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="993a5-104">CallerID, como se hace normalmente, consta de dos partes de información identificables por el usuario:</span><span class="sxs-lookup"><span data-stu-id="993a5-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="993a5-105">Un número de teléfono (generalmente denominado CLID o identificador de línea de llamada)</span><span class="sxs-lookup"><span data-stu-id="993a5-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="993a5-106">Nombre de la persona que llama (normalmente se denomina CNAM), que puede tener hasta 15 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="993a5-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="993a5-107">Cuando se realiza una llamada, la CLID (número de teléfono) se enruta al operador de telefonía del destinatario (también conocido como portador final).</span><span class="sxs-lookup"><span data-stu-id="993a5-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="993a5-108">La información de CNAM de la llamada puede enrutarse con la llamada, ya que depende de la forma en que el país haya implementado CNAM (si es que es necesario).</span><span class="sxs-lookup"><span data-stu-id="993a5-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="993a5-109">La fiabilidad de la entrega de CNAM con la llamada varía según el país y los operadores que administran la llamada, ya sea como un intermediario o un portador de terminación.</span><span class="sxs-lookup"><span data-stu-id="993a5-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="993a5-110">La transmisión de CLID & CNAM es responsabilidad del portador de terminación en la medida en que el portador de terminación debe ser compatible con la funcionalidad de & y también ofrece registros actualizados para ambos valores.</span><span class="sxs-lookup"><span data-stu-id="993a5-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="993a5-111">Microsoft proporciona de manera confiable valores de CLID durante las llamadas de origen, pero es posible que esos valores no se mantengan intactos una vez que pasen por un operador intermediario o el portador de terminación.</span><span class="sxs-lookup"><span data-stu-id="993a5-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="993a5-112">Lamentablemente, en el caso de que el valor de la CLID se cambie, se omita o se elimine o se trunque por parte del transportista o de la terminación, Microsoft tiene poco que recurrir al problema de la red telefónica pública.</span><span class="sxs-lookup"><span data-stu-id="993a5-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="993a5-113">Las incoherencias en CNAM pueden estar causadas por retrasos en las transportadoras intermedias o de terminación que actualizan CNAM información de las bases de datos autorizadas, como en el caso de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="993a5-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="993a5-114">En los países en los que no hay una base de datos autoritaria para CNAM, las prácticas de los operadores individuales también pueden causar problemas con la información de CNAM que llega intacta con la llamada.</span><span class="sxs-lookup"><span data-stu-id="993a5-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="993a5-115">Actualmente, Microsoft no admite la información de CNAM de origen en países que no sean de Estados Unidos. "</span><span class="sxs-lookup"><span data-stu-id="993a5-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="993a5-116">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="993a5-116">Related topics</span></span>


