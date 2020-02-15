---
title: 'Lync Server 2013: probar el acceso de usuarios móviles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6052785bdb8e748ac657d800a630ecc76415af9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42021341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a>Probar el acceso de usuarios móviles en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Programación de comprobación</p></td>
<td><p>Mensualmente</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsMcxConference. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El servicio de movilidad permite a los usuarios de dispositivos móviles realizar tareas como las siguientes:

1.  Intercambiar mensajes instantáneos e información de presencia.

2.  Almacene y recupere el correo de voz internamente en lugar de con su proveedor de telefonía móvil.

3.  Aproveche las ventajas de las capacidades de Lync Server, como las llamadas a través del trabajo y las conferencias de acceso telefónico local. El cmdlet test-CsMcxConference proporciona una forma rápida y sencilla de comprobar que los usuarios pueden unirse a conferencias de Lync Server y participar en ellas mediante un dispositivo móvil.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para ejecutar esta comprobación, debe crear tres objetos de credenciales de Windows PowerShell (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta. A continuación, debe incluir los objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsMcxConference como se muestra en el siguiente ejemplo:

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si la comprobación se realiza correctamente, test-CsMcxConference informará de que se ha realizado correctamente un resultado de prueba:

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino:http://atl-cs-001.litwareinc.com:443/mcx

Resultado: correcto

Latencia: 00:00:00

Mensaje de error:

Diagnóstico

Si la comprobación es incorrecta test-CsMcxConference notificará un resultado de prueba de error. Por lo general, este resultado de la prueba irá acompañado de un mensaje de error detallado y diagnóstico. Por ejemplo:

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino:https://atl-cs-001.litwareinc.com:443/mcx

Resultado: error

Latencia: 00:00:00

Mensaje de error: no se recibió ninguna respuesta para el servicio de vales Web.

Excepción interna: la solicitud HHTP no está autorizada con el cliente

esquema de negociación ' NTLM '. El encabezado de autenticación recibido

del servidor fue "Negotiate".

Excepción interna: el servidor remoto devolvió un error: (401)

No autorizado.

Diagnóstico

Diagnóstico interno: X-MS-Server-Fqdb: atl-cs-001.litwareinc.com

Cache-control: privado

Content-Type: text/html; charset = utf-8.

Servidor: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate, NTLM

Alimentado por X: ASP.NET

Opciones de tipo de contenido X: nosniffing

Fecha: miércoles, 28 de mayo de 2014 19:22:19 GMT

Longitud del contenido: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Si test-CsMcxConference produce un error, debe comprobar que el servicio de movilidad se está ejecutando y que se puede tener acceso a él. Esto se puede hacer con un explorador Web para comprobar que se puede tener acceso a la dirección URL del servicio de movilidad de su grupo de Lync Server. Por ejemplo, este comando comprueba la dirección URL del grupo atl-cs-001.litwareinc.com:

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

Si se puede tener acceso al servicio de movilidad, debe comprobar que los usuarios de prueba tengan cuentas de Lync Server válidas. Puede recuperar la información de la cuenta con un comando similar al siguiente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Si la propiedad Enabled no es igual a true o si se produce un error en el comando, significa que el usuario no tiene una cuenta de Lync Server válida. También debe comprobar que cada cuenta de usuario esté habilitada para la movilidad. Para ello, en primer lugar, determine la Directiva de movilidad que se asigna a la cuenta:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Una vez que conoce el nombre de la Directiva, use el cmdlet Get-CsMobilityPolicy para comprobar que la Directiva en cuestión (por ejemplo, RedmondMobilityPolicy) tiene la propiedad Enablemobility configurada establecida en true:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Si recibe un mensaje de error de "encabezado de autenticación" cuando ejecuta test-CsMcxConference que a menudo significa que no ha especificado una cuenta de usuario válida, compruebe el nombre de usuario y la contraseña y, a continuación, vuelva a intentar la prueba. Si está convencido de que la cuenta de usuario es válida, use el cmdlet Get-CsWebServiceConfiguration y compruebe el valor de la propiedad UseWindowsAuth. Esto le dirá qué métodos de autenticación están habilitados en la organización.

Para obtener más información sobre cómo solucionar problemas del servicio de movilidad, vea el blog de [Troubleshooting external Lync Mobility Connectivity issues Step-by-Step](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

