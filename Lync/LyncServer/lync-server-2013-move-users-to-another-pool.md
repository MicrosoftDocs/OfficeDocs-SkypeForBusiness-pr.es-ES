---
title: Mover usuarios a otro grupo en Lync Server 2013
TOCTitle: Mover usuarios a otro grupo en Lync Server 2013
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48277012
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Mover usuarios a otro grupo en Lync Server 2013

 

_**Última modificación del tema:** 2013-03-11_

Puede usar Panel de control de Lync Server para asignar usuarios a un determinado servidor o grupo de servidores.

> [!TIP]  
> Si se trasladan todos los usuarios existentes de un grupo de servidores de origen que ejecuta Microsoft Office Communications Server 2007 R2 o una versión anterior a un grupo de destino de Lync Server 2013en un entorno de Active Directory complejo, es posible que la replicación de Active Directory sea más lenta. Para evitarlo, puede usar filtros de búsqueda y mover los usuarios de grupos de servidores que ejecutan Microsoft Office Communications Server 2007 R2 por separado, o bien usar Shell de administración de Lync Server para trasladar usuarios con cmdlets. Además, la función de filtrado funciona con usuarios de Lync Server 2013.



## Para mover determinados usuarios a otro servidor o grupo de servidores

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario que desee y, a continuación, haga clic en **Buscar**.

5.  En la tabla, seleccione uno o varios usuarios de la lista.

6.  En el menú **Acción**, haga clic en **Mover usuarios seleccionados a un grupo de servidores**.

7.  En **Mover usuarios**, seleccione el grupo de servidores al que desea trasladar los usuarios en **Grupo de registrador de destino**.

8.  (Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Imponer**.
    
    > [!WARNING]  
    > Si selecciona <strong>Forzar</strong>, se mueve la cuenta de usuario pero se eliminan los datos de usuario asociados (por ejemplo, conferencias que el usuario ha programado). Si no se selecciona, se mueven la cuenta y los datos asociados.
    


## Para mover todos los usuarios de un servidor o grupo de servidores a otro servidor o grupo de servidores

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el menú **Acción**, haga clic en **Mover todos los usuarios a un grupo de servidores**.

5.  En **Mover usuarios**, seleccione el grupo de servidores que contiene las cuentas de usuario que desea trasladar en **Grupo de registrador de origen**.

6.  En **Grupo de registrador de destino**, seleccione el grupo de servidores al que desea trasladar los usuarios.

7.  (Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Imponer**.
    
    > [!WARNING]  
    > Si selecciona <strong>Forzar</strong>, se mueve la cuenta de usuario pero se eliminan los datos de usuario asociados (por ejemplo, conferencias que el usuario ha programado). Si no se selecciona, se mueven la cuenta y los datos asociados.
    


## Para mover usuarios de un grupo a otro grupo diferente mediante un filtro

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En **Búsqueda de usuarios**, haga clic en **Buscar** y en **Agregar filtro**.

5.  En los Criterios de búsqueda, seleccione **Grupo de registradores**, **Igual que**, **FQDN del grupo actual** y, a continuación, haga clic en **Buscar**.

6.  En el menú **Acción**, haga clic en **Mover todos los usuarios al grupo**.
    

    > [!NOTE]
    > Cuando se aplica un filtro a un conjunto de usuarios existente, la opción <STRONG>Mover todos los usuarios al grupo</STRONG> se refiere al subconjunto de usuarios filtrados, no a <STRONG><EM>todos</EM></STRONG> los usuarios posibles.



7.  En **Mover usuarios**, seleccione el grupo de servidores que contiene las cuentas de usuario que desea trasladar en **Grupo de registradores de origen**.

8.  En **Grupo de registradores de destino**, seleccione el grupo de servidores al que desea trasladar los usuarios.

9.  (Opcional) Si el servidor o grupo de destino no está disponible, active la casilla **Forzar**.
    
    > [!WARNING]  
    > Si selecciona <strong>Forzar</strong>, se mueve la cuenta de usuario pero se eliminan los datos de usuario asociados (por ejemplo, conferencias que el usuario ha programado y contactos). Si no se selecciona, se mueven la cuenta y los datos asociados.
    


## Para mover usuarios de un grupo de servidores a otro mediante el Shell de administración de Communications Server

1.  En función de cómo ejecute los comandos de Windows PowerShell (es decir, local o remotamente), deberá iniciar sesión como un miembro de los roles administrativos correctos de Lync Server 2013, tal como sigue:
    
    1.  Si está ejecutando los comandos en el equipo local (por ejemplo, inicia sesión directamente en un Servidor front-end): Inicie sesión en un equipo que tenga instalado el Shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios que se describen en [Delegar permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).
    
    2.  Si está ejecutando los comandos de forma remota en otro equipo (por ejemplo, inicia sesión en su equipo y ejecuta los comandos de forma remota en un Servidor front-end Standard Edition): Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Para mover usuarios únicos, use el cmdlet Move-CsUser de la siguiente forma:
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    Donde el usuario que se moverá es Pilar Ackerman, y el usuario se moverá de su grupo de servidores principales actualmente asignado al grupo pool01.contoso.net

4.  Para mover una cantidad grande de usuarios, use filtros con el cmdlet **Get-CsUser** y pase el conjunto resultante de usuarios a **Move-CsUser**:
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    Los comandos combinados de los cmdlets **Get-CsUser** y **Move-CsUser** podrían dar el resultado siguiente:
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

## Vea también

#### Otros recursos

[Modificación de las propiedades de cuentas de usuario](lync-server-2013-modifying-user-account-properties.md)

