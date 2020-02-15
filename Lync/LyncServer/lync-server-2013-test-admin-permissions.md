---
title: 'Lync Server 2013: permisos de administrador de pruebas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0acb60648333e228b3a48df379c794b6f2b43fce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

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
<td><p>Programación de comprobación</p></td>
<td><p>Después de la implementación inicial de Lync Server. Si es necesario, si surgen problemas relacionados con los permisos.</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsOUPermission. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Al instalar Lync Server 2013 1 de las tareas realizadas por el programa de instalación, el grupo RTCUniversalUserAdmins los permisos de Active Directory necesarios para administrar usuarios, equipos, contactos, contactos de aplicaciones y personas InetOrg. Si ha deshabilitado la herencia de permisos en el programa de instalación de Active Directory, no podrá asignar esos permisos. Como resultado, los miembros del grupo RTCUniversalUserAdmins no podrán administrar entidades de Lync Server. Estos privilegios de administración solo estarán disponibles para los administradores de dominio.

El cmdlet test-CsOUPermission comprueba que los permisos necesarios para administrar usuarios, equipos y otros objetos se establecen en un contenedor de Active Directory. Si estos permisos no están establecidos, puede resolver este problema mediante la ejecución del cmdlet [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .

Tenga en cuenta que Grant-CsOUPermission solo puede asignar permisos a miembros del grupo RTCUniversalUserAdmins. No puede usar este cmdlet para conceder permisos a un usuario o grupo arbitrario. Si desea que un usuario o grupo diferente tenga permisos de administración de usuarios, debe agregar el usuario (o grupo) al grupo RTCUniversalUserAdmins.

Para obtener más información sobre los permisos de OU, vea el artículo la [herencia de permisos está deshabilitada en los contenedores Computers, users o inetOrgPerson en Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para comprobar que los permisos de administración están establecidos en un contenedor, ejecute el cmdlet test-CsOUPermission seguido por el nombre distintivo del contenedor y por el tipo de permisos que está comprobando. Por ejemplo, este comando comprueba si los permisos de usuario están establecidos en ou ou = Redmond, DC = litwareinc, DC = com:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

Para comprobar varios permisos mediante un solo comando, encierre cada tipo de permiso entre comillas y, a continuación, separe los tipos con comas. Por ejemplo, este único comando comprueba los permisos de usuario, equipo y contacto:

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si ya se han establecido los permisos necesarios, test-CsOUPermission devolverá una respuesta de una palabra:

True

Si no se establecen los permisos necesarios, test-CsOUPermission devolverá el valor false. Es posible que deba buscar un momento para encontrar este valor. Por lo general, se incrustará en varias advertencias que lo acompañan. Por ejemplo:

ADVERTENCIA: entrada de control de acceso (ACE) ATL-CS\\-001 RTCUniversalUserReadOnlyGroup; permita ReadProperty ContainerInherit; Descendientes bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4

ADVERTENCIA: las entradas de control de acceso (ACE) del objeto "OU = Norteamérica, DC = ATL-CS-\\001 DC = LITWAREINC, DC = com" no están preparadas.

False

ADVERTENCIA: el procesamiento de "test-CsOUPermission" se completó con advertencias. se han registrado advertencias de "2" durante esta ejecución.

ADVERTENCIA: los resultados detallados se pueden encontrar en\\"\\C\\:\\users admin AppData local\\Temp\\test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de. html".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Si test-CsOUPermission produce un error, suele significar que no se ha asignado el permiso especificado al grupo RTCUniversalUserAdmins. Puede resolver este problema y asignar los permisos necesarios mediante el cmdlet Grant-CsOUPermission. Por ejemplo, este comando proporciona permisos de unidad organizativa para usuarios, contactos y inetOrgPersons al grupo RTCUniversalUserAdmins:

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

Para obtener más información, consulte el tema de ayuda para el cmdlet Grant-CsOUPermission.

</div>

</div>

<span> </span>

</div>

</div>

</div>

