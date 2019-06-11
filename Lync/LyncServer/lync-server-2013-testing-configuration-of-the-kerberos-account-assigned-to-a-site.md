---
title: Probar la configuración de la cuenta Kerberos asignada a un sitio
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12a780c4c900423b23eff6cdaae15ba15786b6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>Prueba de la configuración de la cuenta Kerberos asignada a un sitio en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsKerberosAccountAssignment. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsKerberosAccountAssignment le permite comprobar que una cuenta Kerberos está asociada con un sitio determinado, que esta cuenta está configurada correctamente y que la cuenta funciona como se espera. Las cuentas de Kerberos son cuentas de equipo que pueden servir como entidad principal de autenticación para todos los equipos de un sitio que ejecutan Internet Information Server (IIS). Debido a que estas cuentas usan el protocolo de autenticación Kerberos, las cuentas se conocen como cuentas Kerberos y el nuevo proceso de autenticación se conoce como autenticación Web Kerberos. Esto le permite administrar todos los servidores IIS mediante una sola cuenta.

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

De forma predeterminada, prueba-CsKerberosAccountAssignment muestra muy pocos resultados en pantalla. En su lugar, la información devuelta por el cmdlet se escribe en un archivo HTML. Por eso, le recomendamos que incluya el parámetro verbose y el parámetro de informe en cualquier momento que ejecute test-CsKerberosAccountAssignment. El parámetro verbose proporcionará una salida ligeramente más detallada en pantalla mientras se ejecuta el cmdlet. El parámetro de informe le permite especificar una ruta de acceso y un nombre de archivo para el archivo HTML generado por test-CsKerberosAccountAssignment. Si no incluye el parámetro de informe, el archivo HTML se guardará automáticamente en la carpeta usuarios y recibirá un nombre similar a este: ce84964a-c4da-4622-Ad34-c54ff3ed361f. html.

También debe especificar una identidad de sitio al ejecutar test-CsKerberosAccountAssignment. Las cuentas de Kerberos se asignan en el ámbito del sitio.

El siguiente comando ejecuta test-CsKerberosAccountAssignment y guarda el resultado en un archivo denominado C:\\logs\\KerberosTest. html:

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

El cmdlet test-CsKerberosAccountAssignment no devuelve una indicación simple de éxito o error. En su lugar, debe ver el archivo HTML generado usando Internet Explorer.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsKerberosAccountAssignment podría fallar:

  - Es posible que haya especificado una identidad de sitio incorrecta. Para devolver una lista de identidades de sitio válidas, use este comando:
    
        Get-CsSite | Select-Identity Identity
    
    Una identidad de sitio suele tener el siguiente aspecto:
    
    sitio: Redmond

  - Es posible que el sitio especificado no tenga una cuenta de Kerberos asignada. Puede determinar si se asigna o no una cuenta Kerberos a un sitio ejecutando un comando similar a este:
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - Es posible que su cuenta de Kerberos tenga una contraseña que no es válida. Si recibe el siguiente mensaje de error en el informe, es probable que tenga que restablecer la contraseña de la cuenta Kerberos:
    
    InvalidKerberosConfiguration: la configuración de Kerberos no es válida.
    
    InvalidKerberosConfiguration: la configuración de Kerberos en atl-cs001.litwareinc.com no es válida. La cuenta asignada esperada\\es litwareinc kerberostest. Asegúrese de que la cuenta no haya expirado y de que la contraseña configurada en el equipo coincida con la contraseña de Active Directory de la cuenta.
    
    Puede establecer la contraseña con el cmdlet [set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

