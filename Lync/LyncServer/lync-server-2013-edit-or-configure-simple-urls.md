---
title: 'Lync Server 2013: editar o configurar direcciones URL sencillas'
description: 'Lync Server 2013: editar o configurar direcciones URL sencillas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9152a65083f71510f4cdb1189b3982afdd68b4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551636"
---
# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>Editar o configurar direcciones URL sencillas en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-04_

Este procedimiento no requiere pertenencia al grupo de dominio con privilegios o de administrador local. Deberá iniciar sesión en un equipo como usuario estándar.

Lync Server 2013 usa direcciones URL sencillas para dirigir llamadas internas y externas a los servicios del servidor front-end o del Director, si se ha implementado una. Para obtener más información acerca de las direcciones URL sencillas, consulte [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) en la documentación referente a la planeación. Puede seleccionar el formato de las direcciones URL sencillas desde varias opciones. Para obtener más información sobre estas opciones, consulte [DNS Requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) en la documentación referente a la planeación.

De forma predeterminada, las direcciones URL sencillas se configurarán en forma de (por ejemplo, la dirección URL sencilla de acceso telefónico): https://dialin .\<SIP Domain\>

<div>

## <a name="to-configure-simple-urls"></a>Para configurar direcciones URL sencillas

1.  En el generador de topologías, haga clic con el botón secundario en el nodo **Lync Server** y luego haga clic en **Editar propiedades**.

2.  En el panel **direcciones URL simples** , seleccione **direcciones URL de acceso telefónico:** (acceso telefónico) o **direcciones URL de reunión:** (reunirse) para editar y, a continuación, haga clic en **Editar dirección URL**.

3.  Actualice la dirección URL al valor deseado y haga clic en **Aceptar** para guardar la dirección URL modificada. El ejemplo que se muestra aquí ha modificado la dirección URL de acceso telefónico a https://pool01.contoso.net/dialin .

4.  Edite la dirección URL de reunión realizando los mismos pasos, si es necesario.

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>Para definir la dirección URL sencilla de administración opcional

1.  En el generador de topologías, haga clic con el botón secundario en el nodo **Lync Server** y luego haga clic en **Editar propiedades**.

2.  En el cuadro **dirección URL de acceso administrativo** , escriba la dirección URL sencilla que desee para el acceso administrativo al panel de control de Lync Server 2013 y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!TIP]  
    > Recomendamos usar la dirección URL más simple posible para la dirección URL de administración. La opción más sencilla es <STRONG> https://admin .</STRONG> &lt; dominio &gt; .

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Si cambia una dirección URL sencilla tras la implementación inicial, deberá conocer qué cambios afectan a los certificados y los registros de su sistema de nombres de dominio (DNS) para direcciones de URL sencillas. Si el cambio afecta a la base de una dirección URL sencilla, deberá modificar también los certificados y registros DNS. Por ejemplo, si se cambia de https://lync.contoso.com/Meet para https://meet.contoso.com cambia la dirección URL base de lync.contoso.com a meet.contoso.com, es necesario cambiar los registros DNS y los certificados para hacer referencia a meet.contoso.com. Si ha cambiado la dirección URL sencilla de https://lync.contoso.com/Meet a https://lync.contoso.com/Meetings , la dirección URL base de Lync.contoso.com permanece igual, por lo que no es necesario ningún cambio de certificado o DNS. Sin embargo, cada vez que cambie un nombre de dirección URL simple, debe ejecutar el cmdlet <STRONG>enable-CsComputer</STRONG> en cada director y en el servidor front-end para registrar el cambio.

    
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

