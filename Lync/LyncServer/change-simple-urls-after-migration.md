---
title: Cambiar las direcciones URL simples tras la migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: a24eda274734e0c5a27fab30640a363de6653514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>Cambiar las direcciones URL simples tras la migración

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-22_

Lync Server admite tres direcciones URL simples:

  - **Reunirse** se usa como la dirección URL base para todas las conferencias del sitio o la organización. Con la dirección URL simple, los vínculos a las reuniones de unirse son fáciles de comprender y se pueden comunicar y distribuir fácilmente.

  - El acceso **telefónico** permite el acceso a la Página Web de configuración de conferencias de acceso telefónico local. La dirección URL de acceso telefónico simple está incluida en todas las invitaciones a reuniones para que los usuarios que deseen llamar a la reunión puedan tener acceso a la información del número de teléfono y del PIN necesarios.

  - El **Administrador** permite acceder rápidamente al panel de control de Lync Server. La dirección URL simple de administración es interna de su organización.

Después de migrar a Lync Server 2013, debe tener en cuenta cómo afecta el cambio a los registros DNS y los certificados para las direcciones URL simples. Si el director de Lync Server 2010 heredado permanece en uso en la topología, no es necesario realizar cambios en las direcciones URL simples. Si se quita Lync Server 2010 Director de la topología después de la migración, los registros DNS de direcciones URL simples deben actualizarse para que apunten a uno de los grupos de servidores de Lync Server 2013. Sin embargo, cada vez que cambie un nombre de dirección URL simple, debe ejecutar enable-CsComputer en cada director y en el servidor front-end para registrar el cambio.

<div>

## <a name="changing-simple-urls-after-migration"></a>Cambiar las URL simples después de la migración

**Para actualizar la dirección URL simple de reunirse**

1.  En el generador de topología, haga clic con el botón secundario en el nodo superior de **Lync Server**y, a continuación, haga clic en **Editar propiedades**.

2.  Seleccione **URL simples** en el panel izquierdo y, a continuación, debajo de **direcciones URL de reunión:** seleccione la dirección URL de la reunión y haga clic en **Editar URL**.

3.  Actualice la dirección URL con el valor que quiera y haga clic en **Aceptar** para guardar la dirección URL modificada.

**Para actualizar la dirección URL simple de administración**

1.  En el generador de topología, haga clic con el botón secundario en el nodo superior de **Lync Server**y, a continuación, haga clic en **Editar propiedades**.

2.  Seleccione **URL simples** en el panel izquierdo y, a continuación, haga clic en **dirección URL de acceso administrativo** , escriba la dirección URL simple que desee para el acceso administrativo al panel de Control de Lync Server 2013 y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!TIP]  
    > Recomendamos usar la dirección URL más simple posible como dirección URL sencilla de administración. La opción más sencilla es <STRONG> https://admin.</STRONG> &lt;dominio&gt;.

    
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

