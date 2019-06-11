---
title: 'Lync Server 2013: instrucciones especiales de configuración para transacciones sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8c2f0f45aa2187f1b47f8dfa81b3ba121388f6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Instrucciones especiales de configuración para transacciones sintéticas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-11-16_

La mayoría de las transacciones sintéticas se pueden ejecutar en un nodo de monitor tal cual; es decir, tan pronto como se haya agregado la transacción sintética a los ajustes de configuración del nodo del monitor, el nodo de monitor puede empezar a usar la transacción sintética durante la prueba. Sin embargo, esto no es cierto para todas las transacciones sintéticas. Las excepciones (transacciones sintéticas que requieren instrucciones especiales de configuración) se tratan en las secciones siguientes.

<div>

## <a name="dealing-with-server-timeout-errors"></a>Tratar los errores de tiempo de espera del servidor

En algunos casos, es posible que se produzcan errores en las transacciones sintéticas con errores de tiempo de espera del servidor (código de error 504). Estos errores suelen deberse a problemas de Firewall. Cuando se ejecuta una transacción sintética, esa transacción se ejecuta bajo el proceso de MonitoringHost. exe; a su vez, MonitoringHost. exe inicia una instancia del proceso PowerShell. exe. Si el Firewall bloquea MonitoringHost. exe o PowerShell. exe, se producirá un error en la transacción sintética y se generará un error 504.

Para resolver este problema, debe crear manualmente reglas de Firewall entrantes para MonitoringHost. exe y PowerShell. exe en la máquina local. Esto puede hacerse a través del firewall de Windows o de un software de Firewall local de terceros, en función de la configuración preexistente de su servidor.

Si está usando un dispositivo de Firewall de red entre la máquina del host de transacciones sintéticas y los servidores de Lync que está tratando de supervisar, debe tratar el host como un equipo cliente y, a Observer, todos los requisitos del puerto de Firewall de los [puertos y protocolos para los servidores internos en Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>Transacciones sintéticas de conferencias de datos

Si el equipo del nodo de observador se encuentra fuera de la red perimetral, es posible que no pueda ejecutar la transacción sintética de la Conferencia de datos, a menos que primero deshabilite la configuración de proxy de Internet Explorer para la cuenta de servicio de red. Para deshabilitar la configuración de proxy para este servicio, realice el siguiente procedimiento:

1.  En el equipo del nodo de monitor, haga clic en **Inicio**, haga clic en **todos los programas**, en **accesorios**, en **símbolo del sistema**y luego en **Ejecutar como administrador**.

2.  En la ventana de consola, escriba el siguiente comando y, a continuación, presione ENTRAR:
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

Aparecerá el siguiente mensaje en la ventana de comandos:

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

Este mensaje significa que ha deshabilitado la configuración de proxy de Internet Explorer para la cuenta de servicio de red.

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Transacciones sintéticas de mensajería unificada de Exchange

La transacción sintética de Mensajería unificada de Exchange (UM) comprueba que los usuarios de prueba se pueden conectar a las cuentas de correo de voz hospedadas en Exchange. Estos usuarios de prueba deberán preconfigurarse con cuentas de buzón de voz para poder usar las pruebas de mensajería unificada de Exchange.

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>Transacciones sintéticas de chat persistente

Para usar la transacción sintética de chat persistente, primero debe crear un canal y conceder permisos a los usuarios de prueba para que lo usen. El cmdlet [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) se puede usar para configurar correctamente los usuarios de prueba:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

Esta tarea de configuración debe ejecutarse desde dentro de la empresa:

  - Si se ejecuta desde un equipo que no es servidor, el usuario que ejecuta el cmdlet debe ser miembro del rol PersistentChatAdministrators para el control de acceso basado en roles (RBAC).

  - Si se ejecuta desde el propio servidor, el usuario que ejecuta el cmdlet debe ser miembro del grupo RTCUniversalServerAdmins.

En el comando anterior, se incluyó el parámetro de configuración y se establece en true ($True). Si incluye el parámetro de configuración, test-CsPersistentChatMessage creará un salón de chat especial y rellenará ese salón con los usuarios de prueba. Esto ayuda a garantizar que realmente haya un salón de chat disponible para realizar pruebas. Tenga en cuenta que el parámetro de configuración debe ejecutarse solo desde un servidor front-end.

El salón de chat creado por test-CsPersistentChatMessage solo puede ser eliminado por un administrador.

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>Transacciones sintéticas de llamadas de punto a punto RTC

La transacción sintética [de prueba CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) verifica la capacidad de realizar y recibir llamadas a través de la red de telefonía pública conmutada (RTC).

Para ejecutar esta transacción sintética, los administradores deben configurar:

  - Dos usuarios de prueba (un autor de llamada y un destinatario) habilitados para telefonía IP empresarial.

  - Números de llamada directa a la extensión (DID) de cada cuenta de usuario.

  - Directivas de voz y rutas de voz que habilitan las llamadas al número del destinatario para que lleguen a la puerta de enlace PSTN.

  - Una puerta de enlace RTC que acepta llamadas y medios que enrutan las llamadas al grupo de servidores principales de un destinatario según el número marcado.

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>Transacciones sintéticas del almacén de contactos unificado

La transacción sintética de tienda de contactos unificada comprueba que Lync Server 2013 puede recuperar contactos en nombre de un usuario de Microsoft Exchange Server 2013.

Para ejecutar esta transacción, se deben cumplir las siguientes condiciones:

  - La [Administración de la autenticación de servidor a servidor (OAuth) y de las aplicaciones de socio en Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) debe estar configurada entre lync Server 2013 y Exchange 2013.

  - Los usuarios de prueba deben tener un buzón de Exchange 2013 válido.

Una vez satisfechas estas condiciones, los administradores pueden ejecutar el siguiente comando para comprobar que el usuario con la dirección SIP kenmyer@litwareinc.com puede recuperar sus contactos del almacén de contactos unificado:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

Observe el uso del parámetro de configuración utilizado en el comando anterior. Si el parámetro de configuración se incluye al ejecutar test-CsUnifiedContactStore, los contactos del usuario especificado (en este caso, sip:kenmyer@litwareinc.com) se moverán al almacén de contactos unificado. (Por supuesto, si los contactos del usuario ya están en el almacén de contactos unificado, no es necesario moverlos). El parámetro de configuración se usa normalmente solo una vez (la primera prueba-CsUnifiedContactStore se ejecuta) y solo se debe usar con usuarios de prueba; es decir, con cuentas de usuario que nunca iniciarán sesión realmente en Lync Server. Una vez que se ha migrado el usuario de prueba al almacén de contactos unificado, puede comprobar que los contactos del usuario se pueden recuperar mediante una llamada a test-CsUnifiedContactStore sin el parámetro de configuración:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>Transacciones sintéticas XMPP

La transacción de correo instantáneo XMPP (Protocolo de presencia y mensajería extensible) requiere que la característica XMPP se configure con uno o más dominios federados.

Para habilitar la transacción sintética de XMPP, se debe proporcionar un parámetro XmppTestReceiverMailAddress con una cuenta de usuario en un dominio XMPP enrutable. Por ejemplo:

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

En este ejemplo, tendrá que existir una regla de Lync Server 2013 para enrutar mensajes para litwareinc.com a una puerta de enlace XMPP.

</div>

</div>

<span> </span>

</div>

</div>

</div>

