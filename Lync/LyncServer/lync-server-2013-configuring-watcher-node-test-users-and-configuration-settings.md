---
title: Configuración de usuarios y opciones de configuración de prueba de nodos de monitor
description: Configurar los usuarios de prueba del nodo de monitor y los valores de configuración.
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
ms.openlocfilehash: e39a35d3db6ed80c715c706f4b5766e4b684e39e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542186"
---
# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Configuración de usuarios y opciones de configuración de prueba de nodos de monitor en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-07-29_

Después de configurar el equipo que funcionará como nodo de monitor, debe hacer lo siguiente:

1.  Crear las cuentas de prueba que usarán estos nodos de monitor. Si usa el método de autenticación Negotiate, también debe usar el cmdlet [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) para habilitar estas cuentas de prueba para su uso en el nodo de monitor.

2.  Actualizar las opciones de configuración del nodo de monitor.

En esta sección se describen estos temas:

  - Configurar cuentas de usuario de prueba

  - Configurar un nodo de monitor básico con las transacciones sintéticas predeterminadas

  - Configurar pruebas extendidas

  - Agregar y quitar transacciones sintéticas

  - Ver y probar la configuración de nodo de monitor

<div>

## <a name="configuring-test-user-accounts"></a>Configurar cuentas de usuario de prueba

Los usuarios de prueba no necesitan representar a personas reales, pero deben ser cuentas de servicios de dominio de Active Directory válidas; Además, estas cuentas deben estar habilitadas para Lync Server 2013, deben tener direcciones SIP válidas y deben estar habilitadas para telefonía IP empresarial (para usar la transacción sintética Test-CsPstnPeerToPeerCall). Si usa el método de autenticación TrustedServer, todo lo que debe hacer es asegurarse de que estas cuentas existen y se han configurado tal y como se especifica aquí. Debe asignar al menos tres usuarios de prueba para cada grupo de servidores que quiera probar.

Si usa el método de autenticación Negotiate, también debe usar el cmdlet **set-CsTestUserCredential** y el shell de administración de Lync Server para habilitar estas cuentas de prueba para que funcionen con las transacciones sintéticas. Para ello, puede ejecutar un comando similar al siguiente. (Estos comandos suponen que las tres cuentas de usuario de Active Directory ya se han creado y que esas cuentas se han habilitado para Lync Server 2013):

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Tenga en cuenta que debe incluir no solo la dirección SIP sino también el nombre de usuario y la contraseña. Si no incluye la contraseña Set-CsTestUserCredential le pedirá que escriba dicha información. El nombre de usuario puede especificarse con el formato de nombre de usuario nombre de dominio \\ que se muestra arriba o con el formato usuario Name@domain nombre; por ejemplo:

    -UserName "watcher3@litwareinc.com"

Para comprobar que se han creado las credenciales de usuario de prueba, ejecute estos comandos desde el shell de administración de Lync Server:

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Se debería devolver información similar a la siguiente para cada usuario:

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurar un nodo de monitor básico con las transacciones sintéticas predeterminadas

Una vez creados los usuarios, puede crear un nodo de monitor con un comando similar a este:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Este comando crea un nuevo nodo de monitor que usa la configuración predeterminada y ejecuta el conjunto predeterminado de transacciones sintéticas. El nuevo nodo de monitor también usa los usuarios de prueba watcher1@litwareinc.com, watcher2@litwareinc.com y watcher3@litwareinc.com. Si el nodo de monitor usa la autenticación TrustedServer, las tres cuentas de prueba pueden ser cualquier cuenta de usuario válida habilitada para Active Directory y Lync Server. Si el nodo de monitor usa el método de autenticación Negotiate, también debe habilitar esas cuentas de usuario para el nodo de monitor con el cmdlet **Set-CsTestUserCredential**.

</div>

<div>

## <a name="configuring-extended-tests"></a>Configurar pruebas extendidas

Si desea habilitar la prueba de red telefónica conmutada (RTC), que comprueba la conectividad con RTC, deberá realizar tareas de configuración adicionales al establecer el nodo de monitor. Primero, debe asociar los usuarios de prueba con el tipo de prueba RTC. Para ello, ejecute un comando similar a este desde dentro del shell de administración de Lync Server:

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

Tenga en cuenta que los resultados de este comando se deben almacenar en una variable. En este ejemplo, se trata de una variable denominada $pstnTest.

En este punto, puede usar el cmdlet **New-CsWatcherNodeConfiguration** para asociar el tipo de prueba (almacenado en la variable $pstnTest) a un grupo de servidores de Lync 2013. Por ejemplo, en el siguiente comando, se crea una nueva configuración de nodo de monitor para el grupo atl-cs-001.litwareinc.com, y se agregan los tres usuarios de prueba que se crearon anteriormente y también el tipo de prueba RTC:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Tenga en cuenta que se producirá un error en el comando anterior si no ha instalado los archivos principales de Lync Server y la base de datos RTCLocal en el equipo del nodo de monitor.

Para probar varias directivas de voz, debe crear una prueba extendida para cada directiva con el cmdlet **New-CsExtendedTest**. Los usuarios asignados a esta prueba se deben configurar con las directivas de voz deseadas. Las pruebas extendidas luego se transfieren al cmdlet **New-CsWatcherNodeConfiguration** con un comando similar al siguiente:

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Si se llama a New-CsWatcherNodeConfiguration sin usar el parámetro Tests, eso implica que solo las transacciones sintéticas predeterminadas (y la transacción sintética extendida especificada) se habilitarán para el nuevo nodo de monitor. Por lo tanto, el nodo de monitor probará los siguientes componentes:

  - Registro

  - Mensajería instantánea

  - GroupIM

  - P2PAV (sesiones de audio/vídeo punto a punto)

  - AvConference (audio/conferencia)

  - Presencia

  - ABS (servicio de libreta de direcciones)

  - ABWQ (servicio web de libreta de direcciones)

  - PSTN (llamadas de puerta de enlace RTC, especificadas como una prueba extendida. De manera predeterminada, esta opción está deshabilitada. La prueba se habilita en este caso solamente porque el comando habilitó RTC con el parámetro ExtendedTests).

Esto también significa que los siguientes componentes no se probarán de manera predeterminada:

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

Una vez configurado el nodo de monitor, puede usar el cmdlet **Set-CsWatcherNodeConfiguration** para agregar o quitar transacciones sintéticas en el nodo. Por ejemplo, para agregar la prueba PersistentChatMessage al nodo de monitor, use el método Add y un comando similar al siguiente:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

Es posible agregar varias pruebas si se separan los nombres de las pruebas con comas. Por ejemplo:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Tenga en cuenta que se generará un error si ya se habilitaron una o varias de estas pruebas (por ejemplo, DataConference) en el nodo de monitor. En este caso, aparecerá un mensaje de error similar al siguiente:

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

Cuando se produce este error, no se aplica ningún cambio. El comando se debe ejecutar de nuevo sin la prueba duplicada.

Para quitar una transacción sintética de un nodo de monitor, use el método Remove en vez del método Add. Por ejemplo, este comando quita la prueba ABWQ de un nodo de monitor:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

También puede usar el método Replace para reemplazar todas las pruebas habilitadas actualmente por una o varias pruebas nuevas. Por ejemplo, si solo desea que un nodo de monitor ejecute la prueba IM, puede configurar esto con el siguiente comando:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

Al ejecutar el comando anterior, se deshabilitarán todas las transacciones sintéticas del nodo de monitor especificado, excepto para la prueba IM.

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>Ver y probar la configuración de nodo de monitor

Si desea ver las pruebas que se asignaron a un nodo de monitor, use un comando similar a este:

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

El comando anterior devolverá información similar a la siguiente, según las transacciones sintéticas que se hayan asignado al nodo:

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
> Para ver las transacciones sintéticas en orden alfabético, use este comando en su lugar:<BR>Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object



</div>

Para comprobar que se ha creado un nodo de monitor, escriba el siguiente comando desde el shell de administración de Lync Server:

    Get-CsWatcherNodeConfiguration

Recibirá información similar a esta:

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Para comprobar que el nodo de monitor se ha configurado correctamente, escriba el siguiente comando desde el shell de administración de Lync Server:

    Test-CsWatcherNodeConfiguration

El comando anterior probará cada nodo de monitor de la implementación y proporcionará información, por ejemplo, indicará si:

  - Se instaló el rol de registrador necesario.

  - Se creó automáticamente la clave del Registro necesaria al ejecutar Set-CsWatcherNodeConfiguration.

  - Los servidores ejecutan la versión correcta de Lync Server.

  - Se configuraron correctamente los puertos.

  - Los usuarios de prueba asignados tienen las credenciales necesarias.

</div>

</div>

<span> </span>

</div>

</div>

</div>

