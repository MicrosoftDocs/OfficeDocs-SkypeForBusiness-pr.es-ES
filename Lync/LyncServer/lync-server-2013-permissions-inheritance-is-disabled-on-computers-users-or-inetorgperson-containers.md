---
title: 'Lync Server 2013: la herencia de permisos está deshabilitada en los contenedores Computer, users o InetOrgPerson'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6f0ac6b7614da844a35f97070b61f1b074a4367
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>La herencia de permisos está deshabilitada en los contenedores Computers, users o InetOrgPerson en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-19_

En los servicios de dominio de Active Directory bloqueados, los objetos de usuarios y equipos a menudo se colocan en unidades organizativas específicas con la herencia de permisos deshabilitada para ayudar a proteger la delegación administrativa y habilitar el uso de objetos de directiva de grupo (GPO). para aplicar directivas de seguridad.

La preparación del dominio y la activación del servidor establecen las entradas de control de acceso (ACE) que necesita Lync Server 2013. Cuando la herencia de permisos está deshabilitada, los grupos de seguridad de Lync Server no pueden heredar estas ACE. Cuando estos permisos no se heredan, los grupos de seguridad de Lync Server no pueden obtener acceso a la configuración y se producen los dos problemas siguientes:

  - Para administrar usuarios, InetOrgPersons y contactos, y para operar los servidores, los grupos de seguridad de Lync Server requieren ACE establecidos por el procedimiento de preparación del dominio en cada conjunto de propiedades de usuario, comunicaciones en tiempo real (RTC), búsqueda de usuarios RTC e información pública . Cuando la herencia de permisos está deshabilitada, los grupos de seguridad no heredan estas entradas ACE y no pueden administrar los servidores o usuarios.

  - Para detectar servidores y grupos de servidores, los servidores que ejecutan Lync Server se basan en ACE que se establecen mediante la activación en objetos relacionados con el equipo, incluido el objeto de servidor y el contenedor de Microsoft. Cuando la herencia de permisos está deshabilitada, los grupos de seguridad, servidores y grupos de servidores no heredan estas entradas ACE y no pueden aprovecharlas.

Para solucionar estos problemas, Lync Server proporciona el cmdlet **Grant-CsOuPermission** . Este cmdlet establece las entradas ACE de Lync Server necesarias directamente en un contenedor y unidades organizativas especificadas y en los objetos del contenedor o la unidad organizativa.

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>Definir permisos para los objetos User, InetOrgPerson y Contact después de ejecutar la preparación del dominio

En un entorno con Active Directory bloqueado donde la herencia de permisos está deshabilitada, la preparación del dominio no establece las entradas ACE necesarias en los contenedores o las unidades organizativas que incluyen los objetos User o InetOrgPerson del dominio. En esta situación, debe ejecutar el cmdlet **Grant-CsOuPermission** en cada contenedor o unidad organizativa que tenga objetos User o InetOrgPerson para los que la herencia de permisos esté deshabilitada. Si tiene una topología de bosque central, debe realizar también este procedimiento en los contenedores o unidades organizativas que contengan objetos de contacto. Para obtener más información sobre las topologías de bosques centrales, consulte [topologías admitidas de Active Directory en Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) en la documentación sobre compatibilidad. El parámetro ObjectType especifica el tipo de objeto. El parámetro OU especifica la unidad organizativa.

Este cmdlet agrega las entradas ACE necesarias directamente en los contenedores o unidades organizativas especificados y los objetos User o InetOrgPerson del contenedor. Si la unidad organizativa en la que se ejecuta este comando tiene unidades organizativas secundarias con objetos user o InetOrgPerson, los permisos no se aplicarán a dichos permisos. Tendrá que ejecutar el comando individualmente en cada unidad organizativa secundaria. Este es un escenario común con las implementaciones de hospedaje de Lync, por ejemplo, OU primaria = inquilinos de OCS, DC = CONTOSO, DC = LOCAL y secundaria OU = Tenant1, OU = inquilinos de OCS, DC = CONTOSO, DC = LOCAL.

Necesita tener los derechos de usuario equivalentes a la pertenencia al grupo administradores de dominio para ejecutar este cmdlet. Si las ACE de los usuarios autenticados también se han quitado en el entorno bloqueado, debe conceder a esta cuenta las entradas ACE de acceso de lectura en los contenedores relevantes o en las unidades organizativas del dominio raíz del bosque, tal y como se describe en los [permisos de usuario autenticados, se quitan en Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) o use una cuenta que sea miembro del grupo administradores de empresa

**Para establecer las entradas ACE necesarias para los objetos User, InetOrgPerson y Contact**

1.  Inicie sesión en un equipo unido al dominio con una cuenta que sea miembro del grupo Admins. del dominio o que tenga derechos de usuario equivalentes.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Realizar
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.
    
    Por ejemplo:
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  En el archivo de registro, busque resultado de ejecución ** \<correcta\> ** al final de cada tarea para comprobar que se establecieron los permisos y, a continuación, cierre la ventana de registro. También puede ejecutar el comando siguiente para determinar si se establecieron los permisos:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    Por ejemplo:
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>Establecer permisos para objetos de equipo después de ejecutar la preparación del dominio

En un entorno con Active Directory bloqueado donde la herencia de permisos está deshabilitada, la preparación del dominio no establece las entradas ACE necesarias en los contenedores o unidades organizativas que incluyen los objetos de equipo dentro del dominio. En esta situación, debe ejecutar el cmdlet **Grant-CsOuPermission** en cada uno de los contenedores o unidades organizativas que tienen equipos que ejecutan Lync Server y la herencia de permisos está deshabilitada. El parámetro ObjectType especifica el tipo de objeto.

Este procedimiento agrega las entradas ACE necesarias directamente en los contenedores especificados.

Necesita tener los derechos de usuario equivalentes a la pertenencia al grupo administradores de dominio para ejecutar este cmdlet. Si también se han quitado las ACE de usuario autenticado, debe conceder a esta cuenta las entradas ACE de acceso de lectura en los contenedores relevantes del dominio raíz del bosque, tal y como se describe en [permisos de usuario autenticados, se quitan en Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) o use una cuenta que sea miembro del grupo administradores de la empresa.

**Para establecer las entradas ACE necesarias para los objetos de equipo**

1.  Inicie sesión en un equipo del dominio con una cuenta que sea miembro del grupo Admins. del dominio o que tenga derechos de usuario equivalentes.

2.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.

3.  Realizar
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Si no se especifica el parámetro Domain, el valor predeterminado es el dominio local.
    
    Por ejemplo:
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  En el archivo de registro de ejemplo\\C\\: registra OUPermissions. XML, busque el resultado de la ejecución ** \<correcta\> ** al final de cada tarea y compruebe que no haya errores y, a continuación, cierre el registro. Para probar los permisos, puede ejecutar el siguiente cmdlet:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Por ejemplo:
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > Si ejecuta la preparación del dominio en el dominio raíz del bosque en un entorno de Active Directory bloqueado, tenga en cuenta que Lync Server requiere acceso al esquema de Active Directory y a los contenedores de configuración.<BR>Si se quita el permiso de usuario autenticado predeterminado del esquema o los contenedores de configuración en&nbsp;AD DS, solo se permite que los miembros del grupo de administradores de esquema (para el contenedor de esquemas) o del grupo de administradores de la empresa (para el contenedor de configuración) tengan acceso al contenedor especificado. Debido a que Setup. exe, los cmdlets del shell de administración de Lync Server y el panel de control de Lync Server necesitan acceso a estos contenedores, se producirá un error en la instalación e instalación de las herramientas administrativas, a menos que el usuario que ejecuta la instalación tenga derechos de usuario equivalentes al esquema Administradores y pertenencia al grupo administradores de empresa.<BR>Para solucionar esta situación, deberá conceder al grupo RTCUniversalGlobalWriteGroup acceso de lectura y escritura a los contenedores de esquema y de configuración.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

