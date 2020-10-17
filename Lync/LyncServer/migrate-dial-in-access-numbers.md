---
title: Migrar los números de acceso telefónico
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6401d847c2e0993632ad655fb43f07b0a2731ef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503557"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrar los números de acceso telefónico

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

La migración de números de acceso telefónico local de Lync Server 2010 a Lync Server 2013 requiere la ejecución del cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto. Durante el período de coexistencia de Lync Server 2010 y Lync Server 2013, los números de acceso telefónico que ha creado en Lync Server 2013 se comportan de forma similar a los números de acceso telefónico que crea en Lync Server 2010, tal como se describe en esta sección.

Los números de acceso telefónico que ha creado en Lync Server 2010, pero que se han movido a Lync Server 2013 o que ha creado en Lync Server 2013 antes, durante o después de la migración tienen las siguientes características:

  - No aparecen en las invitaciones a reuniones de Office Communications Server 2007 R2, ni en la página del número de acceso telefónico.

  - Aparecen en las invitaciones a reuniones de Lync Server 2010 y en la página del número de acceso telefónico.

  - Aparecen en las invitaciones a reuniones de Lync Server 2013 y en la página del número de acceso telefónico.

  - No se pueden ver ni modificar en la herramienta administrativa de Office Communications Server 2007 R2.

  - Se pueden ver y modificar en el panel de control de Lync Server 2010 y en el shell de administración de Lync Server 2010.

  - Se pueden ver y modificar en el panel de control de Lync Server 2013 y en el shell de administración de Lync Server 2013.

  - Se pueden volver a secuenciar en la región con el cmdlet Set-CsDialinConferencingAccessNumber con el parámetro Priority.

Finalice la migración de los números de acceso telefónico que apuntan a un grupo de servidores de Lync Server 2010, para dar de baja el grupo de servidores de Lync Server 2010. Si no finaliza la migración tal como se describe en el procedimiento siguiente, las llamadas entrantes a los números de acceso serán erróneas.

<div>


> [!IMPORTANT]  
> Debe realizar este procedimiento antes de retirar el grupo de servidores de Lync Server 2010.



</div>

<div>


> [!NOTE]  
> Se recomienda que mueva los números de acceso telefónico cuando el uso de la red sea bajo, en caso de que se produzca una breve interrupción del servicio.



</div>

**Para identificar y mover números de acceso telefónico**

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

2.  Para mover cada número de acceso telefónico a un grupo hospedado en Lync Server 2013, en la línea de comandos, ejecute:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Abra Panel de control de Lync Server

4.  En la barra de navegación izquierda, haga clic en **Conferencia**.

5.  Haga clic en la pestaña **Número de acceso telefónico**.

6.  Compruebe que no quedan números de acceso telefónico para el grupo de servidores de Lync 2010 desde el que está migrando.
    
    <div>
    

    > [!NOTE]  
    > Cuando todos los números de acceso telefónico local señalan al grupo de servidores de Lync Server 2013, puede retirar el grupo de servidores de Lync Server 2010.

    
    </div>

**Comprobar la migración del número de acceso telefónico con el panel de control de Lync Server**

1.  Desde una cuenta de usuario asignada al rol **CsUserAdministrator** o al rol **CsAdministrator**, inicie sesión en cualquier PC de su implementación interna.

2.  Abra Panel de control de Lync Server

3.  En la barra de navegación izquierda, haga clic en **Conferencia**.

4.  Haga clic en la pestaña **Número de acceso telefónico**.

5.  Compruebe que todo el número de acceso telefónico local se ha migrado al grupo hospedado en Lync Server 2013.

**Comprobar la migración del número de acceso telefónico con el shell de administración de Lync Server**

1.  Abra el shell de administración de Lync Server.

2.  Para devolver todos los números de acceso de conferencias de acceso telefónico migrados, en la línea de comandos ejecute:
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Compruebe que todos los números de acceso telefónico local se migren al grupo hospedado en Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

