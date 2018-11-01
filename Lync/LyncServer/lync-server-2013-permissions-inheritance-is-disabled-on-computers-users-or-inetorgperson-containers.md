---
title: "Herencia de permisos deshabilitada en contenedores Computer, Users o InetOrgPerson"
TOCTitle: La herencia de permisos está deshabilitada en los contenedores Computer, Users o InetOrgPerson
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48276600
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# La herencia de permisos está deshabilitada en los contenedores Computer, Users o InetOrgPerson en Lync Server 2013

 

_**Última modificación del tema:** 2014-12-19_

En un servicio de Servicios de dominio de Active Directory bloqueado, los objetos de usuario y de equipo se colocan a menudo en unidades organizativas específicas con la herencia de permisos deshabilitada para ayudar a proteger la delegación administrativa y para permitir al uso de objetos de directiva de grupo para la aplicación de directivas de seguridad.

La preparación del dominio y la activación del servidor definen las entradas de control de acceso (ACE) necesarias para Lync Server 2013. Cuando la herencia de permisos está deshabilitada, los grupos de seguridad de Lync Server no pueden heredar estas entradas ACE. Cuando estos permisos no se heredan, los grupos de seguridad de Lync Server no pueden tener acceso a la configuración y surgen los dos problemas siguientes:

  - Para administrar los objetos User, InetOrgPerson y Contact y para activar los servidores, los grupos de seguridad de Lync Server requieren entradas ACE establecidas por el procedimiento de preparación del dominio en los conjuntos de propiedades Comunicaciones en tiempo real (RTC), Búsqueda de usuarios RTC e Información pública de cada usuario. Cuando la herencia de permisos está deshabilitada, los grupos de seguridad no heredan estas entradas ACE y no pueden administrar los servidores o usuarios.

  - Para detectar los servidores y grupos de servidores, los servidores que ejecutan Lync Server se basan en las entradas ACE establecidas mediante la activación en los objetos relativos a equipos, incluidos el objeto Server y el contenedor de Microsoft. Cuando la herencia de permisos está deshabilitada, los grupos de seguridad, servidores y grupos de servidores no heredan estas entradas ACE y no pueden aprovecharlas.

Para resolver estos problemas, Lync Server proporciona el cmdlet **Grant-CsOuPermission**. Este cmdlet establece entradas ACE de Lync Server necesarias directamente en un contenedor especificado, y las unidades organizativas y los objetos del contenedor o la unidad organizativa.

## Definir permisos para los objetos User, InetOrgPerson y Contact después de ejecutar la preparación del dominio

En un entorno con Active Directory bloqueado donde la herencia de permisos está deshabilitada, la preparación del dominio no establece las entradas ACE necesarias en los contenedores o las unidades organizativas que incluyen los objetos User o InetOrgPerson del dominio. En esta situación, debe ejecutar el cmdlet **Grant-CsOuPermission** en cada contenedor o unidad organizativa que tenga objetos User o InetOrgPerson para los que la herencia de permisos esté deshabilitada. Si tiene una topología de bosque central, debe realizar también este procedimiento en los contenedores o unidades organizativas que contengan objetos de contacto. Para más información sobre las topologías de bosque, consulte [Topologías admitidas de Active Directory en Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) en la documentación sobre compatibilidad. El parámetro ObjectType especifica el tipo de objeto. El parámetro OU especifica la unidad organizativa.

Este cmdlet agrega las entradas ACE necesarias directamente en los contenedores o unidades organizativas especificados y los objetos User o InetOrgPerson del contenedor.

Necesita derechos de usuario equivalentes a los de los miembros del grupo Admins. del dominio para ejecutar este cmdlet. Si también se han quitado las entradas ACE de usuarios autenticados en el entorno bloqueado, debe conceder a esta cuenta acceso de lectura a las entradas ACE en los contenedores o unidades organizativas relevantes del dominio raíz del bosque, como se describe en [Se quitan los permisos de usuario autenticado en Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md), o usar una cuenta que sea miembro del grupo Administradores de organización.

**Para establecer las entradas ACE necesarias para los objetos User, InetOrgPerson y Contact**

1.  Inicie sesión en un equipo unido al dominio con una cuenta que sea miembro del grupo Admins. del dominio o que tenga derechos de usuario equivalentes.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.
    
    Por ejemplo:
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  En el archivo de registro, busque el resultado de ejecución **\<Correcto\>** al final de cada tarea para comprobar que se establecieron los permisos y, a continuación, cierre la ventana de registro. También puede ejecutar el comando siguiente para determinar si se establecieron los permisos:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    Por ejemplo:
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

## Establecer permisos para objetos de equipo después de ejecutar la preparación del dominio

En un entorno con Active Directory bloqueado donde la herencia de permisos está deshabilitada, la preparación del dominio no establece las entradas ACE necesarias en los contenedores o unidades organizativas que incluyen los objetos de equipo dentro del dominio. En esta situación, debe ejecutar el cmdlet **Grant-CsOuPermission** en cada contenedor o unidad organizativa que tenga equipos ejecutando Lync Server en los que la herencia de permisos esté deshabilitada. El parámetro ObjectType especifica el tipo de objeto.

Este procedimiento agrega las entradas ACE necesarias directamente en los contenedores especificados.

Necesita derechos de usuario equivalentes a los de los miembros del grupo Admins. del dominio para ejecutar este cmdlet. Si también se han quitado las entradas ACE de usuarios autenticados, debe conceder a esta cuenta acceso de lectura a las entradas ACE en los contenedores relevantes del dominio raíz del bosque, como se describe en [Se quitan los permisos de usuario autenticado en Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md), o usar una cuenta que sea miembro del grupo Administradores de organización.

**Para establecer las entradas ACE necesarias para los objetos de equipo**

1.  Inicie sesión en un equipo del dominio con una cuenta que sea miembro del grupo Admins. del dominio o que tenga derechos de usuario equivalentes.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.
    
    Por ejemplo:
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  En el archivo de registro C:\\Logs\\OUPermissions.xml, debería buscar el resultado de ejecución **\<Correcto\>** al final de cada tarea y comprobar que no haya errores; a continuación, cierre la ventana de registro. Para probar los permisos, puede ejecutar el siguiente cmdlet:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Por ejemplo:
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    

    > [!NOTE]
    > Si ejecuta la preparación del dominio en el dominio raíz del bosque en un entorno con Active Directory bloqueado, tenga en cuenta que Lync Server necesita tener acceso a los contenedores de esquema y de configuración en Active Directory.<BR>Si se quita el permiso de usuario autenticado predeterminado de los contenedores de esquema o de configuración en los AD DS, solo los miembros del grupo Administradores de esquema (para el contenedor de esquema) o del grupo Administradores de organización (para el contenedor de configuración) podrán tener acceso al contenedor específico. Dado que Setup.exe, los cmdlets del Shell de administración de Lync Server y el Panel de control de Lync Server necesitan tener acceso a estos contenedores, el programa de instalación y la instalación de las herramientas administrativas no se podrán ejecutar a menos que el usuario que ejecuta la instalación tenga derechos de usuario equivalentes a los de los miembros del grupo Administradores de esquema y Administradores de organización.<BR>Para solucionar esta situación, deberá conceder al grupo RTCUniversalGlobalWriteGroup acceso de lectura y escritura a los contenedores de esquema y de configuración.


