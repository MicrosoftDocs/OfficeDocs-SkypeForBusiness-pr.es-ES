---
title: Configuración de los usuarios de prueba y los parámetros de configuración del nodo Monitor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3713844d5d2364459a28c5919bb1d32d421d706
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Configuración de los usuarios de prueba y la configuración de los nodos de monitor en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-29_

Después de configurar el equipo que funcionará como nodo de monitor, debe hacer lo siguiente:

1.  Cree las cuentas de prueba que usarán estos nodos de monitor. Si usa el método de autenticación Negotiate, también debe usar el cmdlet [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) para habilitar estas cuentas de prueba para su uso en el nodo de monitor.

2.  Actualizar las opciones de configuración del nodo de monitor.

Esta sección trata:

  - Configuración de las cuentas de usuario de prueba

  - Configuración de un nodo de monitor básico con las transacciones sintéticas predeterminadas

  - Configurar pruebas extendidas

  - Agregar y quitar transacciones sintéticas

  - Ver y probar la configuración de nodo de monitor

<div>

## <a name="configuring-test-user-accounts"></a>Configuración de las cuentas de usuario de prueba

Los usuarios de prueba no necesitan representar personas reales, pero deben ser cuentas válidas de servicios de dominio de Active Directory; Además, estas cuentas deben estar habilitadas para Lync Server 2013, deben tener direcciones SIP válidas y deben estar habilitadas para telefonía IP empresarial (para usar la transacción sintética CsPstnPeerToPeerCall). Si usa el método de autenticación TrustedServer, todo lo que tiene que hacer es asegurarse de que estas cuentas existen y se han configurado tal y como se especifica aquí. Debe asignar al menos tres usuarios de prueba para cada grupo que desee probar.

Si usa el método de autenticación Negotiate, también debe usar el cmdlet **set-CsTestUserCredential** y el shell de administración de Lync Server para habilitar estas cuentas de prueba para que funcionen con las transacciones sintéticas. Puede hacerlo ejecutando un comando similar al siguiente. (Estos comandos suponen que las tres cuentas de usuario de Active Directory ya se han creado y que estas cuentas se han habilitado para Lync Server 2013.):

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Tenga en cuenta que debe incluir no solo la dirección SIP sino también el nombre de usuario y la contraseña. Si no incluye la contraseña establecida, CsTestUserCredential le pedirá que introduzca esa información. El nombre de usuario se puede especificar con el formato\\de nombre de usuario del nombre de usuario que se muestra arriba o usando el formato de usuario Name@domain nombre; por ejemplo:

    -UserName "watcher3@litwareinc.com"

Para comprobar que se crearon las credenciales de usuario de prueba, ejecute estos comandos desde el shell de administración de Lync Server:

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Se debe devolver información similar a la siguiente para cada usuario:

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configuración de un nodo de monitor básico con las transacciones sintéticas predeterminadas

Después de que se hayan creado los usuarios de prueba, puede crear un nodo de monitor con un comando parecido a este:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Este comando crea un nodo de monitor nuevo que usa la configuración predeterminada y ejecuta el conjunto predeterminado de transacciones sintéticas. El nuevo nodo de monitor también usa los usuarios de prueba watcher1@litwareinc.com, watcher2@litwareinc.com y watcher3@litwareinc.com. Si el nodo de monitor usa la autenticación TrustedServer, las tres cuentas de prueba pueden ser cualquier cuenta de usuario válida habilitada para Active Directory y Lync Server. Si el nodo de monitor usa el método de autenticación Negotiate, también debe habilitar estas cuentas de usuario para el nodo de monitor mediante el cmdlet **set-CsTestUserCredential** .

</div>

<div>

## <a name="configuring-extended-tests"></a>Configurar pruebas extendidas

Si desea habilitar la red de telefonía pública conmutada (prueba RTC), que verifica la conectividad con la red de telefonía pública conmutada, tendrá que realizar cierta configuración adicional al configurar el nodo de monitor. En primer lugar, debe asociar los usuarios de prueba con el tipo de prueba RTC. Para ello, ejecute un comando similar a este desde el shell de administración de Lync Server:

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

Tenga en cuenta que los resultados de este comando deben almacenarse en una variable. En este ejemplo, esa es una variable denominada $pstnTest.

En este punto, puede usar el cmdlet **New-CsWatcherNodeConfiguration** para asociar el tipo de prueba (almacenado en la variable $pstnTest) a un grupo de servidores de Lync 2013. Por ejemplo, el siguiente comando crea una nueva configuración de nodo de monitor para el grupo atl-cs-001.litwareinc.com, agregando los tres usuarios de prueba que se crearon previamente y también agregando el tipo de prueba RTC:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Tenga en cuenta que el comando anterior fallará si no ha instalado los archivos principales de Lync Server y la base de datos RTCLocal en el equipo del nodo de supervisor.

Para probar varias directivas de voz, debe crear una prueba extendida para cada Directiva mediante el cmdlet **New-CsExtendedTest** . Los usuarios asignados a esta prueba deben estar configurados con las directivas de voz deseadas. Las pruebas extendidas se pasan al cmdlet **New-CsWatcherNodeConfiguration** con un comando similar al siguiente:

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Si se llama New-CsWatcherNodeConfiguration sin usar el parámetro tests, significa que solo las transacciones sintéticas predeterminadas (y la transacción sintética extendida especificada) se habilitarán para el nuevo nodo de monitor. Esto significa que el nodo de monitor probará los siguientes componentes:

  - Registration

  - IM

  - GroupIM

  - P2PAV (sesiones de audio/vídeo punto a punto)

  - AvConference (audio/conferencia)

  - Presence

  - ABS (servicio de libreta de direcciones)

  - ABWQ (servicio web de libreta de direcciones)

  - PSTN (llamadas de puerta de enlace RTC, especificadas como una prueba extendida). De forma predeterminada, la RTC está deshabilitada. En este caso, la prueba solo está habilitada porque el comando habilitó la RTC con el parámetro ExtendedTests).

Esto también significa que los siguientes componentes no se probarán de forma predeterminada:

  - AVEdgeConnectivity

  - MCXP2PIM (mensajería instantánea para dispositivos móviles)

  - ExumConnectivity (mensajería unificada de Exchange)

  - JoinLauncher

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>Agregar y quitar transacciones sintéticas

Una vez que se ha configurado un nodo de monitor, puede usar el cmdlet **set-CsWatcherNodeConfiguration** para agregar o quitar las transacciones sintéticas del nodo. Por ejemplo, para agregar la prueba PersistentChatMessage al nodo de monitor, use el método Add y un comando similar al siguiente:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

Es posible agregar varias pruebas si se separan los nombres de las pruebas con comas. Por ejemplo:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Tenga en cuenta que se producirá un error si una o más de estas pruebas (por ejemplo, congresos) ya se han habilitado en el nodo de monitor. En este caso, aparecerá un mensaje de error similar al siguiente:

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

Cuando se produce este error, no se aplica ningún cambio. Se debe volver a ejecutar el comando con la prueba duplicada eliminada.

Para quitar una transacción sintética de un nodo de monitor, use el método Remove en lugar del método Add. Por ejemplo, este comando quita la prueba ABWQ de un nodo de monitor:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

También puede usar el método replace para reemplazar todas las pruebas habilitadas actualmente con una o más pruebas nuevas. Por ejemplo, si solo desea que un nodo de monitor ejecute la prueba de mi, puede configurarlo con este comando:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

Al ejecutar el comando anterior, se deshabilitarán todas las transacciones sintéticas en el nodo de monitor especificado, excepto para la mensajería instantánea.

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>Ver y probar la configuración de nodo de monitor

Si desea ver las pruebas que se asignaron a un nodo de monitor, use un comando similar a este:

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

El comando anterior devolverá información similar a la siguiente, en función de las transacciones sintéticas que se hayan asignado al nodo:

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> Para ver las transacciones sintéticas en orden alfabético, use este comando en su lugar:<BR>Get-CsWatcherNodeConfiguration – Identity "atl-cs-001.litwareinc.com" | Select-Object-pruebas ExpandProperty | Sort-Object



</div>

Para comprobar que se ha creado un nodo de monitor, escriba el siguiente comando en el shell de administración de Lync Server:

    Get-CsWatcherNodeConfiguration

Recibirá información similar a la siguiente:

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Para comprobar que el nodo de monitor se ha configurado correctamente, escriba el siguiente comando en el shell de administración de Lync Server:

    Test-CsWatcherNodeConfiguration

El comando anterior probará cada nodo de monitor de la implementación y le informará de si:

  - Se ha instalado el rol de registrador requerido.

  - Cuando ejecutó Set-CsWatcherNodeConfiguration, se creó la clave de registro requerida.

  - Los servidores ejecutan la versión correcta de Lync Server.

  - Tus puertos se han configurado correctamente.

  - Los usuarios de prueba asignados tienen las credenciales necesarias.

</div>

</div>

<span> </span>

</div>

</div>

</div>

