---
title: 'Lync Server 2013: comprobar reglas de normalización para el estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dda9fe8d3e0ca9ebc4dec96a8e878fe36576fd41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>Comprobar reglas de normalización para el estacionamiento de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-11_

Las órbitas de estacionamiento de llamadas no deben normalizarse. Compruebe los planes de marcado para asegurarse de que los números de órbita no se normalizan. Si debe crear una regla de normalización adicional para evitar que las órbitas se normalizan, siga el procedimiento descrito en [Create a Dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) para definir una nueva regla de normalización, de modo que el **patrón para la coincidencia** identifique el intervalo de órbita y el **patrón de traducción** sea **$1**. Por ejemplo, si el intervalo de órbita de estacionamiento de llamadas es de 7000 – 7999, el **patrón de coincidencia** es **\\^ (7 d{3}) $** y el modelo de **conversión** es **$1**.

<div>


> [!IMPORTANT]  
> Asegúrese de que la regla de normalización predeterminada en los planes de marcado no contenga <STRONG>^ (\d *)</STRONG>. De lo contrario, la regla de normalización del estacionamiento de llamadas nunca se ejecutará.



</div>

<div>

## <a name="see-also"></a>Vea también


[Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

