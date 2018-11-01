---
title: Instrucciones de configuración especiales para transacciones sintéticas
TOCTitle: Instrucciones de configuración especiales para transacciones sintéticas
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49889215
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instrucciones de configuración especiales para transacciones sintéticas

 

_**Última modificación del tema:** 2015-11-16_

La mayoría de las transacciones sintéticas se puede ejecutar en un nodo de monitor tal cual; es decir, en cuanto la transacción se agregue a la configuración del nodo, este podrá utilizarla durante sus fases de prueba. Esto, sin embargo, no es aplicable a todas las transacciones sintéticas. En las siguientes secciones se detallan estas excepciones (transacciones sintéticas que requieren instrucciones especiales de configuración).

## Transacciones sintéticas de conferencia de datos

Si el equipo que actúa como nodo de monitor no está en la red perimetral, lo más seguro es que no pueda ejecutar transacciones sintéticas de conferencia de datos, a menos que deshabilite la configuración de proxy de Internet Explorer de la cuenta de servicio de red. Haga lo siguiente para deshabilitarla:

1.  En el equipo que actúa como nodo de monitor, haga clic en **Inicio**, **Todos los programas** y **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y, finalmente, haga clic en **Ejecutar como administrador**.

2.  Escriba el siguiente comando en la ventana de la consola y presione ENTRAR:
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

Aparecerá el siguiente mensaje en la ventana Comandos:

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

Este mensaje indica que ha deshabilitado la configuración de proxy de Internet Explorer de la cuenta de servicio de red.

## Transacciones sintéticas de mensajería unificada de Exchange

La transacción sintética de Mensajería unificada de Exchange (UM) comprueba que los usuarios de prueba se pueden conectar a las cuentas de correo de voz hospedadas en Exchange. Estos usuarios de prueba deben estar configurados previamente con cuentas de correo de voz para poder usar pruebas de mensajería unificada de Exchange.

## Transacciones sintéticas de Chat persistente

Para usar la transacción sintética de Chat persistente, los administradores deben crear un canal y conceder permiso a los usuarios de prueba para que puedan usarlo. El cmdlet [Test-CsPersistentChatMessage](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPersistentChatMessage) sirve para configurar a los usuarios de prueba correctamente:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

Esta tarea de configuración debe realizarse desde la empresa:

  - Si se realiza en un equipo que no es servidor, el usuario que ejecute el cmdlet debe pertenecer al rol PersistentChatAdministrators de control de acceso basado en roles (RBAC).

  - Si se realiza desde el propio servidor, el usuario que ejecute el cmdlet debe pertenecer al grupo RTCUniversalServerAdmins.

El comando anterior incluía el parámetro Setup establecido en True ($True). Si incluye el parámetro Setup, Test-CsPersistentChatMessage creará un salón de Chat persistente especial y lo llenará con los usuarios de prueba. Esto sirve para garantizar que existe realmente un salón de chat destinado a realizar pruebas. No olvide que el parámetro Setup solo se puede ejecutar en un Servidor front-end.

Solo un administrador puede eliminar el salón de chat que Test-CsPersistentChatMessage crea.

## Transacciones sintéticas de llamada punto a punto de RTC

La transacción sintética [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsPstnPeerToPeerCall) confirma que es posible realizar y recibir llamadas a través de la Red telefónica conmutada (RTC).

Para ejecutar esta transacción sintética, los administradores deben tener preparado lo siguiente:

  - Dos usuarios de prueba (el autor y el receptor de la llamada) con Telefonía IP empresarial habilitada.

  - Números de llamada directa a la extensión (DID) de cada cuenta de usuario.

  - Directivas y rutas de voz que permitan efectuar llamadas al número del receptor para llegar a la puerta de enlace RTC.

  - Una puerta de enlace RTC que acepte llamadas, además de medios que enruten llamadas de regreso al grupo de servidores principales de un receptor en función del número marcado.

## Transacciones sintéticas de almacén de contactos unificados

La transacciones sintética de almacén de contactos unificados comprueba que Lync Server 2013 puede recuperar contactos de Microsoft Exchange Server 2013 en nombre de un usuario.

Para ejecutar esta transacción, se deben cumplir las siguientes condiciones:

  - Debe existir una configuración para [Administración de la autenticación servidor a servidor (Oauth) y las aplicaciones de socio en Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) entre Lync Server 2013 y Exchange 2013.

  - Los usuarios de prueba deben tener un buzón de Exchange 2013 válido.

Si se cumplen, los administradores pueden ejecutar el siguiente comando a fin de constatar que el usuario con la dirección SIP kenmyer@litwareinc.com puede recuperar sus contactos del almacén de contactos unificados:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

Detengámonos en el uso que se hace del parámetro Setup en el comando anterior. Si este parámetro está incluido al ejecutar Test-CsUnifiedContactStore, los contactos del usuario en cuestión (en este caso, sip:kenmyer@litwareinc.com) se trasladarán a almacén de contactos unificados (sobra decir que los contactos no se moverán si ya están en el almacén de contactos unificados). El parámetro Setup suele emplearse una sola vez (la primera vez que Test-CsUnifiedContactStore se ejecuta) y debe usarse única y exclusivamente con usuarios de prueba, es decir, con cuentas de usuario que nunca vayan a iniciar sesión en Lync Server. Después de migrar los usuarios de prueba al almacén de contactos unificados, puede comprobar que los contactos del usuario se pueden recuperar llamando a Test-CsUnifiedContactStore sin el parámetro Setup:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

## Transacciones sintéticas XMPP

La transacción sintética de mensajería instantánea XMPP (protocolo extensible de mensajería y presencia) requiere que la característica XMPP esté configurada con uno o más dominios federados.

Para habilitar la transacción sintética XMPP, se debe incluir un parámetro XmppTestReceiverMailAddress con una cuenta de usuario en un dominio XMPP que pueda enrutarse. Por ejemplo:

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

En este ejemplo es necesario que haya una regla de Lync Server 2013 para enrutar los mensajes de litwareinc.com a una puerta de enlace XMPP.

