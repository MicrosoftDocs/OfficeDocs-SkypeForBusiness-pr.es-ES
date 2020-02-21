---
title: 'Lync Server 2013: derechos de topología de administración de prueba'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 050ba83b4598fc5ed8ed3d40d0b1aa02ba9356b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a>Probar los derechos de topología de administración en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-12-08_


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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsSetupPermission. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

De forma predeterminada, solo los administradores de dominio pueden habilitar una topología de Lync Server y realizar cambios importantes en la infraestructura de Lync Server. Esto no será un problema siempre que los administradores de dominio y los administradores de Lync Server sean uno y el mismo. En muchas organizaciones, los administradores de Lync Server no mantienen derechos administrativos en todo el dominio. De forma predeterminada, esto significa que estos administradores (definidos como miembros del grupo RTCUniversalServerAdmins) no pueden hacer cambios en la topología de Lync Server. Para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho de realizar cambios en la topología, debe asignar los permisos necesarios de Active Directory mediante el cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) .

El cmdlet test-CsSetupPermission comprueba que los permisos necesarios para instalar Lync Server o uno de sus componentes estén configurados en el contenedor de Active Directory especificado. Si no se asignan los permisos, puede ejecutar el cmdlet Grant-CsSetupPermission para conceder a los miembros del grupo RTCUniversalServerAdmins el derecho de instalar y habilitar Lync Server.

<div>


> [!NOTE]  
> Para obtener una lista detallada de los permisos asignados por Grant-CsSetupPermission, consulte la entrada de blog <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission y Grant-CsOUPermission</A>.



</div>

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para determinar si se asignan permisos de configuración para un contenedor de Active Directory, llame al cmdlet test-CsSetupPermission. Especifique el nombre distintivo del contenedor que se va a comprobar. Por ejemplo, este comando comprueba los permisos de configuración en el contenedor ou = CsServers, DC = litwareinc, DC = com:

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si test-CsSetupPermission determina que ya se han establecido los permisos necesarios en un contenedor de Active Directory, el cmdlet devolverá el valor true:

True

Si no se establecen los permisos, test-CsSetupPermission devolverá el valor false. Tenga en cuenta que este valor normalmente se incluirá en muchos mensajes de advertencia. Por ejemplo:

ADVERTENCIA: entrada de control de acceso (ACE) ATL-CS\\-001 RTCUniversalServerAdmins; Permita ExtendedRight; None None 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

ADVERTENCIA: las entradas de control de acceso (ACE) del objeto "CN = Computers, DC = litwareinc, DC = com" no están preparadas.

False

ADVERTENCIA: el procesamiento de "test-CsSetupPermission" se completó con advertencias. se han registrado advertencias de "2" durante esta ejecución.

ADVERTENCIA: los resultados detallados se pueden encontrar en\\"\\C\\:\\users admin local\\Temp\\test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118. html".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Aunque existen raras excepciones, si test-CsSetupPermission produce un error que suele significar que no se asignan permisos de configuración para el contenedor de Active Directory especificado. Estos permisos se pueden asignar mediante el cmdlet Grant-CsSetupPermission. Por ejemplo, este comando concede permisos de configuración al contenedor Computers del dominio litwareinc.com:

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

