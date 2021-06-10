---
title: Más información sobre Identificadores de línea de la llamada entrante y nombres para mostrar a la persona que llama
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: Obtenga información sobre el identificador de línea de llamadas y el nombre de la parte de llamadas.
ms.openlocfilehash: dd68327c8fb3f63bf17e0736f9d41b727efc1ff8
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308319"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="5a6f1-103">Más información sobre Identificadores de línea de la llamada entrante y nombres para mostrar a la persona que llama</span><span class="sxs-lookup"><span data-stu-id="5a6f1-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="5a6f1-104">CallerID consta de dos partes de información orientadas al usuario:</span><span class="sxs-lookup"><span data-stu-id="5a6f1-104">CallerID consists of two user-facing pieces of information:</span></span>

- <span data-ttu-id="5a6f1-105">Un número de teléfono (normalmente conocido como CLID o id. de línea de llamada).</span><span class="sxs-lookup"><span data-stu-id="5a6f1-105">A phone number (typically referred to as CLID or calling line ID).</span></span>

- <span data-ttu-id="5a6f1-106">Nombre del usuario que llama (normalmente denominado CNAM).</span><span class="sxs-lookup"><span data-stu-id="5a6f1-106">Calling party name (typically referred to as CNAM).</span></span> 

<span data-ttu-id="5a6f1-107">Cuando se realiza una llamada, el CLID (número de teléfono) se enruta al operador del destino (también conocido como el operador de finalización).</span><span class="sxs-lookup"><span data-stu-id="5a6f1-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="5a6f1-108">La información de CNAM para la llamada puede o no enrutada con la llamada, ya que esta información depende de cómo el país haya implementado CNAM (si es que lo hace).</span><span class="sxs-lookup"><span data-stu-id="5a6f1-108">The CNAM information for the call may or may not be routed with the call because as this information depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="5a6f1-109">La confiabilidad de la entrega CNAM con la llamada varía según el país y los transportistas que se encargan de la llamada, ya sea como intermediario o como transportista de finalización.</span><span class="sxs-lookup"><span data-stu-id="5a6f1-109">The reliability of CNAM delivery with the call varies depending on the country and carriers that handle the call--either as an intermediary or a terminating carrier.</span></span> 

<span data-ttu-id="5a6f1-110">Clid & transmisión CNAM es la responsabilidad del operador de terminación.</span><span class="sxs-lookup"><span data-stu-id="5a6f1-110">CLID & CNAM transmission is the responsibility of the terminating carrier.</span></span> <span data-ttu-id="5a6f1-111">El operador de terminación debe admitir & funcionalidad CNAM, así como proporcionar registros actualizados para ambos valores.</span><span class="sxs-lookup"><span data-stu-id="5a6f1-111">The terminating carrier must support CLID & CNAM functionality as well as provide up-to-date records for both values.</span></span> <span data-ttu-id="5a6f1-112">Microsoft proporciona de forma fiable valores CLID al originar llamadas, pero es posible que esos valores no se conservarán intactos una vez que pasen por un operador intermedio o el operador de terminación.</span><span class="sxs-lookup"><span data-stu-id="5a6f1-112">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="5a6f1-113">Si el operador intermedio o de terminación cambia, omite o trunca el valor CLID, Microsoft tiene poco o ningún recurso para corregir estos problemas en la red telefónica pública.</span><span class="sxs-lookup"><span data-stu-id="5a6f1-113">If the CLID value is changed, omitted, or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="5a6f1-114">Las incoherencias en CNAM pueden deberse a que los operadores intermedios o finales retrasan la actualización de la información de CNAM en bases de datos autoritarios, como en el caso de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="5a6f1-114">Inconsistencies in CNAM can be caused when the intermediate or terminating carriers delay refreshing the CNAM information in authoritative databases--as in the case of the United States.</span></span> <span data-ttu-id="5a6f1-115">En los países donde no hay bases de datos autoritarias para CNAM, las prácticas de operadores individuales también pueden causar problemas con la información de CNAM que llega intacta con la llamada.</span><span class="sxs-lookup"><span data-stu-id="5a6f1-115">In countries where there are no authoritative databases for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="5a6f1-116">Actualmente, Microsoft no admite la información CNAM de origen en países distintos de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="5a6f1-116">Microsoft currently does not support originating CNAM information in countries other than the United States.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5a6f1-117">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5a6f1-117">Related topics</span></span>


