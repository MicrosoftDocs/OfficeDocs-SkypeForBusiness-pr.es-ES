---
title: 'Lync Server 2013: pruebas de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 941f8830689c95fb782ac56594cd1d62785c1e1f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a>Prueba de chat persistente en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsPersistentChatMessage</strong> . Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet **Test-CsPersistentChatMessage** comprueba que un par de usuarios de prueba puedan intercambiar mensajes mediante el servicio de chat persistente. Para ello, el cmdlet registra los dos usuarios en Lync Server 2013, conecta los usuarios a un salón de chat persistente, intercambia un par de mensajes y, a continuación, sale del salón de chat y cierra sesión en los dos usuarios. Tenga en cuenta que se producirá un error en las llamadas a este cmdlet si no ha creado ningún salón de chat o si las dos cuentas de usuario de prueba no tienen asignada una directiva de chat persistente que les dé acceso al servicio de chat persistente.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Los comandos que se muestran en el siguiente ejemplo prueban la capacidad de un par de\\usuarios (litwareinc\\Pilar y litwareinc kenmyer) para iniciar sesión en Lync Server 2013 y, a continuación, intercambiar mensajes con el servicio de chat persistente. Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman. (Como el nombre de inicio de\\sesión, litwareinc pilar, se incluyó como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta Pilar Ackerman). A continuación, el objeto de credenciales resultante se almacena en una variable llamada $cred 1. El segundo comando realiza la misma acción pero, esta vez, devuelve un objeto de credenciales de la cuenta de Ken Myer.

Con los objetos de credenciales a mano, el tercer comando determina si estos dos usuarios pueden iniciar sesión en Lync Server 2013 y intercambiar mensajes con el chat persistente. Para realizar esta tarea, se llama al cmdlet **Test-CsPersistentChatMessage** con los parámetros siguientes: TargetFqdn (el FQDN del grupo de registrador); SenderSipAddress (la dirección SIP del primer usuario de prueba); SenderCredential (el objeto de Windows PowerShell que contiene las credenciales para este mismo usuario); ReceiverSipAddress (la dirección SIP del otro usuario de prueba); y ReceiverCredential (el objeto de Windows PowerShell que contiene las credenciales del otro usuario de prueba).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si el usuario especificado tiene una directiva de ubicación válida, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta**:

FQDN de destino: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:00

Mensaje de error:

Diagnóstico

Si los usuarios especificados no pueden intercambiar mensajes mediante el servicio de chat persistente, el resultado se mostrará como **error**y se registrará información adicional en las propiedades error y diagnóstico:

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

no se pudo \[responder 2001:4898: E8: f39e: 5c9a: ad83:81b3:\]9944:5061

Excepción interna: error en el intento de conexión porque el

la parte conectada no respondió correctamente después de un período de

tiempo o error de conexión establecida debido a que el host conectado

no respondió

\[2001:4898: E8: f39e: 5c9a: ad83:81b3:9944\]: 5061

Diagnóstico

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsPersistentChatMessage** podría fallar:

  - Se ha suministrado un valor de parámetro incorrecto. Es posible que las cuentas de prueba necesarias no existan o se hayan creado correctamente.

  - Es posible que haya un problema de red que ocasionó un retraso inesperado que agotó el tiempo de espera de la prueba.

</div>

<div>

## <a name="see-also"></a>Vea también


[Grant-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[New-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[Set-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

