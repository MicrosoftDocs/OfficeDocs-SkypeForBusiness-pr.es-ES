---
title: 'Lync Server 2013: capacidad de probar la conexión a un dominio federado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f18a8c703b085fe559b3a979ac72d9c0b0dfe38f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Capacidad de prueba para conectarse a un dominio federado desde Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsFederatedPartner. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Prueba-CsFederatedPartner comprueba su capacidad de conectar con el dominio de un socio federado. Para comprobar la conectividad a un dominio, ese dominio debe aparecer en la colección de dominios permitidos (federados). Puede recuperar una lista de los dominios en la lista de dominios permitidos con este comando:

    Get-CsAllowedDomain

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-FederatedPartner requiere dos datos: el FQDN de su servidor perimetral y el FQDN del socio federado. Por ejemplo, este comando prueba la capacidad de conectar con el dominio contoso.com:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

Este comando le permite probar las conexiones a todos los dominios que se encuentran en la lista de dominios permitidos:

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si se puede contactar con el dominio especificado, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:00

:

Diagnóstico

Si no se puede contactar con el dominio especificado, el resultado se mostrará como erróneo y la información adicional se registrará en las propiedades de diagnóstico y errores:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: 504, tiempo de espera del servidor

Diagnosis: ErrorCode = 2, Source = ATL-CS-001. litwareinc. com, razón = ver

código de respuesta y frase de motivo.

Microsoft. RTC. Signaling. DiagnosticHeader

Por ejemplo, la salida anterior indica que no se pudo realizar la prueba debido a un error de tiempo de espera del servidor. Normalmente, esto indica problemas de conectividad de red o problemas para ponerse en contacto con el servidor perimetral.

Si prueba-CsFederatedPartner da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsFederatedPartner podría fallar:

  - Es posible que el servidor perimetral no esté disponible. Puede usar los FQDN de los servidores perimetrales con este comando:
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    Después, puede hacer ping a cada servidor perimetral para comprobar que se puede tener acceso a él a través de la red. Por ejemplo:
    
        ping atl-edge-001.litwareinc.com

  - Es posible que el dominio especificado no aparezca en la lista de dominios permitidos. Para comprobar los dominios que se han agregado a la lista de dominios permitidos, use este comando:
    
        Get-CsAllowedDomain
    
    Si desea ver una lista de los dominios con los que los usuarios no pueden comunicarse, use este comando:
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

