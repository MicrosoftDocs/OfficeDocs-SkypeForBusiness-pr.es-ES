---
title: 'Lync Server 2013: Editar o configurar direcciones URL sencillas'
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
ms.openlocfilehash: 0fe6ae7197e2f47c590384547c34dd4b1db50950
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>Editar o configurar direcciones URL sencillas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-04_

Este procedimiento no requiere la pertenencia a un grupo de dominio de administrador o de privilegios local. Debe iniciar sesión en un equipo como usuario estándar.

Lync Server 2013 usa direcciones URL simples para dirigir llamadas internas y externas a servicios en el servidor front-end o en el director, si se ha implementado una. Para obtener más información acerca de las direcciones URL simples, consulte [planificación de direcciones URL simples en Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) en la documentación de planeación. Puede seleccionar el formato de las direcciones URL simples de varias opciones. Para obtener más información sobre estas opciones, consulte [requisitos de DNS para obtener direcciones URL simples en Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) en la documentación de planeación.

De forma predeterminada, las direcciones URL simples se configurarán con el formato (por ejemplo, la dirección URL de acceso https://dialin.\<SIP telefónico simple): dominio\>

<div>

## <a name="to-configure-simple-urls"></a>Para configurar direcciones URL simples

1.  En el generador de topología, haga clic con el botón secundario en el nodo de **Lync Server** y luego haga clic en **Editar propiedades**.

2.  En el panel **Direcciones URL sencillas**, seleccione **Direcciones URL de acceso telefónico:** (marcado) o **Direcciones URL de reunión:** (reunión) para editarlas. Luego, haga clic en **Editar dirección URL**.

3.  Actualice la dirección URL con el valor que quiera y haga clic en **Aceptar** para guardar la dirección URL modificada. El ejemplo que se muestra aquí ha modificado la dirección URL de https://pool01.contoso.net/dialinacceso telefónico.

4.  Edite la dirección URL de reunión realizando los mismos pasos, si es necesario.

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>Para definir la dirección URL sencilla de administración opcional

1.  En el generador de topología, haga clic con el botón secundario en el nodo de **Lync Server** y luego haga clic en **Editar propiedades**.

2.  En el cuadro **dirección URL de acceso administrativo** , escriba la dirección URL simple que desee para el acceso administrativo al panel de control de Lync Server 2013 y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!TIP]  
    > Recomendamos usar la dirección URL más simple posible como dirección URL sencilla de administración. La opción más sencilla es <STRONG> https://admin.</STRONG> &lt;dominio&gt;.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Si modifica una dirección URL sencilla después de la implementación inicial, necesita saber qué cambios influyen en los certificados y registros del Sistema de nombres de dominio (DNS) relativos a las direcciones URL sencillas. Si el cambio afecta a la base de una dirección URL simple, debe cambiar también los certificados y los registros DNS. Por ejemplo, si cambia https://lync.contoso.com/Meet de https://meet.contoso.com para cambia la dirección URL base de Lync.contoso.com a meet.contoso.com, tendrá que cambiar los registros DNS y los certificados para hacer referencia a meet.contoso.com. Si cambió la dirección URL simple de https://lync.contoso.com/Meet a https://lync.contoso.com/Meetings, la dirección URL base de Lync.contoso.com permanece igual, por lo que no es necesario realizar cambios en el certificado o DNS. Sin embargo, siempre que cambie un nombre de dirección URL simple, debe ejecutar el cmdlet <STRONG>enable-CsComputer</STRONG> en cada director y en el servidor front-end para registrar el cambio.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Planeación de las direcciones URL simples en Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

