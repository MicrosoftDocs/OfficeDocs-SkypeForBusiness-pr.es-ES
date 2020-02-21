---
title: 'Lync Server 2013: configurar la tabla de órbitas de estacionamiento de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce2919e783b24148cd6526a1b4ecfbf082c11985
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>Configurar la tabla de órbitas de estacionamiento de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-10_

El estacionamiento de llamadas usa órbitas para las llamadas de estacionamiento. Antes de que los usuarios puedan estacionar y recuperar llamadas, debe configurar la tabla de órbitas de estacionamiento de llamadas. Debe especificar los intervalos de números de extensión (órbitas) que la organización reservará para las llamadas de estacionamiento y definir la distribución para los intervalos especificando qué grupo de estacionamiento de llamadas administra cada intervalo. A la hora de definir intervalos de órbitas, el objetivo es tener una cantidad suficiente de órbitas, de modo que ninguna de las órbitas vuelva a usarse en seguida, pero tampoco se deben tener demasiadas órbitas porque esto limitaría el número de extensiones disponibles para los usuarios u otros servicios. Puede crear varios intervalos de órbitas de estacionamiento de llamadas para cada grupo de Lync Server en el que se implemente la aplicación de estacionamiento de llamadas. Cada intervalo de órbitas de estacionamiento de llamadas debe tener un nombre único global y un conjunto único de extensiones.

<div>


> [!IMPORTANT]  
> Un intervalo de órbitas suele estar formado por 100 órbitas o menos, pero puede ser mucho mayor, siempre que tenga menos de 10.000 órbitas (número máximo) por intervalo y que usted tenga menos de 50.000 órbitas por grupo de servidores. Si un intervalo es demasiado pequeño, las órbitas se volverán a usar con mayor rapidez.



</div>

Use bloques de extensiones virtuales (extensiones que no tengan asignado ningún usuario ni teléfono) para los intervalos de órbitas.

<div>


> [!NOTE]  
> No se admite la asignación de números de llamada directa (DID) como números de órbita en la tabla de órbitas de estacionamiento de llamadas.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

[Crear o modificar un intervalo de órbitas de estacionamiento de llamadas en Lync Server 2013](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

