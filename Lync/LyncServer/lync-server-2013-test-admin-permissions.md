---
title: 'Lync Server 2013: permisos de administrador de prueba'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3da940b30822a5cfcc1fed302ff3db1f34bd8380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a>Probar permisos de administrador en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-18_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Programación de verificación</p></td>
<td><p>Después de la implementación inicial de Lync Server. Según sea necesario, si surgen problemas relacionados con los permisos.</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsOUPermission. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Al instalar Lync Server 2013 1 de las tareas que realizó el programa de instalación, el grupo RTCUniversalUserAdmins los permisos de Active Directory que se necesitan para administrar usuarios, equipos, contactos, contactos de aplicaciones y personas de InetOrg. Si ha deshabilitado la herencia de permisos en la instalación de Active Directory, no podrá asignar esos permisos. Como resultado, los miembros del grupo RTCUniversalUserAdmins no podrán administrar entidades de Lync Server. Esos privilegios de administración solo estarán disponibles para los administradores de dominio.

El cmdlet test-CsOUPermission comprueba que los permisos necesarios para administrar usuarios, equipos y otros objetos se establecen en un contenedor de Active Directory. Si no se han establecido esos permisos, puede resolver este problema ejecutando el cmdlet [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .

Tenga en cuenta que Grant-CsOUPermission solo puede asignar permisos a miembros del grupo RTCUniversalUserAdmins. No puede usar este cmdlet para conceder permisos a un usuario o grupo arbitrario. Si desea que un usuario o grupo diferente tenga permisos de administración de usuarios, debe agregar ese usuario (o grupo) al grupo RTCUniversalUserAdmins.

Para obtener más información sobre los permisos de Uo, vea el artículo la [herencia de permisos está deshabilitada en los contenedores de equipos, usuarios o inetOrgPerson en Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para comprobar que los permisos de administración se establecen en un contenedor, ejecute el cmdlet test-CsOUPermission seguido del nombre distintivo del contenedor y del tipo de permisos que está comprobando. Por ejemplo, este comando comprueba si los permisos de usuario están establecidos en la ou ou = Redmond, DC = litwareinc, DC = com:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

Para comprobar varios permisos con un solo comando, encierra cada tipo de permiso entre comillas y luego separa esos tipos con comas. Por ejemplo, este comando comprueba los permisos de usuario, equipo y contacto:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

Para obtener más información, vea el tema de ayuda para el cmdlet [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si los permisos necesarios ya se han establecido, test-CsOUPermission devolverá una respuesta de una palabra:

True

Si no se establecen los permisos necesarios, test-CsOUPermission devolverá el valor false. Es posible que tenga que buscar un momento para encontrar este valor. Normalmente, se incluirá en varias advertencias de acompañamiento. Por ejemplo:

ADVERTENCIA: entrada de control de acceso (ACE) ATL-CS\\-001 RTCUniversalUserReadOnlyGroup; permitir ReadProperty; ContainerInherit; Descendientes; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4

ADVERTENCIA: las entradas de control de acceso (ACE) del objeto "OU = Norteamérica, DC = ATL-CS-\\001 DC = LITWAREINC, DC = com" no están listas.

False

ADVERTENCIA: el procesamiento de "prueba-CsOUPermission" se completó con advertencias. durante esta ejecución, se grabaron "2" advertencias.

ADVERTENCIA: los resultados detallados se encuentran en "\\C\\:\\users\\admin\\\\local Temp test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de. html".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Si prueba-CsOUPermission se produce un error que normalmente significa que el permiso especificado no se ha asignado al grupo RTCUniversalUserAdmins. Puede resolver este problema y asignar los permisos necesarios mediante el cmdlet Grant-CsOUPermission. Por ejemplo, este comando proporciona a los usuarios, los contactos y el inetOrgPersons permisos para el grupo RTCUniversalUserAdmins:

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

Para obtener más información, consulte el tema de ayuda para el cmdlet Grant-CsOUPermission.

</div>

</div>

<span> </span>

</div>

</div>

</div>

