---
title: Seleccionar reglas de conversión
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: Enterprise Voice requiere que todas las cadenas de marcado puede normalizar al formato E.164 con el fin de realizar la búsqueda inversa de números (RNL). El tronco (es decir, el tronco SIP, PBX o puerta de enlace asociada) puede requerir que los números estén en un formato de marcado local. Para convertir números con formato E.164 a un formato de marcado local puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.
ms.openlocfilehash: ab2a39442ce41f96769668d19de0694d4a464a4b
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="select-translation-rules"></a><span data-ttu-id="24c96-106">Seleccionar reglas de conversión</span><span class="sxs-lookup"><span data-stu-id="24c96-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="24c96-107">Enterprise Voice requiere que todas las cadenas de marcado puede normalizar al formato E.164 con el fin de realizar la búsqueda inversa de números (RNL).</span><span class="sxs-lookup"><span data-stu-id="24c96-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="24c96-108">El tronco (es decir, el tronco SIP, PBX o puerta de enlace asociada) puede requerir que los números estén en un formato de marcado local.</span><span class="sxs-lookup"><span data-stu-id="24c96-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="24c96-109">Para convertir números con formato E.164 a un formato de marcado local puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco.</span><span class="sxs-lookup"><span data-stu-id="24c96-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="24c96-110">Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.</span><span class="sxs-lookup"><span data-stu-id="24c96-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="24c96-111">La capacidad para asociar una o varias reglas de traducción con una configuración de tronco de Enterprise Voice está pensada para usarse como alternativa a la configuración de reglas de conversión en el mismo nivel de tronco.</span><span class="sxs-lookup"><span data-stu-id="24c96-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="24c96-112">No asocie reglas de conversión con una configuración de tronco de Enterprise Voice si ha configurado reglas de conversión en el mismo nivel de tronco debido a que las dos reglas entran en conflicto.</span><span class="sxs-lookup"><span data-stu-id="24c96-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="24c96-113">Para usar una regla de conversión existente, haga clic en una regla de la lista y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="24c96-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
<span data-ttu-id="24c96-114">Para obtener información detallada sobre los distintos procedimientos que puede realizar mediante el uso de la Skype para el Panel de Control de servidor empresarial, vea [Administrar Skype para Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="24c96-114">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

