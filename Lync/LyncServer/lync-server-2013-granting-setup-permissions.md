---
title: 'Lync Server 2013: Concesión de permisos de instalación'
TOCTitle: Concesión de permisos de instalación
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48274528
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Concesión de permisos de instalación en Lync Server 2013

 

_**Última modificación del tema:** 2012-08-27_

El cmdlet **Grant-CsSetupPermission** sirve para agregar permisos Read, Write, ReadSPN y WriteSPN al grupo RTCUniversalServerAdmins en relación con una unidad organizativa de Active Directory en particular. De este modo, los miembros del grupo RTCUniversalServerAdmins de dicha unidad podrán instalar servidores que ejecuten Lync Server 2013 en el dominio especificado sin que tengan que pertenecer al grupo administradores del dominio.

Use el cmdlet **Test-CsSetupPermission** para comprobar los permisos que ha configurado mediante el cmdlet **Grant-CsSetupPermission**.

El cmdlet **Revoke-CsSetupPermission** sirve para quitar cualquier permiso que se haya otorgado a través del cmdlet **Grant-CsSetupPermission**.

## Para conceder permisos de instalación

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 del dominio donde desea conceder los permisos de instalación. Use una cuenta que pertenezca al grupo Admins. del dominio o al grupo Administradores de organización (si la unidad organizativa se encuentra en otro dominio secundario).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    El parámetro ComputerOu se puede especificar como relativo al contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN=Computers). Otra opción consiste en especificar este parámetro como nombre distintivo de toda la unidad organizativa (por ejemplo, "CN=Computers,DC=Contoso,DC=com") En este caso, se debe indicar un nombre distintivo de unidad organizativa coherente con el dominio especificado.
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.

## Para comprobar permisos de instalación

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que quiera comprobar los permisos de instalación que se han concedido mediante el cmdlet **Grant-CsSetupPermission**. Use una cuenta que pertenezca al grupo Admins. del dominio o al grupo Administradores de organización (si la unidad organizativa se encuentra en otro dominio secundario).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    El parámetro ComputerOu se puede especificar como relativo al contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN=Computers). Otra opción consiste en especificar este parámetro como nombre distintivo de toda la unidad organizativa (por ejemplo, "CN=Computers,DC=Contoso,DC=com") En este caso, se debe indicar un nombre distintivo de unidad organizativa coherente con el dominio especificado.
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.

## Para revocar permisos de instalación

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio en el que quiera revocar los permisos de instalación que se han concedido mediante el cmdlet **Grant-CsSetupPermission**. Use una cuenta que pertenezca al grupo Admins. del dominio o al grupo Administradores de organización (si la unidad organizativa se encuentra en otro dominio secundario).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    El parámetro ComputerOu se puede especificar como relativo al contexto de nomenclatura predeterminado del dominio especificado (por ejemplo, CN=Computers). Otra opción consiste en especificar este parámetro como nombre distintivo de toda la unidad organizativa (por ejemplo, "CN=Computers,DC=Contoso,DC=com") En este caso, se debe indicar un nombre distintivo de unidad organizativa coherente con el dominio especificado.
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.

