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
description: Telefonía IP empresarial requiere que todas las cadenas de marcado se normaliza en formato E.164 con el fin de realizar la búsqueda de número inversa (RNL). El tronco (es decir, el tronco SIP, PBX o puerta de enlace asociada) puede requerir que los números estén en un formato de marcado local. Para convertir números con formato E.164 a un formato de marcado local puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco. Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.
ms.openlocfilehash: ab2a39442ce41f96769668d19de0694d4a464a4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="select-translation-rules"></a><span data-ttu-id="198a0-106">Seleccionar reglas de conversión</span><span class="sxs-lookup"><span data-stu-id="198a0-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="198a0-107">Telefonía IP empresarial requiere que todas las cadenas de marcado se normaliza en formato E.164 con el fin de realizar la búsqueda de número inversa (RNL).</span><span class="sxs-lookup"><span data-stu-id="198a0-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="198a0-108">El tronco (es decir, el tronco SIP, PBX o puerta de enlace asociada) puede requerir que los números estén en un formato de marcado local.</span><span class="sxs-lookup"><span data-stu-id="198a0-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="198a0-109">Para convertir números con formato E.164 a un formato de marcado local puede definir una o más reglas de conversión para manipular el URI de solicitud antes de enrutarlo a la entidad del mismo nivel que el tronco.</span><span class="sxs-lookup"><span data-stu-id="198a0-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="198a0-110">Por ejemplo, puede escribir una regla de conversión para quitar +44 del inicio de la cadena de marcado y sustituirlo por 0144.</span><span class="sxs-lookup"><span data-stu-id="198a0-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="198a0-111">La capacidad de asociar uno o más de las reglas de conversión con la configuración de troncales de Telefonía IP empresarial está pensada para utilizarse como alternativa a la configuración de las reglas de conversión en el mismo nivel de tronco.</span><span class="sxs-lookup"><span data-stu-id="198a0-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="198a0-112">No se asocia las reglas de conversión con la configuración de troncales de Telefonía IP empresarial si ha configurado reglas de traducción en el mismo nivel de tronco porque las dos reglas entran en conflicto.</span><span class="sxs-lookup"><span data-stu-id="198a0-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="198a0-113">Para usar una regla de conversión existente, haga clic en una regla de la lista y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="198a0-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
<span data-ttu-id="198a0-114">Para obtener más información acerca de los distintos procedimientos que se pueden realizar utilizando el Skype para Business Server Control Panel, vea [Administrar Skype para Business Server 2015](../../manage/manage.md).</span><span class="sxs-lookup"><span data-stu-id="198a0-114">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

