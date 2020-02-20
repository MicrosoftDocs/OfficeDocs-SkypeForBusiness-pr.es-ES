---
title: 'Lync Server 2013: posibilidad de probar la capacidad de los usuarios móviles para intercambiar mensajes instantáneos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5885ed34fd28f06b9a7d8c4f95abc29d3b5e147
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsMcxP2PIM. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El servicio de movilidad permite a los usuarios de dispositivos móviles realizar tareas como las siguientes:

1.  Intercambiar mensajes instantáneos e información de presencia.

2.  Almacene y recupere el correo de voz internamente en lugar de con su proveedor de telefonía móvil.

3.  Aproveche las ventajas de las capacidades de Lync Server, como las llamadas a través del trabajo y las conferencias de acceso telefónico local.

El cmdlet test-CsMxcP2PIM proporciona una forma rápida y sencilla de comprobar que los usuarios pueden usar el servicio de movilidad para intercambiar mensajes instantáneos.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para ejecutar esta prueba, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta. A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsMcxP2PIM:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si los dos usuarios de prueba pueden intercambiar mensajes instantáneos mediante el servicio de movilidad, test-CsMcxP2PIM devolverá el resultado de la prueba correcta:

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino:http://atl-cs-001.litwareinc.com:443/mcx

Resultado: correcto

Latencia: 00:00:00

Mensaje de error:

Diagnóstico

Si se produce un error en la prueba, el resultado se establecerá en error y se mostrará un mensaje de error detallado y un diagnóstico:

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino:https://atl-cs-001.litwareinc.com:443/mcx

Resultado: error

Latencia: 00:00:00

Mensaje de error: no se recibió ninguna respuesta para el servicio de vales Web.

Excepción interna: la solicitud HHTP no está autorizada con

esquema de negociación del cliente ' NTLM '. La autenticación

el encabezado recibido del servidor era ' Negotiate, NTLM '.

Excepción interna: el servidor remoto devolvió un error:

(401) no autorizado.

Diagnóstico

Diagnóstico interno: X-MS-Server-Fqdb: ATL-CS-

001.litwareinc.com

Cache-control: privado

Content-Type: text/html; charset = utf-8.

Servidor: Microsoft-IIS/8.5

WWW-Authenticate: Negotiate, NTLM

Alimentado por X: ASP.NET

Opciones de tipo de contenido X: nosniffing

Fecha: miércoles, 28 de mayo de 2014 19:16:05 GMT

Longitud del contenido: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Si test-CsMcxP2PIM produce un error, el primer paso debe ser comprobar que el servicio de movilidad está en funcionamiento. Esto se puede hacer con un explorador Web para comprobar que se puede tener acceso a la dirección URL del servicio de movilidad de su grupo de Lync Server. Por ejemplo, este comando comprueba la dirección URL del grupo atl-cs-001.litwareinc.com:

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

Si el servicio de movilidad parece estar en ejecución, compruebe que los dos usuarios de prueba tengan cuentas de Lync Server válidas. Puede recuperar la información de la cuenta con un comando similar al siguiente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Si la propiedad Enabled no es igual a true o si se produce un error en el comando, significa que el usuario no tiene una cuenta de Lync Server válida.

También debe comprobar que el usuario está habilitado para la movilidad. Para ello, en primer lugar, determine la Directiva de movilidad que se asigna a la cuenta:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

Una vez que conoce el nombre de la Directiva, use el cmdlet Get-CsMobilityPolicy para comprobar que la Directiva en cuestión (por ejemplo, RedmondMobilityPolicy) tiene la propiedad Enablemobility configurada establecida en true:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

Si recibe un mensaje de error con encabezados de autenticación, a menudo significa que no ha especificado una cuenta de usuario válida. Compruebe el nombre de usuario y la contraseña y, a continuación, vuelva a intentar la prueba. Si está convencido de que la cuenta de usuario es válida, use el cmdlet Get-CsWebServiceConfiguration y compruebe el valor de la propiedad UseWindowsAuth. Esto le dirá qué métodos de autenticación están habilitados en la organización. Para obtener más información sobre cómo solucionar problemas del servicio de movilidad, vea el blog de [Troubleshooting external Lync Mobility Connectivity issues Step-by-Step](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

