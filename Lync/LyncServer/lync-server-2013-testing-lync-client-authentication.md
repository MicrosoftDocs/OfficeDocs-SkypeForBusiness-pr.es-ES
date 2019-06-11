---
title: 'Lync Server 2013: comprobación de la autenticación de clientes de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d8ea26c39582a69062526c7b4ae00343bb19482
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>Prueba de la autenticación de clientes de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Programación de verificación</p></td>
<td><p>Cada día</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsClientAuth. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsClientAuth le permite determinar si un usuario puede iniciar sesión en el servidor de Lync con un certificado de cliente, puede ejecutar el cmdlet test-CsClientAuth. Después de llamar a test-CsClientAuth, el cmdlet se pondrá en contacto con el servicio de aprovisionamiento de certificados y descargará una copia de todos los certificados de cliente del usuario especificado. Si se puede encontrar y descargar un certificado de cliente, test-CsClientAuth intentará iniciar sesión con ese certificado. Si el inicio de sesión se realiza correctamente, test-CsClientAuth cerrará e informará de que la prueba se realizó correctamente. Si un certificado no se puede encontrar o descargar, o si el cmdlet no puede iniciar sesión con ese certificado, test-CsClientAuth le informará de que se produjo un error en la prueba.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsClientAuth se ejecuta con la cuenta de cualquier usuario que esté habilitado para Lync Server. Para ejecutar esta comprobación mediante una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre de la cuenta y la contraseña. Después, debes incluir ese objeto de credenciales y la dirección SIP asignada a la cuenta cuando el sistema llame test-CsClientAuth:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si el usuario especificado puede iniciar sesión en Lync Server con un certificado de cliente, recibirá una salida similar a la siguiente y la propiedad result se marcará como **correcta:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:06.8630376

:

Diagnóstico

Si el usuario especificado no puede iniciar sesión, el resultado se mostrará como error y se registrará información adicional en las propiedades de diagnóstico y errores:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:03.3645259

Error: no se pudo descargar un certificado CS para el usuario dado. Comprobar si

el URI y las credenciales proporcionados son correctos.

Diagnóstico

Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque no se encontró un certificado de cliente válido para el usuario especificado. Puede devolver una lista de los certificados de cliente emitidos para un usuario ejecutando un comando de la siguiente manera:

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

Si prueba-CsClientAuth da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

Cuando se incluye el parámetro detallado, test-CsClientAuth devolverá una cuenta paso a paso de cada acción que se probó cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo:

Intentando descargar un certificado CS para el usuario: kenmyer@litwareinc.com Endpoint: STEpid

Dirección URL del servicio Web:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

No se pudo descargar un certificado CS del servicio Web.

Si

\-La dirección URL del servicio web es válida y los servicios web son funcionales

\-Si usas PhoneNo\\\\PIN para autenticar, asegúrate de que coincidan con el URI de usuario.

\-Si usa NTLM\\Kerberos auth, asegúrese de que ha proporcionado credenciales válidas

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsClientAuth podría fallar:

  - Ha especificado una cuenta de usuario que no es válida. Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

  - Es posible que el usuario de prueba no tenga un certificado de cliente válido. Puede devolver información acerca de los certificados de cliente asignados a un usuario mediante un comando similar a este:
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

