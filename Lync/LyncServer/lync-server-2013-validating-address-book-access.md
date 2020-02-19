---
title: 'Lync Server 2013: validar el acceso a la libreta de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02747101523351823b8abfb85a58691323262ece
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42115173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a>Validar el acceso a la libreta de direcciones en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsAddressBookService. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsAddressBookService proporciona una manera de comprobar que un usuario puede conectarse al servicio Web de descarga de la libreta de direcciones. Cuando se ejecuta el cmdlet, test-CsAddressBookService se conecta al servicio Web de descarga de la libreta de direcciones en el grupo de servidores especificado y solicita la ubicación de los archivos de la libreta de direcciones. Si el servicio Web de descarga de la libreta de direcciones proporciona esa ubicación, se considerará que la prueba se ha realizado correctamente. Si se deniega la petición, el resultado de la prueba es erróneo.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsAddressBookService se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que se haya habilitado para Lync Server. Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el nombre de dominio completo (FQDN) del grupo de Lync Server que se está probando. Por ejemplo:

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación con una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre y la contraseña de la cuenta. A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta al llamar a test-CsAddressBookService:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si el usuario especificado puede conectarse al servicio de libreta de direcciones, obtendrá una salida similar a la siguiente, con la propiedad result marcada como **correcta**:

TargetUrihttps://lync-se.fabrikam.com:443/abs/handler

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:06.2260399

Error

Diagnóstico

Si el usuario especificado no puede realizar esta conexión, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnóstico:

TargetUri

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com

Razón = URI de destino no habilitado para SIP o no

haber.

Microsoft. RTC. Signaling. DiagnosticHeader

Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque el usuario especificado (es decir, el "URI de destino") no existe o no se ha habilitado para Lync Server. Puede comprobar si una cuenta de usuario es válida y comprobar que ha proporcionado la dirección SIP correcta, mediante la ejecución de un comando como este:

Get-CsUser-Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Si test-CsAddressBookService produce un error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:

Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-verbose

Cuando se incluye el parámetro verbose test-CsAddressBookService devolverá una cuenta paso a paso de cada acción que intentó realizar la comprobación de la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo, este resultado de ejemplo muestra que test-CsAddressBookService, al menos en este ejemplo, pudo descargar el archivo de la libreta de direcciones:

Envío de la solicitud HTTP GET.

Ruta de acceso de archivo =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

Número de intento = 1

Tiempo de espera (MS) = 60000

El archivo ABS se descargó correctamentehttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsAddressBookService podría fallar:

  - Ha especificado una cuenta de usuario no válida. Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario se ha habilitado para Lync Server, ejecute un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

</div>

<div>

## <a name="see-also"></a>Vea también


[Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

