---
title: 'Lync Server 2013: La herencia de permisos está deshabilitada en los contenedores Computer, Users o InetOrgPerson'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73692539fb5dda38446ffddccbe35c8d366e2d67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>La herencia de permisos está deshabilitada en los contenedores Computer, Users o InetOrgPerson en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-12-19_

En los servicios de dominio de Active Directory bloqueados, los usuarios y los objetos de equipos se colocan a menudo en unidades organizativas específicas con la herencia de permisos deshabilitada para ayudar a proteger la delegación administrativa y para habilitar el uso de objetos de directiva de grupo (GPO) para exigir directivas de seguridad.

La preparación del dominio y la activación del servidor establecen las entradas de control de acceso (ACE) que necesita Lync Server 2013. Cuando la herencia de permisos está deshabilitada, los grupos de seguridad de Lync Server no pueden heredar estas ACE. Cuando no se heredan estos permisos, los grupos de seguridad de Lync Server no pueden obtener acceso a la configuración y se producen los dos problemas siguientes:

  - Para administrar usuarios, InetOrgPersons y contactos, y para trabajar con los servidores, los grupos de seguridad de Lync Server requieren entradas ACE establecidas por el procedimiento de preparación del dominio en los conjuntos de propiedades de cada usuario, en las comunicaciones en tiempo real (RTC), en la búsqueda de usuario RTC y en la información pública. . Cuando la herencia de permisos está deshabilitada, los grupos de seguridad no heredan estas ACE y no pueden administrar servidores ni usuarios.

  - Para descubrir servidores y grupos, los servidores que ejecutan Lync Server dependen de las entradas que se establecen mediante la activación en objetos relacionados con el equipo, incluidos el objeto servidor y el contenedor de Microsoft. Cuando la herencia de permisos está deshabilitada, los grupos de seguridad, los servidores y los grupos no heredan estas entradas ACE y no pueden aprovechar las ventajas de estas entradas.

Para solucionar estos problemas, Lync Server proporciona el cmdlet **Grant-CsOuPermission** . Este cmdlet establece las entradas de Lync Server requeridas directamente en un contenedor y unidades organizativas especificadas y en los objetos dentro del contenedor o la unidad organizativa.

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>Establecer permisos para objetos user, InetOrgPerson y Contact después de ejecutar la preparación del dominio

En un entorno de Active Directory bloqueado donde la herencia de permisos está deshabilitada, la preparación del dominio no establece las entradas ACE necesarias en los contenedores o unidades organizativas que contienen los usuarios o los objetos InetOrgPerson dentro del dominio. En esta situación, debe ejecutar el cmdlet **Grant-CsOuPermission** en cada contenedor o unidad organizativa que tenga objetos de usuario o inetOrgPerson para los que se haya deshabilitado la herencia de permisos. Si tiene una topología de bosque central, también debe realizar este procedimiento en los contenedores o en las unidades organizativas que contienen objetos de contacto. Para obtener más información sobre las topologías de bosque central, consulte [topologías de Active Directory admitidas en Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) en la documentación de soporte técnico. El parámetro ObjectType especifica el tipo de objeto. El parámetro OU especifica la unidad organizativa.

Este cmdlet agrega las ACE necesarias directamente en los contenedores o unidades organizativas especificados y los objetos user o InetOrgPerson dentro del contenedor. Si la OU en la que se ejecuta este comando tiene unidades organizativas secundarias con objetos user o InetOrgPerson, los permisos no se aplicarán a esos permisos. Tendrá que ejecutar el comando en cada unidad organizativa secundaria individualmente. Este es un escenario común con las implementaciones de hospedaje de Lync, por ejemplo, uo primaria = inquilinos de OCS, DC = CONTOSO, DC = LOCAL y secundarias = Tenant1, OU = OCS.

Necesita los derechos de usuario equivalentes a los miembros del grupo administradores de dominio para ejecutar este cmdlet. Si las entradas ACE de usuarios autenticados también se han eliminado en el entorno bloqueado, debe conceder a esta cuenta las entradas de acceso de lectura en los contenedores o las unidades organizativas relevantes del dominio raíz del bosque, como se describe en [permisos de usuario autenticados que se quitan en Lync. Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) o use una cuenta que sea miembro del grupo administradores de la empresa.

**Para establecer las entradas ACE necesarias para los objetos user, InetOrgPerson y Contact**

1.  Inicie sesión en un equipo unido al dominio con una cuenta que sea miembro del grupo administradores del dominio o que tenga derechos de usuario equivalentes.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Si no especifica el parámetro domain, el valor predeterminado es el dominio local.
    
    Por ejemplo:
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  En el archivo de registro, busque el resultado de la ejecución ** \<correcta\> ** al final de cada tarea para comprobar que se establecieron los permisos y, a continuación, cierre la ventana de registro. O bien, puede ejecutar el comando siguiente para determinar si se establecieron los permisos:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    Por ejemplo:
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>Establecer permisos para objetos de equipo después de ejecutar la preparación del dominio

En un entorno de Active Directory bloqueado donde la herencia de permisos está deshabilitada, la preparación del dominio no establece las entradas ACE necesarias en los contenedores o las unidades organizativas que contienen objetos de equipo dentro del dominio. En esta situación, debe ejecutar el cmdlet **Grant-CsOuPermission** en cada contenedor o unidad organizativa que tenga equipos que ejecuten Lync Server donde la herencia de permisos esté deshabilitada. El parámetro ObjectType especifica el tipo de objeto.

Este procedimiento agrega las entradas ACE necesarias directamente en los contenedores especificados.

Necesita los derechos de usuario equivalentes a los miembros del grupo administradores de dominio para ejecutar este cmdlet. Si las ACE de los usuarios autenticados también se han eliminado, debe conceder a esta cuenta las entradas de acceso de lectura en los contenedores relevantes del dominio raíz del bosque, como se describe en [permisos de usuario autenticados se quitan de Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) o usar una cuenta que sea miembro del grupo de administradores de la empresa.

**Para establecer las entradas ACE necesarias para objetos de equipo**

1.  Inicie sesión en el equipo del dominio con una cuenta que sea miembro del grupo administradores del dominio o que tenga derechos de usuario equivalentes.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Ejecute:
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Si no especifica el parámetro domain, el valor predeterminado es el dominio local.
    
    Por ejemplo:
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  En el archivo de registro C:\\registra\\OUPermissions. XML, debería buscar el resultado de la ejecución ** \<correcta\> ** al final de cada tarea y comprobar que no hay errores y, a continuación, cerrar el registro. Puede ejecutar el siguiente cmdlet para probar los permisos:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Por ejemplo:
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > Si ejecuta la preparación del dominio en el dominio raíz del bosque en un entorno de Active Directory bloqueado, tenga en cuenta que Lync Server requiere acceso al esquema y a los contenedores de configuración de Active Directory.<BR>Si se quita el permiso de usuario autenticado predeterminado del esquema o los contenedores de configuración de&nbsp;AD DS, solo se permiten miembros del grupo de administradores de esquema (para el contenedor de esquemas) o del grupo de administradores de la empresa (en el caso del contenedor de configuración). obtener acceso al contenedor determinado. Como Setup. exe, los cmdlets del shell de administración de Lync Server y el panel de control de Lync Server requieren acceso a estos contenedores, la configuración e instalación de las herramientas administrativas no se realizarán correctamente, a menos que el usuario que ejecuta la instalación tenga los derechos de usuario equivalentes al esquema Miembros del grupo administradores y administradores de empresa.<BR>Para solucionar este problema, debe conceder al grupo RTCUniversalGlobalWriteGroup lectura, acceso de escritura al esquema y a los contenedores de configuración.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

