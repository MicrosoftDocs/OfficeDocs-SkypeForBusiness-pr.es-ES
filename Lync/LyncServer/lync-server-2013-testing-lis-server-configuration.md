---
title: 'Lync Server 2013: prueba de la configuración del servidor LIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e5baed37e4c72da8b8348dab9702b5d22fbbc5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lis-server-configuration-in-lync-server-2013"></a>Probar la configuración del servidor LIS en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsLisConfiguration. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsLisConfiguration verifica su capacidad para ponerse en contacto con el servicio Web de LIS. Si se puede contactar con el servicio Web, la prueba se considerará satisfactoria, independientemente de si se puede encontrar algún lugar específico.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsLisConfguration se puede ejecutar mediante una cuenta de prueba preconfigurada (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o la cuenta de cualquier usuario que esté habilitado para Lync Server. Para ejecutar esta comprobación mediante una cuenta de prueba, solo tiene que especificar el FQDN del grupo de servidores de Lync que se está probando. Por ejemplo:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación mediante una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre de la cuenta y la contraseña. Después debes incluir ese objeto de credenciales y la dirección SIP asignada a la cuenta al llamar a test-CsLisConfiguration:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si el LIS está configurado correctamente, recibirá un resultado similar a este, con la propiedad result marcada como **correcta:**

TargetUrihttps://atl-cs-001.litwareinc.com:443/locationinformation/

liservice. SVC

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:06.1616913

:

Diagnóstico

Si el usuario especificado no puede iniciar sesión o cerrar sesión, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:

TargetUri

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: 11004, el nombre solicitado es válido pero no se han especificado datos del

se encontró el tipo

Diagnóstico

Prueba-CsLisConfiguration: no se encontró ningún clúster coincidente en la topología.

Por ejemplo, la salida anterior incluye la nota "no se encontró ningún clúster coincidente en la topología". Esto suele indicar un problema con el servidor perimetral: LIS con el servidor perimetral para conectarse al proveedor de servicios y validar las direcciones.

Si prueba-CsLisConfiguration da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Cuando se incluye el parámetro detallado, test-CsLisConfiguration devolverá una cuenta paso a paso de cada acción que se probó cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo:

Servicio de información de ubicación de llamadas.

Ruta de servicio =https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc

Subnet =

BssId = 5

ChassisId =

PortId =

PortIdSubType = tipo no definido

Mac

Error en la solicitud de servicio Web de información de ubicación de excepción con un código de respuesta de Item400 '. durante el flujo de trabajo, Microsoft. RTC. SyntheticTrsnactions. workflows. STLisConfigurationWorkflow Execution.

Si examina atentamente la salida anterior, verá que el cmdlet falló después de intentar llamar al servicio de información de ubicación. Uno de los parámetros que se usó en la llamada fue este:

BssId = 5

Ese no es un valor válido para el identificador de conjunto de servicios (BssID) básico. En su lugar, un BssID debe tener un aspecto similar a este:

12-34-56-78-90-AB

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsLisConfiguration podría fallar:

  - Se proporcionó un valor de parámetro incorrecto. Tal y como se muestra en el ejemplo anterior, los parámetros opcionales deben estar configurados correctamente o no se puede realizar la prueba. Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

