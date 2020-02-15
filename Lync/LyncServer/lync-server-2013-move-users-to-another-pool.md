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
ms.openlocfilehash: 1feda518b1a15ce5b4622659b9e5df45044bcefa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a>Mover usuarios a otro grupo de servidores en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2018-02-09_

Puede usar el panel de control de Lync Server para asignar usuarios a un servidor o grupo de servidores específico.

<div>


> [!TIP]  
> Mover todos los usuarios existentes de un grupo de servidores de origen que ejecuta Lync Server 2010 o anterior a un grupo de servidores de destino de Lync Server 2013 en un entorno de Active Directory complejo puede dar como resultado una replicación más lenta de Active Directory. Para evitar esto, puede usar filtros de búsqueda para mover usuarios de grupos que ejecutan Lync Server 2010 o una versión anterior por separado, o puede usar el shell de administración de Lync Server para mover usuarios con cmdlets. Además, la funcionalidad de filtros funciona con los usuarios de Lync Server 2013.



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>Para mover determinados usuarios a otro servidor o grupo de servidores

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.

5.  En la tabla, seleccione uno o varios usuarios de la lista.

6.  En el menú **Acción**, haga clic en **Mover usuarios seleccionados a un grupo de servidores**.

7.  En **Mover usuarios**, seleccione el grupo de servidores al que desea trasladar los usuarios en **Grupo de registrador de destino**.

8.  (Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Forzar**.
    
    <div>
    

    > [!Caution]  
    > Si selecciona <STRONG>forzar</STRONG>, la cuenta de usuario se mueve, pero los datos de usuario asociados, las conferencias y los contactos programados no se mueven.

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>Para mover todos los usuarios de un servidor o grupo de servidores a otro servidor o grupo de servidores

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el menú **Acción**, haga clic en **Mover todos los usuarios a un grupo de servidores**.

5.  En **Mover usuarios**, seleccione el grupo de servidores que contiene las cuentas de usuario que desea trasladar en **Grupo de registrador de origen**.

6.  En **Grupo de registrador de destino**, seleccione el grupo de servidores al que desea trasladar los usuarios.

7.  (Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Imponer**.
    
    <div>
    

    > [!Caution]  
    > Si selecciona <STRONG>forzar</STRONG>, la cuenta de usuario se mueve, pero los datos de usuario asociados, las conferencias y los contactos programados no se mueven.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>Para mover usuarios de un grupo a otro grupo diferente mediante un filtro

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En **búsqueda de usuarios**, haga clic en **Buscar**y, a continuación, en **Agregar filtro**.

5.  En los Criterios de búsqueda, seleccione **Grupo de registradores**, **Igual que**, **FQDN del grupo actual** y, a continuación, haga clic en **Buscar**.

6.  En el menú **Acción**, haga clic en **Mover todos los usuarios al grupo**.
    
    <div>
    

    > [!NOTE]  
    > Cuando se aplica un filtro a un conjunto de usuarios existente, la opción <STRONG>mover todos los usuarios al grupo</STRONG> está en el contexto del subconjunto filtrado de usuarios, no de <STRONG><EM>todos</EM></STRONG> los usuarios posibles.

    
    </div>

7.  En **Mover usuarios**, seleccione el grupo de servidores que contiene las cuentas de usuario que desea trasladar en **Grupo de registradores de origen**.

8.  En **Grupo de registradores de destino**, seleccione el grupo de servidores al que desea trasladar los usuarios.

9.  (Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Forzar**.
    
    <div>
    

    > [!Caution]  
    > Si selecciona <STRONG>forzar</STRONG>, la cuenta de usuario se mueve, pero los datos de usuario asociados, las conferencias y los contactos programados no se mueven.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>Para mover usuarios de un grupo de servidores a otro mediante cmdlets de Windows PowerShell

1.  En función de cómo ejecute los comandos de Windows PowerShell (es decir, local o remotamente), debe iniciar sesión como miembro de los roles administrativos correctos de Lync Server 2013 de la siguiente manera:
    
    1.  Si está ejecutando los comandos en el equipo local (por ejemplo, inicia sesión directamente en un servidor front-end): inicie sesión en el equipo en el que está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).
    
    2.  Si ejecuta los comandos de forma remota en otro equipo (por ejemplo, inicia sesión en el equipo y ejecuta los comandos de forma remota en un servidor front-end Standard Edition): desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator rol, inicie sesión en cualquier equipo de la implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Para mover usuarios únicos, use el cmdlet Move-CsUser de la siguiente forma:
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    Donde el usuario que se moverá es Pilar Ackerman, y el usuario se moverá de su grupo de servidores principales actualmente asignado al grupo pool01.contoso.net

4.  Para mover una cantidad grande de usuarios, use filtros con el cmdlet **Get-CsUser** y pase el conjunto resultante de usuarios a **Move-CsUser**:
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    Los comandos combinados de los cmdlets **Get-CsUser** y **Move-CsUser** podrían dar el resultado siguiente:
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a>Vea también


[Modificación de las propiedades de la cuenta de usuario en Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

