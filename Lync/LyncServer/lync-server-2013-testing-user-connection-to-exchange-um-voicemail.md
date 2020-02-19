---
title: 'Lync Server 2013: prueba de la conexión del usuario al correo de voz de mensajería unificada de Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa3ad3f51d1342ac99d3c58be66931ba0770bf6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a>Prueba de la conexión del usuario al correo de voz de mensajería unificada de Exchange en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-11-01_


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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsExUMVoiceMail</strong> . Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet **Test-CsExUMVoiceMail** permite a los administradores comprobar que un usuario puede tener acceso y usar el servicio de mensajería unificada de Microsoft Exchange Server 2013. Para ello, el cmdlet se conecta al servicio de mensajería unificado y deja un correo de voz en el buzón especificado. Este puede ser un correo de voz proporcionado por el sistema o un archivo .WAV personalizado que haya grabado.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

En el siguiente ejemplo se comprueba la Conectividad del correo de voz de mensajería unificada de Exchange para el grupo atl-cs-001.litwareinc.com. Este comando solo funcionará si se definieron usuarios de prueba para el grupo atl-cs-001.litwareinc.com. Si lo tienen, el comando determinará si el primer usuario de prueba puede usar el correo de voz de mensajería unificada. Si no se han configurado los usuarios de prueba para el grupo, se producirá un error en el comando.

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

Los comandos que aparecen en el siguiente ejemplo prueban la Conectividad del correo de voz de mensajería\\unificada de Exchange para el usuario litwareinc kenmyer. Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credenciales de interfaz de línea de comandos de Windows PowerShell para\\el usuario litwareinc kenmyer. Tenga en cuenta que debe proporcionar la contraseña de esta cuenta para crear un objeto de credenciales válido y para asegurarse de que el cmdlet **Test-CsExUMVoiceMail** puede ejecutar su comprobación.

El segundo comando del ejemplo usa el objeto de credenciales proporcionado ($x) y la dirección SIP del usuario litwareinc\\kenmyer para determinar si o este usuario puede conectarse al correo de voz de mensajería unificada de Exchange.

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

El comando que se muestra en el ejemplo siguiente es una variación del comando que se muestra en el ejemplo 1; en este caso, el parámetro OutLoggerVariable se incluye para generar un registro detallado de cada paso realizado por la **prueba-CsExUMVoiceMail** cmdletand el éxito o error de cada uno de estos pasos. Para ello, se agrega el parámetro OutLoggerVariable junto con el valor del parámetro ExumText; Esto provoca que la información de registro detallada se almacene en una variable llamada $ExumTest. En el comando final del ejemplo, el método ToXML() se utiliza para convertir la información de registro en formato XML. A continuación, los datos XML se escriben en un archivo denominado C\\:\\registra VoicemailTest. XML mediante el cmdlet out-File.

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si la integración de Exchange está correctamente configurada, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta**:

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:02.9911345

Mensaje de error:

Diagnóstico

Si el usuario especificado no puede conectarse al correo de voz, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades error y diagnóstico:

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

Estas son algunas de las razones comunes por las que **Test-CsExUMVoiceMail** podría fallar:

  - Se ha suministrado un valor de parámetro incorrecto. Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba. Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.

  - Este comando producirá un error si el servidor de Exchange está mal configurado o no se ha implementado todavía.

</div>

<div>

## <a name="see-also"></a>Vea también


[Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

