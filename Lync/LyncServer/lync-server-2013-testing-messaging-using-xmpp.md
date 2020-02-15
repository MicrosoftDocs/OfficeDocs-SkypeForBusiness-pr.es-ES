---
title: 'Lync Server 2013: probar la mensajería mediante XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94841a3ec17878258b26fd945aa60123ac76a9c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>Probar la mensajería con XMPP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-11-03_


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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsXmppIM</strong> . Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El protocolo de presencia y mensajería extensible (XMPP) es un protocolo de comunicaciones estándar (basado en XML) que se usa para enviar mensajes a través de Internet. XMPP se llamaba originalmente Jabber y es compatible con varias aplicaciones de mensajería y comunicaciones de Internet, como Google Talk y Facebook Chat. El cmdlet **Test-CsXmppIM** comprueba que un usuario puede intercambiar mensajes instantáneos con un usuario en una red XMPP. Tenga en cuenta que, para que esta prueba se realice correctamente, debe tener una dirección SIP válida para el usuario XMPP y que la dirección SIP deba estar en una red configurada como asociado de XMPP permitido.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

En el siguiente ejemplo se comprueba la funcionalidad de mensajería instantánea XMPP para el grupo atl-cs-001.litwareinc.com. Este comando funcionará solo si los usuarios de prueba están definidos para el grupo atl-cs-001.litwareinc.com. Si lo tienen, el comando determinará si el primer usuario de prueba puede enviar un mensaje instantáneo XMPP a un usuario que tiene la dirección SIP adelaney@contoso.com.

Si no se definen los usuarios de prueba, se producirá un error en el comando porque no sabrá en qué usuario se inicia sesión. Si no ha definido usuarios de prueba para un grupo de servidores, debe incluir el parámetro UserSipAddress y las credenciales del usuario que el comando debe usar al intentar iniciar sesión.

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

Los comandos que se muestran en el siguiente ejemplo prueban la capacidad de un usuario\\específico (litwareinc Pilar) para iniciar sesión para enviar un mensaje instantáneo XMPP al usuario adelaney@contoso.com. Para ello, el primer comando del ejemplo usa el cmdlet Get-Credential para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman. (Como el nombre de inicio\\de sesión litwareinc Pilar se incluyó como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta Pilar Ackerman). El objeto Credential resultante se almacena en una variable llamada $cred 1.

A continuación, el segundo comando comprueba si el usuario puede iniciar sesión en el grupo atl-cs-001.litwareinc.com y enviar el mensaje instantáneo XMPP. Para ejecutar esta tarea, se llama al cmdlet **Test-CsXmppIm** , junto con cuatro parámetros: TargetFqdn (el FQDN del grupo de registrador); Receiver (la dirección SIP del usuario al que se dirige el mensaje); UserCredential (el objeto de Windows PowerShell que contiene las credenciales de usuario de Pilar Ackerman); y UserSipAddress (la dirección SIP que corresponde a las credenciales de usuario suministradas).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si la mensajería instantánea XMPP está configurada correctamente, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta:**

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:02.5361946

Mensaje de error:

Diagnóstico

Si los usuarios especificados no pueden usar la mensajería instantánea XMPP, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades error y diagnóstico:

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

Estas son algunas de las razones comunes por las que **Test-CsXmppIM** podría fallar:

  - Se ha suministrado un valor de parámetro incorrecto. Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba. Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.

  - Este comando producirá un error si la configuración de la puerta de enlace XMPP no se ha configurado correctamente o no se ha implementado todavía.

</div>

<div>

## <a name="see-also"></a>Vea también


[Set-CsXmppGatewayConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

