---
title: 'Lync Server 2013: prueba de la configuración del servidor LIS'
description: 'Lync Server 2013: prueba de la configuración del servidor LIS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba4d16d2ce48e3e5bb89e863f02902d05ce77bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560616"
---
# <a name="testing-lis-server-configuration-in-lync-server-2013"></a>Prueba de la configuración del servidor LIS en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsLisConfiguration. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet Test-CsLisConfiguration comprueba su capacidad para ponerse en contacto con el servicio Web de LIS. Si se puede contactar con el servicio Web, la prueba se considerará un éxito, independientemente de si se encuentra alguna ubicación específica.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet Test-CsLisConfguration se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que esté habilitado para Lync Server. Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando. Por ejemplo:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación con una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre y la contraseña de la cuenta. A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta al llamar a test-CsLisConfiguration:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si el LIS está configurado correctamente, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta:**

TargetUri https://atl-cs-001.litwareinc.com:443/locationinformation/

liservice. SVC

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:06.1616913

Error

Diagnóstico

Si el usuario especificado no puede iniciar o cerrar sesión, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:

TargetUri

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: 11004, el nombre solicitado es válido pero no hay datos de la solicitud

se encontró el tipo

Diagnóstico

Test-CsLisConfiguration: no se encontró ningún clúster que coincida en la topología.

Por ejemplo, la salida anterior incluye la nota "no se encontró ningún clúster que coincida en la topología". Esto suele indicar un problema con el servidor perimetral: el LIS que usa el servidor perimetral para conectarse al proveedor de servicios y validar las direcciones.

Si Test-CsLisConfiguration da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Cuando se incluye el parámetro verbose, Test-CsLisConfiguration devolverá una cuenta paso a paso por cada acción que se intentó realizar cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo:

Servicio de información de ubicación de llamadas.

Ruta de acceso al servicio = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc

Subnet =

BssId = 5

ChassisId =

PortId =

PortIdSubType = tipo no definido

Mac

Error en la solicitud de servicio Web de información de ubicación de la excepción con un código de respuesta Item400. se produjeron durante la ejecución del flujo de trabajo Microsoft. RTC. SyntheticTrsnactions. workflows. STLisConfigurationWorkflow.

Si examina atentamente la salida anterior, verá que el cmdlet produjo un error después de intentar llamar al servicio de información de ubicación. Uno de los parámetros usados en la llamada fue el siguiente:

BssId = 5

No es un valor válido para el identificador de conjunto de servicios (BssID) básico. En su lugar, un BssID debe tener un aspecto similar a este:

12-34-56-78-90-AB

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que Test-CsLisConfiguration podría producir un error:

  - Se ha suministrado un valor de parámetro incorrecto. Como se muestra en el ejemplo anterior, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba. Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

