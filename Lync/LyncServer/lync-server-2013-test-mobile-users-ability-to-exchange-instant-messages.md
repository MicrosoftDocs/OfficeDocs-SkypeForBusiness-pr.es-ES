---
title: 'Lync Server 2013: posibilidad de probar los mensajes instantáneos de los usuarios móviles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7fd19f6ef2f4a44a61d56848b4bf845c79736ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>Probar la capacidad de los usuarios móviles para intercambiar mensajes instantáneos en Lync Server 2013

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
<td><p>Programación de verificación</p></td>
<td><p>Cada mes</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsMcxP2PIM. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El servicio de movilidad permite que los usuarios de dispositivos móviles realicen estas acciones como:

1.  Intercambia mensajes instantáneos e información de presencia.

2.  Almacene y recupere el correo de voz internamente en lugar de con su proveedor de telefonía móvil.

3.  Aproveche las capacidades de Lync Server, como las llamadas a través del trabajo y las conferencias de acceso telefónico local.

El cmdlet test-CsMxcP2PIM ofrece una manera rápida y fácil de comprobar que los usuarios pueden usar el servicio de movilidad para intercambiar mensajes instantáneos.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para ejecutar esta prueba, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contengan el nombre y la contraseña de la cuenta) de cada cuenta. Después, debe incluir esos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsMcxP2PIM:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

Para obtener más información, vea el tema de ayuda para el cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si los dos usuarios de prueba pueden intercambiar mensajes instantáneos con el servicio de movilidad, test-CsMcxP2PIM devolverá el resultado de la prueba:

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino:http://atl-cs-001.litwareinc.com:443/mcx

Resultado: éxito

Latencia: 00:00:00

Mensaje de error:

Diagnóstico

Si se produce un error en la prueba, el resultado se establecerá en error y aparecerá un mensaje de error detallado y un diagnóstico:

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino:https://atl-cs-001.litwareinc.com:443/mcx

Resultado: error

Latencia: 00:00:00

Mensaje de error: no se recibió respuesta para el servicio de vales Web.

Excepción interna: la solicitud HHTP no está autorizada con

esquema de negociación de cliente ' NTLM '. La autenticación

el encabezado recibido del servidor era ' Negotiate, NTLM '.

Excepción interna: el servidor remoto devolvió un error:

(401) no autorizado.

Diagnóstico

Diagnosis interior: X-MS-Server-Fqdb: ATL-CS-

001.litwareinc.com

Cache-control: Private

Tipo de contenido: text/html; charset = utf-8.

Servidor: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate, NTLM

Alimentado por X: ASP.NET

Opciones de tipo de contenido X: nosniffing

Fecha: miércoles, 28 de mayo de 2014 19:16:05 GMT

Longitud del contenido: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Si prueba-CsMcxP2PIM da error, el primer paso debe ser comprobar que el servicio de movilidad está funcionando. Esto se puede realizar con un explorador Web para comprobar que se puede acceder a la dirección URL del servicio de movilidad de su grupo de Lync Server. Por ejemplo, este comando comprueba la dirección URL del grupo atl-cs-001.litwareinc.com:

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

Si el servicio de movilidad parece estar ejecutándose, compruebe que los dos usuarios de prueba tengan cuentas válidas de Lync Server. Puede recuperar información de la cuenta mediante un comando similar a este:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Si la propiedad Enabled no es igual a true o si se produce un error en el comando, significa que el usuario no tiene una cuenta válida de Lync Server.

También debe comprobar que el usuario está habilitado para la movilidad. Para ello, primero determine la Directiva de movilidad que está asignada a la cuenta:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Una vez que conozca el nombre de la Directiva, use el cmdlet Get-CsMobilityPolicy para comprobar que la Directiva en cuestión (por ejemplo, RedmondMobilityPolicy) tiene la propiedad EnableMobility establecida en true:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Si recibe un mensaje de error con encabezados de autenticación, eso a menudo significa que no ha especificado una cuenta de usuario válida. Compruebe el nombre de usuario y la contraseña y, a continuación, vuelva a intentar la prueba. Si está convencido de que la cuenta de usuario es válida, use el cmdlet Get-CsWebServiceConfiguration y compruebe el valor de la propiedad UseWindowsAuth. Que le indicará qué métodos de autenticación están habilitados en su organización. Para obtener más información sobre cómo solucionar problemas del servicio de movilidad, vea la [solución de problemas de la conectividad de movilidad de Lync externa](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

