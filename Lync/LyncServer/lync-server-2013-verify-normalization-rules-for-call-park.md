---
title: 'Lync Server 2013: comprobar las reglas de normalización de la llamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 114c7e035d96217f8cf41e88a87ccfd490fe5754
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>Comprobar reglas de normalización del parque de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-11_

Las órbitas del parque de llamadas no deben normalizarse. Revise sus planes de marcado para comprobar que los números de órbita no estén normalizados. Si tiene que crear una regla de normalización adicional para evitar que las órbitas se normalizaran, siga el procedimiento de [crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md) para definir una nueva regla de normalización, de modo que el **patrón para que coincida** identifique el intervalo de órbita y el **patrón de traducción** es **$1**. Por ejemplo, si el intervalo de llamada de estacionamiento orbital es 7000 – 7999, el **patrón de coincidencia** es **^\\({3}7 d) $** y el **patrón de traducción** es **$1**.

<div>


> [!IMPORTANT]  
> Asegúrese de que la regla de normalización predeterminada de sus planes de marcado no contenga <STRONG>^(\d*)</STRONG>. En caso contrario, la regla de normalización del parque de llamadas nunca se ejecutará.



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

