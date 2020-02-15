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
ms.openlocfilehash: a48580561a1a070b44b202e5d49c89261518dafe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42017851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a>Probar el acceso a la aplicación web en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsWebApp. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsWebApp comprueba que los usuarios autenticados pueden unirse a conferencias de Lync Server mediante Lync Web App. Cuando se ejecuta el cmdlet, test-CsWebApp se pone en contacto con el servicio de vales web para obtener vales web para los usuarios especificados. Estos vales actúan efectivamente como "vales de admisión" para la Conferencia de Lync Server. Si se pueden recuperar los vales y, si los usuarios se pueden autenticar, test-CsWebApp se pondrá en contacto con Lync Server e intentará establecer conferencias independientes para la mensajería instantánea, el uso compartido de aplicaciones y la colaboración de datos.

Tenga en cuenta que test-CsWebApp solo comprueba las API y las conexiones usadas para crear estas conferencias. El cmdlet está diseñado para comprobar que Lync Web App puede usarse para crear conferencias y unirse a ellas. Sin embargo, en realidad no crea y lleva a cabo una conferencia.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsWebApp se puede ejecutar usando tanto un par de cuentas de prueba preconfiguradas como las cuentas de dos usuarios que están habilitados para Lync Server. Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el nombre de dominio completo del grupo de Lync Server que se está probando. Por ejemplo:

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta. A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsWebApp:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) . Tenga en cuenta que test-CsWebApp quedó obsoleto para su uso en Lync Server 2013.

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si test-CsWebApp puede unir a los usuarios a sus conferencias, el cmdlet devolverá el resultado de la prueba correcto:

FQDN de destino:

Resultado: correcto

Latencia: 00:00:00

Mensaje de error:

Diagnóstico

Si los usuarios no pueden unirse a las conferencias necesarias, el resultado de la prueba se marcará como error. Por lo general, test-CsWebApp también devolverá un mensaje de error detallado y diagnóstico:

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Mensaje de error: no se recibió ninguna respuesta para el servicio de vales Web

Diagnóstico: la solicitud HTTP no está autorizada con el cliente

esquema de autenticación ' NTLM '. La autenticación

el encabezado recibido del servidor era ' Negotiate, NTLM '.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Los errores de test-CsWebApp suelen implicar errores de autenticación de usuario. Si test-CsWebApp produce un error, primero debe comprobar que los usuarios especificados tengan cuentas de usuario válidas y que estén habilitados para Lync Server. Puede recuperar la información de la cuenta con un comando similar al siguiente:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Si la propiedad Enabled no es igual a true o si se produce un error en el comando, significa que el usuario no tiene una cuenta de Lync Server válida. También debe comprobar que las contraseñas que proporcionó al cmdlet son válidas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

