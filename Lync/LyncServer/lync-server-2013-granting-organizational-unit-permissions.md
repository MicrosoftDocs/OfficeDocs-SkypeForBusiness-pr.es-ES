---
title: 'Lync Server 2013: Conceder permisos de unidad organizativa'
TOCTitle: Conceder permisos de unidad organizativa
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48276074
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conceder permisos de unidad organizativa en Lync Server 2013

 

_**Última modificación del tema:** 2012-05-14_

Use el cmdlet **Grant-CsOuPermission** para conceder permisos a objetos en unidades organizativas especificadas, de modo que los miembros de los grupos universales RTC creados mediante la preparación del bosque puedan obtener acceso a ellos sin ser miembros del grupo Admins. del dominio. Los permisos agregados a la unidad organizativa especificada son los mismos permisos que el cmdlet **Enable-CsAdDomain** agrega a los contenedores de usuarios y equipos durante la preparación del dominio.

Use el cmdlet **Test-CsOuPermission** para comprobar los permisos que ha configurado mediante el cmdlet **Grant-CsOuPermission**.

El cmdlet **Revoke-CsOuPermission** sirve para quitar cualquier permiso que se haya otorgado a través del cmdlet **Grant-CsOuPermission**.

## Para conceder permisos de unidades organizativas

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio donde desea conceder permisos de unidades organizativas. Use una cuenta que pertenezca al grupo Admins. del dominio o al grupo Administradores de organización (si la unidad organizativa se encuentra en otro dominio secundario).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.

## Para comprobar permisos de unidades organizativas

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio donde desee comprobar los permisos de unidades organizativas que haya concedido mediante el cmdlet **Grant-CsOuPermission**. Use una cuenta que pertenezca al grupo Admins. del dominio o al grupo Administradores de organización (si la unidad organizativa se encuentra en otro dominio secundario).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.

## Para revocar permisos de unidades organizativas

1.  Inicie sesión en un equipo que ejecute Lync Server 2013 en el dominio donde desee revocar los permisos de unidades organizativas que hayan sido concedidos mediante el cmdlet **Grant-CsOuPermission**. Use una cuenta que pertenezca al grupo Admins. del dominio o al grupo Administradores de organización (si la unidad organizativa se encuentra en otro dominio secundario).

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.

