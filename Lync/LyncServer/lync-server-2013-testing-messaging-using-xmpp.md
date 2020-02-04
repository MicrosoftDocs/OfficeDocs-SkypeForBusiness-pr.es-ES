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
ms.openlocfilehash: d5a1840e344ee19114cca424822fa1df14028495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsXmppIM</strong> . Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El protocolo de presencia y mensajería extensible (XMPP) es un protocolo de comunicaciones estándar (basado en XML) que se usa para enviar mensajes a través de Internet. XMPP se llamaba originalmente Jabber y es compatible con varias aplicaciones de mensajería y comunicaciones de Internet, como Google Talk y la conversación de Facebook. El cmdlet **Test-CsXmppIM** verifica que un usuario puede intercambiar mensajes instantáneos con un usuario en una red XMPP. Tenga en cuenta que, para que esta prueba se realice correctamente, debe tener una dirección SIP válida para el usuario de XMPP, y esa dirección SIP debe estar en una red que se haya configurado como socio XMPP autorizado.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

En el ejemplo siguiente se comprueban las capacidades de mensajería instantánea de XMPP para el grupo atl-cs-001.litwareinc.com. Este comando solo funciona si se han definido usuarios de prueba para el grupo atl-cs-001.litwareinc.com. De ser así, el comando determinará si el primer usuario de prueba puede enviar un mensaje instantáneo XMPP a un usuario que tenga la dirección SIP adelaney@contoso.com.

Si no se definen los usuarios de prueba, el comando fallará porque no sabrá en qué usuario iniciar sesión. Si no ha definido usuarios de prueba para un grupo, debe incluir el parámetro UserSipAddress y las credenciales del usuario que debe usar el comando al intentar iniciar sesión.

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

Los comandos que se muestran en el siguiente ejemplo prueban la capacidad de un usuario\\específico (litwareinc Pilar) para iniciar sesión y enviar un mensaje instantáneo XMPP a la adelaney@contoso.com de usuario. Para ello, el primer comando del ejemplo usa el cmdlet Get-Credential para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman. (Como el nombre de inicio\\de sesión litwareinc Pilar se incluyó como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta de Pilar Ackerman). El objeto de credencial resultante se almacena en una variable llamada $cred 1.

El segundo comando comprueba si este usuario puede iniciar sesión en el grupo atl-cs-001.litwareinc.com y enviar el mensaje instantáneo XMPP. Para ejecutar esta tarea, se llama al cmdlet **Test-CsXmppIm** , junto con cuatro parámetros: TargetFqdn (el FQDN del grupo de servidores de registrar); Receptor (la dirección SIP del usuario al que se dirige el mensaje); UserCredential (el objeto de Windows PowerShell que contiene las credenciales de usuario de Pilar Ackerman); y UserSipAddress (la dirección SIP que corresponde a las credenciales de usuario suministradas).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si la mensajería instantánea XMPP está configurada correctamente, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:02.5361946

Mensaje de error:

Diagnóstico

Si los usuarios especificados no pueden usar la mensajería instantánea de XMPP, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades de diagnóstico y errores:

ADVERTENCIA: no se pudo leer el número de puerto del registrador para el nombre completo

nombre de dominio (FQDN). Usando el número de puerto predeterminado del registrador. Excepción

System. InvalidOperationException: no se encontró ningún clúster coincidente en la topología.

en

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Mensaje de error: 10060, error al intentar la conexión porque la persona conectada

no respondió correctamente después de un período de tiempo, o

error en la conexión establecida porque el host conectado tiene

Error al responder 10.188.116.96:5061

Excepción interna: error en el intento de conexión porque el

la parte conectada no respondió correctamente después de un período de

hora o error de conexión establecida porque el host conectado

Error al responder 10.188.116.96:5061

Diagnóstico

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsXmppIM** podría fallar:

  - Se proporcionó un valor de parámetro incorrecto. Si se usa, los parámetros opcionales deben estar configurados correctamente o se producirá un error en la prueba. Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.

  - Este comando fallará si la configuración de la puerta de enlace XMPP no se ha configurado correctamente o si aún no se ha implementado.

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

