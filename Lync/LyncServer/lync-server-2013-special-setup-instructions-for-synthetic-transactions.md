---
title: 'Lync Server 2013: instrucciones de configuración especiales para transacciones sintéticas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: defed8a0356d489a628f883b42ae658aadd6442d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Instrucciones de configuración especiales para transacciones sintéticas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-11-16_

La mayoría de las transacciones sintéticas se puede ejecutar en un nodo de monitor tal cual; es decir, en cuanto la transacción se agregue a la configuración del nodo, este podrá utilizarla durante sus fases de prueba. Esto, sin embargo, no es aplicable a todas las transacciones sintéticas. En las siguientes secciones se detallan estas excepciones (transacciones sintéticas que requieren instrucciones especiales de configuración).

<div>

## <a name="dealing-with-server-timeout-errors"></a>Tratar errores de tiempo de espera del servidor

En algunos casos, es posible que las transacciones sintéticas fallen con errores de tiempo de espera del servidor (código de error 504). Estos errores suelen deberse a problemas del firewall. Cuando se ejecuta una transacción sintética, esa transacción se ejecuta en el proceso MonitoringHost. exe; a su vez, MonitoringHost. exe inicia una instancia del proceso PowerShell. exe. Si el Firewall bloquea MonitoringHost. exe o PowerShell. exe, se producirá un error en la transacción sintética y se generará un error 504.

Para resolver este problema, debe crear manualmente reglas de Firewall de entrada para MonitoringHost. exe y PowerShell. exe en el equipo local. Esto puede realizarse a través de Firewall de Windows o de un software de Firewall local de terceros, en función de la configuración preexistente del servidor.

Si va a usar un dispositivo de Firewall de red entre el equipo de host de transacción sintética y los servidores de Lync que está tratando de supervisar, debe tratar el host como un equipo cliente y todos los requisitos de puerto de Firewall de [puertos y protocolos para los servidores internos en Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>Transacciones sintéticas de conferencia de datos

Si el equipo de nodo de monitor está ubicado fuera de la red perimetral, es probable que no pueda ejecutar la transacción sintética de conferencia de datos a menos que primero deshabilite la configuración de proxy de Internet Explorer para la cuenta de servicio de red. Haga lo siguiente para deshabilitarla:

1.  En el equipo nodo de supervisor, haga clic en **Inicio**, **Todos los programas**, **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y haga clic en **Ejecutar como administrador**.

2.  Escriba el siguiente comando en la ventana de la consola y presione ENTRAR:
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

Aparecerá el siguiente mensaje en la ventana Comandos:

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

Este mensaje significa que ha deshabilitado la configuración de proxy de Internet Explorer para la cuenta de servicio de red.

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Transacciones sintéticas de mensajería unificada de Exchange

La transacción sintética de mensajería unificada (UM) de Exchange comprueba que los usuarios de prueba se pueden conectar a cuentas de correo de voz hospedadas en Exchange. Estos usuarios de prueba deben estar configurados previamente con cuentas de correo de voz para poder usar pruebas de mensajería unificada de Exchange.

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>Transacciones sintéticas de chat persistente

Para usar la transacción sintética de chat persistente, los administradores primero deben crear un canal y conceder a los usuarios de prueba permisos para usarlos. El cmdlet [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) se puede usar para configurar correctamente los usuarios de prueba:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

Esta tarea de configuración debe realizarse desde la empresa:

  - Si se realiza en un equipo que no es servidor, el usuario que ejecute el cmdlet debe pertenecer al rol PersistentChatAdministrators de control de acceso basado en roles (RBAC).

  - Si se realiza desde el propio servidor, el usuario que ejecute el cmdlet debe pertenecer al grupo RTCUniversalServerAdmins.

El comando anterior incluía el parámetro Setup establecido en True ($True). Si incluye el parámetro Setup, test-CsPersistentChatMessage creará un salón de chat persistente especial y rellenará ese salón con los usuarios de prueba. Esto sirve para garantizar que existe realmente un salón de chat destinado a realizar pruebas. Tenga en cuenta que el parámetro Setup solo debe ejecutarse desde un servidor front-end.

Solo un administrador puede eliminar el salón de chat que Test-CsPersistentChatMessage crea.

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>Transacciones sintéticas de llamada punto a punto de RTC

La transacción sintética [de test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) comprueba la capacidad de realizar y recibir llamadas a través de la red telefónica conmutada (RTC).

Para ejecutar esta transacción sintética, los administradores deben tener preparado lo siguiente:

  - Dos usuarios de prueba (un autor y un receptor) habilitados para Enterprise Voice.

  - Números de llamada directa a la extensión (DID) de cada cuenta de usuario.

  - Directivas y rutas de voz que permitan efectuar llamadas al número del receptor para llegar a la puerta de enlace RTC.

  - Una puerta de enlace RTC que acepte llamadas, además de medios que enruten llamadas de regreso al grupo de servidores principales de un receptor en función del número marcado.

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>Transacciones sintéticas de almacén de contactos unificados

La transacción sintética de almacén de contactos unificados comprueba que Lync Server 2013 puede recuperar contactos en nombre de un usuario de Microsoft Exchange Server 2013.

Para ejecutar esta transacción, se deben cumplir las siguientes condiciones:

  - La [Administración de la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) debe estar configurada entre lync Server 2013 y Exchange 2013.

  - Los usuarios de prueba deben tener un buzón válido de Exchange 2013.

Si se cumplen, los administradores pueden ejecutar el siguiente comando a fin de constatar que el usuario con la dirección SIP kenmyer@litwareinc.com puede recuperar sus contactos del almacén de contactos unificados:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

Tenga en cuenta el uso del parámetro de configuración usado en el comando anterior. Si se incluye el parámetro setup cuando se ejecuta test-CsUnifiedContactStore, los contactos del usuario especificado (en este caso, sip:kenmyer@litwareinc.com) se moverán al almacén de contactos unificados. (Por supuesto, si los contactos del usuario ya están en el almacén de contactos unificados, no es necesario moverlos). El parámetro Setup se suele usar una sola vez (la primera vez que se ejecuta test-CsUnifiedContactStore) y solo debe usarse con usuarios de prueba; es decir, con las cuentas de usuario que nunca se iniciarán sesión en Lync Server en realidad. Una vez que se ha migrado el usuario de prueba al almacén de contactos unificado, puede comprobar que los contactos del usuario se pueden recuperar llamando a test-CsUnifiedContactStore sin el parámetro Setup:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>Transacciones sintéticas XMPP

La transacción sintética de mensajería instantánea XMPP (protocolo extensible de mensajería y presencia) requiere que la característica XMPP esté configurada con uno o más dominios federados.

Para habilitar la transacción sintética XMPP, se debe incluir un parámetro XmppTestReceiverMailAddress con una cuenta de usuario en un dominio XMPP que pueda enrutarse. Por ejemplo:

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

En este ejemplo, debe existir una regla de Lync Server 2013 para enrutar mensajes para litwareinc.com a una puerta de enlace XMPP.

</div>

</div>

<span> </span>

</div>

</div>

</div>

