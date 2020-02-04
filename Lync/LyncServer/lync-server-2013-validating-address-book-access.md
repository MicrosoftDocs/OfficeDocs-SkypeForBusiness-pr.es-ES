---
title: 'Lync Server 2013: validación del acceso a la libreta de direcciones'
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
ms.openlocfilehash: 96fe45f1491ca518a6985b0c15f8bcc229bd7f8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsAddressBookService. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsAddressBookService le permite comprobar que un usuario puede conectarse al servicio Web de descarga de la libreta de direcciones. Al ejecutar el cmdlet, test-CsAddressBookService se conecta al servicio Web de descarga de la libreta de direcciones en el grupo de servidores especificado y solicita la ubicación de los archivos de la libreta de direcciones. Si el servicio Web de descarga de la libreta de direcciones proporciona esa ubicación, la prueba se considerará satisfactoria. Si la solicitud es denegada, la prueba se considerará un error.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsAddressBookService se puede ejecutar mediante una cuenta de prueba preconfigurada (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o la cuenta de cualquier usuario que se haya habilitado para Lync Server. Para ejecutar esta comprobación mediante una cuenta de prueba, todo lo que tiene que hacer es especificar el nombre de dominio completo (FQDN) del grupo de Lync Server que se está probando. Por ejemplo:

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación mediante una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre de la cuenta y la contraseña. Después, debes incluir ese objeto de credenciales y la dirección SIP asignada a la cuenta al llamar a test-CsAddressBookService:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si el usuario especificado puede conectarse al servicio de libreta de direcciones, obtendrá un resultado similar a este, con la propiedad result marcada como **correcta**:

TargetUrihttps://lync-se.fabrikam.com:443/abs/handler

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:06.2260399

:

Diagnóstico

Si el usuario especificado no puede establecer esta conexión, el resultado se mostrará como error y la información adicional se registrará en las propiedades de error y diagnóstico:

TargetUri

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com,

Motivo = URI de destino no habilitado para SIP o no

condiciones.

Microsoft. RTC. Signaling. DiagnosticHeader

Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque el usuario especificado (es decir, el "URI de destino") no existe o no se ha habilitado para Lync Server. Puede comprobar si una cuenta de usuario es válida, y comprobar si ha suministrado la dirección SIP correcta ejecutando un comando como este:

Get-CsUser-Identity "sip:kenmyer@litwareinc.com" | SipAddress seleccionar-objeto, habilitado

Si prueba-CsAddressBookService da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:

Prueba-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com": detallado

Cuando se incluye el parámetro detallado, test-CsAddressBookService devolverá una cuenta paso a paso de cada acción que se intentó realizar al comprobar la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo, este resultado de ejemplo muestra que test-CsAddressBookService, al menos en este ejemplo, pudo descargar el archivo de la libreta de direcciones:

Envío de solicitud HTTP GET.

Ruta de archivo =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

Número de intento = 1

Tiempo de espera (MS) = 60000

El archivo ABS se ha descargado correctamentehttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsAddressBookService podría fallar:

  - Ha especificado una cuenta de usuario no válida. Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que se ha habilitado una cuenta de usuario para Lync Server, ejecute un comando similar al siguiente:
    
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

