---
title: Migrar números de acceso telefónico local
TOCTitle: Migrar números de acceso telefónico local
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49889764
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrar números de acceso telefónico local

 

_**Última modificación del tema:** 2012-10-19_

Para migrar números de acceso telefónico de Lync Server 2010 a Lync Server 2013, necesita ejecutar el cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto. Durante el período de coexistencia de Lync Server 2010 y Lync Server 2013, los números de acceso telefónico que creó en Lync Server 2013 se comportan igual que los números de acceso telefónico que crea en Lync Server 2010, tal como se describe en esta sección.

Los números de acceso telefónico que creó en Lync Server 2010 pero movió a Lync Server 2013 o que creó en Lync Server 2013 anteriormente, tienen las características siguientes durante o después de la migración:

  - No aparecen en las invitaciones a reuniones de Office Communications Server 2007 R2, ni en la página del número de acceso telefónico.

  - Aparecen en las invitaciones a reuniones de Lync Server 2010 y en la página del número de acceso telefónico.

  - Aparecen en las invitaciones a reuniones de Lync Server 2013 y en la página del número de acceso telefónico.

  - No se pueden ver ni modificar en la herramienta administrativa de Office Communications Server 2007 R2.

  - Se pueden ver y modificar en el panel de control de Lync Server 2010 y en el shell de administración de Lync Server 2010.

  - Se pueden ver y modificar en el panel de control de Lync Server 2013 y en el shell de administración de Lync Server 2013.

  - Se pueden volver a secuenciar en la región con el cmdlet Set-CsDialinConferencingAccessNumber con el parámetro Priority.

Finalice la migración de los números de acceso telefónico que apuntan a un grupo de servidores de Lync Server 2010, para dar de baja el grupo de servidores de Lync Server 2010. Si no finaliza la migración tal como se describe en el procedimiento siguiente, las llamadas entrantes a los números de acceso serán erróneas.

> [!IMPORTANT]  
> Ejecute este procedimiento antes de retirar el grupo de servidores de Lync Server 2010.




> [!NOTE]
> Le recomendamos que mueva los números de acceso telefónico cuando el uso de la red sea bajo, en caso de que se produzca una breve interrupción del servicio.



**Para identificar y mover números de acceso telefónico**

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Para mover cada número de acceso telefónico a un grupo hospedado en Lync Server 2013, en la línea de comandos ejecute lo siguiente:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Abra Panel de control de Lync Server.

4.  En la barra de navegación izquierda, haga clic en **Conferencia**.

5.  Haga clic en la pestaña **Número de acceso telefónico**.

6.  Compruebe que no quede ningún número de acceso telefónico para el grupo de servidores de Lync Server 2010 desde el que realiza la migración.
    

    > [!NOTE]
    > Cuando todos los números de acceso telefónico apunten al grupo de servidores de Lync Server 2013, dé de baja el grupo de servidores de Lync Server 2010.



**Comprobar la migración del número de acceso telefónico con el panel de control de Lync Server**

1.  Desde una cuenta de usuario asignada al rol **CsUserAdministrator** o al rol **CsAdministrator**, inicie sesión en cualquier PC de su implementación interna.

2.  Abra Panel de control de Lync Server.

3.  Enn la barra de navegación izquierda, haga clic en **Conferencia**.

4.  Haga clic en la pestaña **Número de acceso telefónico**.

5.  Compruebe que todos los números de acceso telefónico hayan migrado al grupo de servidores hospedado en Lync Server 2013.

**Comprobar la migración del número de acceso telefónico con el shell de administración de Lync Server**

1.  Abra Shell de administración de Lync Server.

2.  Para devolver todos los números de acceso de conferencias de acceso telefónico migrados, en la línea de comandos ejecute:
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Compruebe que todos los números de acceso telefónico hayan migrado al grupo de servidores hospedado en Lync Server 2013.

