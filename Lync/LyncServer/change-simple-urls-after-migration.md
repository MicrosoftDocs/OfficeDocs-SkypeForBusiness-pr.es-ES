---
title: Cambiar las direcciones URL simples tras la migración
description: Cambiar direcciones URL sencillas después de la migración.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f9974106d28bcfdc64c2255337baf721a937e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545766"
---
# <a name="change-simple-urls-after-migration"></a>Cambiar las direcciones URL simples tras la migración

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-22_

Lync Server admite tres direcciones URL sencillas:

  - **Reunión** sirve como dirección URL base de todas las conferencias del sitio o la organización. Con una dirección URL simple de reunión, los vínculos para unirse a reuniones son fáciles de identificar, comunicar y distribuir.

  - **Acceso telefónico** permite el acceso a la página web Configuración de conferencia de acceso telefónico local. La dirección URL simple de acceso telefónico aparece en todas las invitaciones a reuniones para que los usuarios que marquen para unirse a la reunión puedan tener acceso al número de teléfono e información de PIN necesarios.

  - El **Administrador** habilita el acceso rápido al panel de control de Lync Server. La dirección URL simple de administración es de uso interno para la organización.

Después de migrar a Lync Server 2013, debe tener en cuenta cómo afecta el cambio a los registros DNS y certificados para las direcciones URL sencillas. Si el director de Lync Server 2010 heredado permanece en uso en la topología, no es necesario realizar cambios en las direcciones URL simples. Si se quita el director de Lync Server 2010 de la topología después de la migración, los registros DNS de direcciones URL simples deben actualizarse para que apunten a uno de los grupos de servidores de Lync Server 2013. Sin embargo, cuando modifique el nombre de una dirección URL simple, deberá ejecutar Enable-CsComputer en cada director y servidor front-end para registrar el cambio.

<div>

## <a name="changing-simple-urls-after-migration"></a>Cambiar las direcciones URL simples tras la migración

**Para actualizar las direcciones URL simples de reunión**

1.  En el generador de topologías, haga clic con el botón secundario en el nodo superior **Lync Server**y, a continuación, haga clic en **Editar propiedades**.

2.  Seleccione **direcciones URL simples** en el panel izquierdo y, a continuación, debajo de direcciones URL de **reunión:** seleccione la dirección URL de reunirse y haga clic en **Editar dirección URL**.

3.  Actualice la dirección URL al valor deseado y haga clic en **Aceptar** para guardar la dirección URL modificada.

**Para actualizar las direcciones URL simples de administración**

1.  En el generador de topologías, haga clic con el botón secundario en el nodo superior **Lync Server**y, a continuación, haga clic en **Editar propiedades**.

2.  Seleccione **direcciones URL simples** en el panel izquierdo y, a continuación, en el cuadro **dirección URL de acceso administrativo** , escriba la dirección URL sencilla que desee para el acceso administrativo al panel de Control de Lync Server 2013 y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!TIP]  
    > Recomendamos usar la dirección URL más simple posible para la dirección URL de administración. La opción más sencilla es <STRONG> https://admin .</STRONG> &lt; dominio &gt; .

    
    </div>

</div>

<div>

## <a name="see-also"></a>Consulte también


[Planeación de direcciones URL sencillas en Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

