---
title: Migrar los números de acceso telefónico
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f0f286450aeaaf747d4642bf8791695d16b603
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>Migrar los números de acceso telefónico

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

La migración de números de acceso telefónico local de Lync Server 2010 a Lync Server 2013 requiere que se ejecute el cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto. Durante el período de coexistencia de Lync Server 2010 y Lync Server 2013, los números de acceso telefónico local creados en Lync Server 2013 se comportan de forma similar a los números de acceso telefónico local que se crean en Lync Server 2010, tal y como se describe en esta sección.

Los números de acceso telefónico local que ha creado en Lync Server 2010, pero que se han movido a Lync Server 2013 o que ha creado en Lync Server 2013 antes, durante o después de la migración tienen las siguientes características:

  - No aparecen en las invitaciones a reuniones de Office Communications Server 2007 R2 y la página de número de acceso telefónico local.

  - Aparece en las invitaciones a reuniones de Lync Server 2010 y la página de número de acceso telefónico local.

  - Aparece en las invitaciones a reuniones de Lync Server 2013 y la página de número de acceso telefónico local.

  - No se puede ver ni modificar en la herramienta administrativa de Office Communications Server 2007 R2.

  - Se puede ver y modificar en el panel de control de Lync Server 2010 y en el shell de administración de Lync Server 2010.

  - Se puede ver y modificar en el panel de control de Lync Server 2013 y en el shell de administración de Lync Server 2013.

  - Se puede volver a secuenciar dentro de la región mediante el cmdlet Set-CsDialinConferencingAccessNumber con el parámetro Priority.

Debe finalizar la migración de los números de acceso telefónico local que apunten a un grupo de 2010 de Lync Server antes de retirar el grupo de Lync Server 2010. Si no completa la migración de números de acceso telefónico, como se describe en el siguiente procedimiento, se producirán errores en las llamadas entrantes a los números de acceso.

<div>


> [!IMPORTANT]  
> Debe realizar este procedimiento antes de dar de baja al grupo de servidores de Lync Server 2010.



</div>

<div>


> [!NOTE]  
> Le recomendamos que mueva los números de acceso telefónico cuando el uso de la red sea bajo, en caso de que haya un breve período de tiempo de servicio.



</div>

**Para identificar y mover los números de acceso telefónico local**

1.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

2.  Para mover cada número de acceso de acceso telefónico local a un grupo alojado en Lync Server 2013, en la línea de comandos ejecute:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Abra el Panel de control de Lync Server.

4.  En la barra de navegación izquierda, haga clic en **Conferencia**.

5.  Haga clic en la pestaña **número de acceso telefónico local** .

6.  Compruebe que no quedan números de acceso telefónico local para el grupo de servidores de Lync Server 2010 desde el que está migrando.
    
    <div>
    

    > [!NOTE]  
    > Cuando todos los números de acceso telefónico local señalan al grupo de servidores de Lync Server 2013, puede retirar el grupo de servidores de Lync Server 2010.

    
    </div>

**Comprobar la migración de números de acceso telefónico local con el panel de control de Lync Server**

1.  Desde una cuenta de usuario que tenga asignada la función **CsUserAdministrator** o el rol **CsAdministrator** , inicie sesión en cualquier equipo de su implementación interna.

2.  Abra el Panel de control de Lync Server.

3.  En la barra de navegación izquierda, haga clic en **Conferencia**.

4.  Haga clic en la pestaña **número de acceso telefónico local** .

5.  Compruebe que todo el número de acceso telefónico local se ha migrado al grupo hospedado en Lync Server 2013.

**Comprobar la migración de números de acceso telefónico local con el shell de administración de Lync Server**

1.  Abra el Shell de administración de Lync Server.

2.  Para devolver todos los números de acceso de la Conferencia de acceso telefónico local migrados, desde la línea de comandos ejecute:
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Compruebe que todos los números de acceso telefónico local se migran al grupo hospedado en Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

