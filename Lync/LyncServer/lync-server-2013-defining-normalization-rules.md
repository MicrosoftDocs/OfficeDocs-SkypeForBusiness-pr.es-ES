---
title: 'Lync Server 2013: Definir las reglas de normalización'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b75883d99d218d711e9d96de7ebfd7d360972a6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a>Definir las reglas de normalización en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-04-22_

Reglas de normalización de Lync Server 2013 usar expresiones regulares de .NET Framework para traducir números de teléfono marcados al formato E. 164; en otras palabras, las reglas de normalización toman el número de teléfono marcado por un usuario y convierten ese número al formato usado internamente por Lync Server. Cada plan de marcado debe tener asignadas una o más reglas de normalización.

Para obtener más información sobre las reglas de normalización, consulte [planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) en la documentación de planeación.

Para obtener más información sobre cómo escribir expresiones regulares, vea "expresiones regulares de .NET Framework [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)" en.

Puede usar cualquiera de los siguientes métodos para definir o editar una regla de normalización:

  - Use la herramienta **crear una regla de normalización** para especificar valores para los dígitos iniciales, la longitud, los dígitos que se van a quitar y los dígitos que se van a agregar y, a continuación, deje que el panel de control de Lync Server genere el patrón correspondiente y la regla de traducción correspondiente.

  - Escriba de forma manual expresiones regulares para definir el patrón de coincidencia y la regla de traducción.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Crear o modificar una regla de normalización mediante la creación de una regla de normalización en Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [Crear o modificar una regla de normalización manualmente en Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md)  
[Modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

