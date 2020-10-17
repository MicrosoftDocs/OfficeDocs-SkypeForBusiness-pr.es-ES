---
title: 'Lync Server 2013: capacidad de prueba para conectarse a un dominio federado'
description: 'Lync Server 2013: capacidad de prueba para conectarse a un dominio federado.'
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
ms.openlocfilehash: bf1f5bdef66d34b9ca2e39797df0b4ad32d9afde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560826"
---
# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Probar la capacidad de conectarse a un dominio federado desde Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<td><p>Programación de comprobación</p></td>
<td><p>Diario</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsFederatedPartner. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Test-CsFederatedPartner verifica su capacidad de conectarse con el dominio de un socio federado. Para comprobar la conectividad a un dominio, ese dominio debe estar incluido en la colección de dominios permitidos (federado). Puede recuperar una lista de los dominios en la lista de dominios permitidos con este comando:

    Get-CsAllowedDomain

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet Test-FederatedPartner requiere dos datos: el FQDN del servidor perimetral y el FQDN del socio federado. Por ejemplo, este comando comprueba la capacidad de conectarse al dominio contoso.com:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

Este comando le permite probar las conexiones a todos los dominios que se encuentran en la lista de dominios permitidos:

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si se puede establecer contacto con el dominio especificado, recibirá un resultado similar al siguiente con la propiedad result marcada como **correcta:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:00

Error

Diagnóstico

Si no se puede establecer contacto con el dominio especificado, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: 504, tiempo de espera del servidor

Diagnosis: ErrorCode = 2, Source = ATL-CS-001. litwareinc. com, Reason = vea

código de respuesta y frase de motivo.

Microsoft. RTC. Signaling. DiagnosticHeader

Por ejemplo, la salida anterior indica que la prueba produjo un error debido a un error de tiempo de espera del servidor. Normalmente, esto indica problemas de conectividad de red o problemas al contactar con el servidor perimetral.

Si Test-CsFederatedPartner da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que Test-CsFederatedPartner podría producir un error:

  - Es posible que el servidor perimetral no esté disponible. Puede usar este comando para los FQDN de los servidores perimetrales:
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    Después, puede hacer ping a cada servidor perimetral para comprobar que se puede tener acceso a él a través de la red. Por ejemplo:
    
        ping atl-edge-001.litwareinc.com

  - Es posible que el dominio especificado no aparezca en la lista de dominios permitidos. Para comprobar los dominios que se agregaron a la lista de dominios permitidos, use este comando:
    
        Get-CsAllowedDomain
    
    Si quiere ver una lista de dominios con los que los usuarios no se pudieron comunicar, use este comando:
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

