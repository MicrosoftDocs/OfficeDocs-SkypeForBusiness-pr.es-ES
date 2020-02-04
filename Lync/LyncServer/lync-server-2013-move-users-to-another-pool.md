---
title: 'Lync Server 2013: mover usuarios a otro grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dffa2e7651e056d9dc14b1e261134783d0fd193
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a>Mover usuarios a otro grupo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2018-02-09_

Puede usar el panel de control de Lync Server para asignar usuarios a un servidor o grupo de servidores específico.

<div>


> [!TIP]  
> El traslado de todos los usuarios existentes de un grupo de origen que ejecute Lync Server 2010 o una versión anterior a un grupo de destino de Lync Server 2013 en un entorno de Active Directory complejo puede ralentizar la replicación de Active Directory. Para evitar esto, puede usar filtros de búsqueda para mover usuarios de grupos que ejecuten Lync Server 2010 o una versión anterior por separado, o bien puede usar el shell de administración de Lync Server para mover usuarios con cmdlets. Además, la funcionalidad de filtro funciona con usuarios de Lync Server 2013.



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Para mover los usuarios seleccionados a otro servidor o grupo de servidores

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios** , escriba todas o la primera parte del nombre para mostrar, el nombre, el apellido, el nombre de cuenta del administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.

5.  En la tabla, seleccione un usuario o usuarios específicos de la lista.

6.  En el menú **acción** , haga clic en **mover los usuarios seleccionados al grupo**.

7.  En **mover usuarios**, seleccione el grupo al que desea mover los usuarios en el **grupo de registrador de destinos**.

8.  Faculta Si el servidor de destino o el grupo de servidores no están disponibles, active la casilla **forzar** .
    
    <div>
    

    > [!Caution]  
    > Si selecciona <STRONG>Force</STRONG>, la cuenta de usuario se mueve, pero los datos de usuario asociados tales conferencias y contactos programados no se mueven.

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Para mover todos los usuarios de un servidor o grupo de servidores a otro servidor o grupo de servidores

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el menú **acción** , haga clic en **mover todos los usuarios al grupo**.

5.  En **mover usuarios**, seleccione el grupo que contiene las cuentas de usuario que desea mover en el **grupo de registrador de origen**.

6.  En **grupo de registradores de destino**, seleccione el grupo al que desea mover a los usuarios.

7.  Faculta Si el servidor de destino o el grupo de servidores no están disponibles, active la casilla **forzar** .
    
    <div>
    

    > [!Caution]  
    > Si selecciona <STRONG>Force</STRONG>, la cuenta de usuario se mueve, pero los datos de usuario asociados tales conferencias y contactos programados no se mueven.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Para mover los usuarios de un grupo a otro mediante un filtro

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En **búsqueda de usuario**, haga clic en **Buscar**y, a continuación, haga clic en **Agregar filtro**.

5.  En los criterios de búsqueda, seleccione **registrar grupo**, seleccione **igual a**, seleccione **FQDN del grupo actual**y, a continuación, haga clic en **Buscar**.

6.  En el menú **acción** , haga clic en **mover todos los usuarios al grupo**.
    
    <div>
    

    > [!NOTE]  
    > Cuando se aplica un filtro a un conjunto de usuarios existente, la opción <STRONG>mover todos los usuarios al grupo</STRONG> se encuentra en el contexto del subconjunto filtrado de usuarios, no de <STRONG><EM>todos</EM></STRONG> los usuarios posibles.

    
    </div>

7.  En **mover usuarios**, seleccione el grupo que contiene las cuentas de usuario que desea mover en el **grupo de registrador de origen**.

8.  En **grupo de registradores de destino**, seleccione el grupo al que desea mover los usuarios.

9.  Faculta Si el servidor de destino o el grupo de servidores no están disponibles, active la casilla **forzar** .
    
    <div>
    

    > [!Caution]  
    > Si selecciona <STRONG>Force</STRONG>, la cuenta de usuario se mueve, pero los datos de usuario asociados tales conferencias y contactos programados no se mueven.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Para mover usuarios de un grupo a otro mediante cmdlets de Windows PowerShell

1.  En función de cómo ejecute los comandos de Windows PowerShell (es decir, de forma local o remota), tendrá que iniciar sesión como miembro de las funciones administrativas correctas de Lync Server 2013 de la siguiente manera:
    
    1.  Si está ejecutando los comandos en el equipo local (por ejemplo, inicia sesión directamente en un servidor de aplicaciones para el usuario): inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal como se describe en [permisos de configuración de delegado en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).
    
    2.  Si ejecuta los comandos de forma remota en otro equipo (por ejemplo, inicia sesión en el equipo y ejecuta los comandos de forma remota en un servidor front-end Standard Edition): desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator rol, inicie sesión en cualquier equipo de su implementación interna.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Para mover usuarios individuales, use el cmdlet Move-CsUser de la siguiente manera:
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    Donde el usuario debe mover es el usuario Pilar Ackerman, y el usuario se moverá de su grupo local asignado a la agrupación pool01.contoso.net

4.  Para mover un gran número de usuarios, use filtros con el cmdlet **Get-CsUser** y pase el conjunto de usuarios resultante a **Move-CsUser**:
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    Los comandos combinados de **Get-CsUser** y **Move-CsUser** pueden dar lugar a esto:
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a>Vea también


[Modificar las propiedades de la cuenta de usuario en Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

