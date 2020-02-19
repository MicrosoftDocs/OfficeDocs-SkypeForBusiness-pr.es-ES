---
title: 'Lync Server 2013: probar el acceso al almacén de contactos unificado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6022d7651a99c2165961ed8cb8852048c10779ff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>Probar el acceso al almacén de contactos unificado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-05-15_


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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsUnifiedContactStore</strong> . Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El almacén de contactos unificados que se presenta en Lync Server 2013 ofrece a los administradores la opción de almacenar los contactos de un usuario en Microsoft Exchange Server 2013 en lugar de en Lync Server. Esto permite al usuario tener acceso al mismo conjunto de contactos de Outlook Web Access, además de Lync 2013. (O bien, puede seguir almacenando contactos en Lync Server. En ese caso, los usuarios tendrán que mantener dos conjuntos de contactos distintos: uno para usar con Outlook y Outlook Web Access, y otro para usarlo con Lync 2013.

Puede determinar si los contactos de un usuario se movieron o no al almacén de contactos unificado ejecutando el cmdlet **Test-CsUnifiedContactStore** . El cmdlet **Test-CsUnifiedContactStore** tomará la cuenta de usuario especificada, se conectará al almacén de contactos unificado e intentará recuperar un contacto para el usuario. Si no se pueden recuperar contactos, el comando producirá un error junto con el mensaje "no se recibió ningún contacto para el usuario. Verifique que los contactos existan para el usuario".

Tenga en cuenta que se producirá un error en el cmdlet **Test-CsUnifiedContactStore** si el usuario se migró correctamente al almacén de contactos unificados, pero no tiene contactos en su lista de contactos. El usuario especificado debe tener al menos un contacto para que el cmdlet **Test-CsUnifiedContactStore** se complete correctamente.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Los comandos que se muestran en el siguiente ejemplo determinan si se\\pueden encontrar los contactos del usuario litwareinc kenmyer en el almacén de contactos unificados. Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credenciales de interfaz de línea de comandos de Windows PowerShell para\\el usuario litwareinc kenmyer. Tenga en cuenta que debe proporcionar la contraseña de esta cuenta para crear un objeto de credenciales válido y asegurarse de que el cmdlet **Test-CsUnifiedContactStore** puede ejecutar su comprobación.

El segundo comando del ejemplo usa el objeto de credenciales proporcionado ($x) y la dirección SIP del usuario litwareinc\\kenmyer para determinar si se pueden encontrar sus contactos en el almacén de contactos unificados.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si el acceso al almacén de contactos está configurado correctamente, recibirá un resultado similar a este, con la propiedad result marcada como **correcta:**

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:14.9862716

Mensaje de error:

Diagnóstico

Si el acceso al almacén de contactos no está configurado correctamente, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades error y diagnóstico:

ADVERTENCIA: no se pudo leer el número de puerto del registrador para el certificado completo

nombre de dominio (FQDN). Se usará el número de puerto del registrador predeterminado. Excepción

System. InvalidOperationException: no se encontró ningún clúster que coincida en la topología.

Veamos

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Mensaje de error: 10060, se ha producido un error en el intento de conexión porque la entidad conectada

no respondió correctamente después de un período de tiempo o

error en la conexión establecida porque el host conectado tiene

no se pudo responder 10.188.116.96:5061

Excepción interna: error en el intento de conexión porque el

la parte conectada no respondió correctamente después de un período de

tiempo o error de conexión establecida debido a que el host conectado

Error al responder 10.188.116.96:5061

Diagnóstico

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsUnifiedContactStore** podría fallar:

  - Se ha suministrado un valor de parámetro incorrecto. Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba. Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.

  - No se pudo conectar con el almacén de contactos unificados y no fue posible intentar recuperar un contacto para el usuario. Es posible que haya problemas de conectividad de red.

</div>

<div>

## <a name="see-also"></a>Vea también


[New-CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[Set-CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

