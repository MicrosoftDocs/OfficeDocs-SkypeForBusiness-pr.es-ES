---
title: Tipo de regla de conversión una expresión regular
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: En el campo Hacer coincidir este patrón, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión. En el campo Regla de conversión, especifique un patrón para el formato de los números convertidos. Por ejemplo, si escribe ^ (\d \d+)$ en el campo Coincidir este patrón y 011$1 en el campo de regla de conversión, la regla traducirá \+ {9} +441235551010 a 011441235551010.
ms.openlocfilehash: badbc5a34325e6bc2b5bef7e67ae39a4c8f02dc7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818860"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="40906-105">Regla de conversión: Escribir una expresión regular</span><span class="sxs-lookup"><span data-stu-id="40906-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="40906-106">En el campo **Hacer coincidir este patrón**, especifique el patrón que se usará para hacer coincidir los números objeto de la conversión.</span><span class="sxs-lookup"><span data-stu-id="40906-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="40906-107">En el campo **Regla de conversión**, especifique un patrón para el formato de los números convertidos.</span><span class="sxs-lookup"><span data-stu-id="40906-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="40906-108">Por ejemplo, si escribe ^ (\d \d+)$ en el campo Coincidir este patrón y 011$1 en el campo de regla de conversión, la regla traducirá \+ {9} +441235551010 a 011441235551010.  </span><span class="sxs-lookup"><span data-stu-id="40906-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="40906-109">Para obtener más información sobre los distintos procedimientos que puede realizar con el Panel de control de Skype Empresarial Server, consulte Administrar Skype Empresarial [Server 2015.](../../manage/manage.md)</span><span class="sxs-lookup"><span data-stu-id="40906-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

