---
title: Cambiar las direcciones URL simples tras la migración
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
ms.openlocfilehash: 2c9f46944e80c5eb7a2d81de6f164d19aab64d29
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>Cambiar las direcciones URL simples tras la migración

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-22_

Lync Server admite tres direcciones URL sencillas:

  - **Meet** is used as the base URL for all conferences in the site or organization. With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.

  - **Dial-in** enables access to the Dial-in Conferencing Settings webpage. The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.

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

## <a name="see-also"></a>Vea también


[Planeación de direcciones URL sencillas en Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

