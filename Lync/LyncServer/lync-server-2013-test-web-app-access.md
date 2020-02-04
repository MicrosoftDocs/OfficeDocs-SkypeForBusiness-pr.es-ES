---
title: 'Lync Server 2013: probar el acceso a la aplicación Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7618bcc9a69d177950bae64354106a67721e822a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a>Probar el acceso a aplicaciones web en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsWebApp. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsWebApp comprueba que los usuarios autenticados pueden unirse a conferencias de Lync Server mediante Lync Web App. Al ejecutar el cmdlet, test-CsWebApp se pone en contacto con el servicio de vales web para obtener vales web para los usuarios especificados. Estos vales actúan de manera eficaz como "vales de admisión" en la Conferencia de Lync Server. Si se pueden recuperar los vales y si los usuarios pueden ser autenticados, test-CsWebApp se pondrá en contacto con Lync Server e intentará establecer conferencias distintas para la mensajería instantánea, el uso compartido de aplicaciones y la colaboración de datos.

Ten en cuenta que prueba-CsWebApp solo verifica las API y las conexiones usadas para crear estas conferencias. El cmdlet está diseñado para comprobar que Lync Web App podría usarse para crear conferencias y unirse a ellas. Sin embargo, en realidad no crea y realiza una conferencia.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsWebApp se puede ejecutar con un par de cuentas de prueba preconfiguradas o con las cuentas de dos usuarios que están habilitados para Lync Server. Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el nombre de dominio completo del grupo de servidores de Lync que se está probando. Por ejemplo:

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contengan el nombre y la contraseña de la cuenta) de cada cuenta. Después, debe incluir esos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsWebApp:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

Para obtener más información, vea el tema de ayuda para el cmdlet [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) . Tenga en cuenta que test-CsWebApp quedó obsoleto para usarse en Lync Server 2013.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si test-CsWebApp puede unir a los usuarios a sus conferencias, el cmdlet devolverá el resultado de la prueba correcta:

FQDN de destino:

Resultado: éxito

Latencia: 00:00:00

Mensaje de error:

Diagnóstico

Si los usuarios no pueden unirse a las conferencias necesarias, el resultado de la prueba se marcará como erróneo. Por lo general, test-CsWebApp también devolverá un mensaje de error y diagnóstico detallado:

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Mensaje de error: no se recibió respuesta para el servicio de vales Web

Diagnóstico: la solicitud HTTP no está autorizada con el cliente

esquema de autenticación ' NTLM '. La autenticación

el encabezado recibido del servidor era ' Negotiate, NTLM '.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Los errores de prueba-CsWebApp suelen incluir errores de autenticación de usuario. Si prueba-CsWebApp da error, primero debe comprobar que los usuarios especificados tienen cuentas de usuario válidas y que están habilitados para Lync Server. Puede recuperar información de la cuenta mediante un comando similar a este:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Si la propiedad Enabled no es igual a true o si se produce un error en el comando, significa que el usuario no tiene una cuenta válida de Lync Server. También debe comprobar que las contraseñas proporcionadas al cmdlet son válidas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

