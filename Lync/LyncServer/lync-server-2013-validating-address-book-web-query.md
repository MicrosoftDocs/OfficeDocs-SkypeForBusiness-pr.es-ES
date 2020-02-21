---
title: 'Lync Server 2013: validación de la consulta Web de la libreta de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 548ec62a56de829955647a696e33578b9ab3dfd8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a>Validación de la consulta Web de la libreta de direcciones en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsAddressBookWebQuery. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsAddressBookWebQuery permite a los administradores comprobar que los usuarios pueden usar el servicio de consulta Web de libreta de direcciones para buscar un contacto específico. Al ejecutar el cmdlet, test-CsAddressBookWebQuery se conectará primero al servicio de vale web para autenticarse. Si la autenticación se realiza correctamente, el cmdlet se conectará al servicio de consulta Web de la libreta de direcciones y buscará el contacto especificado. Si se encuentra ese contacto, el cmdlet intentará devolver esa información al equipo local. La prueba se marcará como correcta solo si se pueden completar todos los pasos.

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsAddressBookWebQuery se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que esté habilitado para Lync Server. Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server y la dirección SIP del usuario que actúa como destino de la búsqueda. Por ejemplo:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

Para ejecutar esta comprobación con una cuenta de usuario real, debe crear un objeto de credenciales de Windows PowerShell que contenga un nombre de usuario y una contraseña válidos. A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta cuando el código llame a test-CsAddressBookWebQuery:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si el usuario especificado puede conectarse al servicio de libreta de direcciones y recuperar la dirección del usuario de destino, se devuelve un resultado similar al siguiente con la propiedad result marcada como correcta:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:06.2611356

Error

Diagnóstico

Si el usuario especificado no se puede conectar o si no se puede recuperar la dirección de usuario de destino, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: error en la solicitud del servicio Web de libreta de direcciones con código de respuesta

NoEntryFound.

Diagnóstico

La salida anterior indica que se produjo un error en la prueba porque no se encontró el usuario de destino. Puede determinar si se ha pasado una dirección SIP válida a test-CsAddressBookWebQuery mediante la ejecución de un comando similar al siguiente:

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

Si test-CsAddressBookWebQuery produce un error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

Cuando se incluye el parámetro verbose, test-CsAddressBookWebQuery devolverá una cuenta paso a paso de cada acción que ha probado mientras se comprueba la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo, este resultado indica que test-CsAddressBookWebQuery se pudo conectar al servicio de libreta de direcciones, pero no pudo encontrar la dirección SIP de destino:

Se inició la actividad ' QueryAddressBookWebService '.

Llamar al servicio de consulta Web de libreta de direcciones. DIRECCIÓN URL DE ABWS =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

Excepción de consulta de la libreta de direcciones: error en la solicitud de servicio Web de libreta de direcciones con código de respuesta NoEntryFound.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsAddressBookWebQuery podría fallar:

  - Ha especificado una cuenta de usuario no válida. Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario se ha habilitado para Lync Server, ejecute un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

  - Es posible que el usuario de destino no esté en la libreta de direcciones.

  - Es posible que la libreta de direcciones no se haya actualizado completamente y replicado. Para forzar una actualización de todos los servidores de la libreta de direcciones de la organización, ejecute el siguiente comando:
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

