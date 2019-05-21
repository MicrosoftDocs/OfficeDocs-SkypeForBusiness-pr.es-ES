---
title: Seleccionar reglas de conversión
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: La telefonía IP empresarial requiere normalizar todas las cadenas de marcado al formato E. 164 con el fin de realizar la búsqueda de números inversos (RNL). El tronco (es decir, el tronco SIP, PBX o puerta de enlace asociada) puede requerir que los números estén en un formato de marcado local. Para convertir números con formato E.164 a un formato de marcado local puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.
ms.openlocfilehash: e6df4b2eed01849af7290596bc0e91896e527574
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290720"
---
# <a name="select-translation-rules"></a><span data-ttu-id="d5150-106">Seleccionar reglas de conversión</span><span class="sxs-lookup"><span data-stu-id="d5150-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="d5150-107">La telefonía IP empresarial requiere normalizar todas las cadenas de marcado al formato E. 164 con el fin de realizar la búsqueda de números inversos (RNL).</span><span class="sxs-lookup"><span data-stu-id="d5150-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="d5150-108">El tronco (es decir, el tronco SIP, PBX o puerta de enlace asociada) puede requerir que los números estén en un formato de marcado local.</span><span class="sxs-lookup"><span data-stu-id="d5150-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="d5150-109">Para convertir números con formato E.164 a un formato de marcado local puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco.</span><span class="sxs-lookup"><span data-stu-id="d5150-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="d5150-110">Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.</span><span class="sxs-lookup"><span data-stu-id="d5150-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d5150-111">La capacidad de asociar una o más reglas de traducción con una configuración de telefonía IP empresarial está pensada para su uso como alternativa a la configuración de reglas de traducción en el punto de conexión del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="d5150-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="d5150-112">No asociar reglas de traducción con una configuración de telefonía IP empresarial si ha configurado reglas de traducción en el punto de conexión del mismo nivel porque las dos reglas podrían entrar en conflicto.</span><span class="sxs-lookup"><span data-stu-id="d5150-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="d5150-113">Para usar una regla de conversión existente, haga clic en una regla de la lista y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d5150-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
 
  

