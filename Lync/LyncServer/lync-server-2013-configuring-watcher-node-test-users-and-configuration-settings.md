---
title: "Configurar usuarios de la prueba del nodo de monitor y opciones de configuración"
TOCTitle: "Conf. des ut. de test d’un nœud observateur et paramètres de configuration"
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48276324
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de los usuarios de la prueba del nodo de monitor y opciones de configuración

 

_**Última modificación del tema:** 2013-07-29_

Después de configurar el equipo que funcionará como nodo de monitor, debe hacer lo siguiente:

1.  Crear las cuentas de prueba que usarán estos nodos de monitor. Si usa el método de autenticación Negotiate, también debe usar el cmdlet [Set-CsTestUserCredential](https://docs.microsoft.com/en-us/powershell/module/skype/) para habilitar estas cuentas de prueba para su uso en el nodo de monitor.

2.  Actualizar las opciones de configuración del nodo de monitor.

En esta sección se describen estos temas:

  - Configurar cuentas de usuario de prueba

  - Configurar un nodo de monitor básico con las transacciones sintéticas predeterminadas

  - Configurar pruebas extendidas

  - Agregar y quitar transacciones sintéticas

  - Ver y probar la configuración de nodo de monitor

## Configurar cuentas de usuario de prueba

No es necesario que los usuarios de prueba representen a personales reales, pero deben ser cuentas válidas de Servicios de dominio de Active Directory. Además, estas cuentas se deben habilitar para Lync Server 2013, deben tener direcciones SIP válidas y se deben habilitar también para Telefonía IP empresarial (para usar la transacción sintética Test-CsPstnPeerToPeerCall). Si usa el método de autenticación TrustedServer, todo lo que necesita hacer es asegurarse de que esas cuentas existan y de que se hayan configurado como se especifica aquí. Debe asignar al menos tres usuarios de prueba para cada grupo que desea probar.

Si usa el método de autenticación Negotiate, debe usar también el cmdlet **Set-CsTestUserCredential** y el Shell de administración de Lync Server para habilitar estas cuentas de prueba a fin de que funcionen con las transacciones sintéticas. Para ello, puede ejecutar un comando similar al siguiente. (Estos comandos dan por sentado que se han creado las tres cuentas de usuario de Active Directory y que esas cuentas se han habilitado para Lync Server 2013):

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Tenga en cuenta que no solo debe incluir la dirección SIP, sino también el nombre de usuario y la contraseña. Si no incluye la contraseña, Set-CsTestUserCredential le pedirá que escriba esa información. El nombre de usuario se puede especificar con el formato nombredominio\\nombreusuario mostrado arriba o con el formato nombreusuario@nombredominio. Por ejemplo:

    -UserName "watcher3@litwareinc.com"

Para comprobar que se hayan creado las credenciales de usuario de prueba, ejecute estos comandos desde el Shell de administración de Lync Server:

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Se debería devolver información similar a la siguiente para cada usuario:

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

## Configurar un nodo de monitor básico con las transacciones sintéticas predeterminadas

Una vez creados los usuarios, puede crear un nodo de monitor con un comando similar a este:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Este comando crea un nuevo nodo de monitor que usa la configuración predeterminada y ejecuta el conjunto predeterminado de transacciones sintéticas. El nuevo nodo de monitor también usa los usuarios de prueba watcher1@litwareinc.com, watcher2@litwareinc.com y watcher3@litwareinc.com. Si el nodo de monitor usa la autenticación TrustedServer, las tres cuentas de prueba pueden ser cualquier cuenta de usuario válida habilitada para Active Directory y Lync Server. Si el nodo de monitor usa el método de autenticación Negotiate, también debe habilitar esas cuentas de usuario para el nodo de monitor con el cmdlet **Set-CsTestUserCredential**.

## Configurar pruebas extendidas

Si desea habilitar la prueba de red telefónica conmutada (RTC), que comprueba la conectividad con RTC, deberá realizar tareas de configuración adicionales al establecer el nodo de monitor. Primero, debe asociar los usuarios de prueba con el tipo de prueba RTC. Para ello, ejecute un comando similar al siguiente desde el Shell de administración de Lync Server:

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

Tenga en cuenta que los resultados de este comando se deben almacenar en una variable. En este ejemplo, se trata de una variable denominada $pstnTest.

En este momento, puede usar el cmdlet **New-CsWatcherNodeConfiguration** para asociar el tipo de prueba (almacenado en la variable $pstnTest) a un grupo de servidores Lync Server 2013. Por ejemplo, en el siguiente comando, se crea una nueva configuración de nodo de monitor para el grupo atl-cs-001.litwareinc.com, y se agregan los tres usuarios de prueba que se crearon anteriormente y también el tipo de prueba RTC:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Tenga en cuenta que el comando anterior no se ejecutará correctamente si no instaló los archivos principales de Lync Server y la base de datos RTCLocal en el equipo del nodo de monitor.

Para probar varias directivas de voz, debe crear una prueba extendida para cada directiva con el cmdlet **New-CsExtendedTest**. Los usuarios asignados a esta prueba se deben configurar con las directivas de voz deseadas. Las pruebas extendidas luego se transfieren al cmdlet **New-CsWatcherNodeConfiguration** con un comando similar al siguiente:

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Si se llama a New-CsWatcherNodeConfiguration sin usar el parámetro Tests, eso implica que solo las transacciones sintéticas predeterminadas (y la transacción sintética extendida especificada) se habilitarán para el nuevo nodo de monitor. Por lo tanto, el nodo de monitor probará los siguientes componentes:

  - Registro

  - IM

  - GroupIM

  - P2PAV (sesiones de audio/vídeo punto a punto)

  - AvConference (audio/conferencia)

  - Presencia

  - ABS (servicio de libreta de direcciones)

  - ABWQ (servicio web de libreta de direcciones)

  - RTC (llamadas de puerta de enlace RTC, especificadas como una prueba extendida. De manera predeterminada, RTC está deshabilitada. La prueba se habilita en este caso solamente porque el comando habilitó RTC con el parámetro ExtendedTests).

Esto también significa que los siguientes componentes no se probarán de manera predeterminada:

  - AVEdgeConnectivity

  - MCXP2PIM (mensajería instantánea para dispositivos móviles)

  - ExumConnectivity (mensajería unificada de Exchange)

  - JoinLauncher

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

## Agregar y quitar transacciones sintéticas

Una vez configurado el nodo de monitor, puede usar el cmdlet **Set-CsWatcherNodeConfiguration** para agregar o quitar transacciones sintéticas en el nodo. Por ejemplo, para agregar la prueba PersistentChatMessage al nodo de monitor, use el método Add y un comando similar al siguiente:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

Es posible agregar varias pruebas si se separan los nombres de las pruebas con comas. Por ejemplo:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Tenga en cuenta que se generará un error si ya se habilitaron una o varias de estas pruebas (por ejemplo, DataConference) en el nodo de monitor. En este caso, aparecerá un mensaje de error similar al siguiente:

    Set-CsWatcherNodeConfiguration : Existe la secuencia de claves duplicadas 'DataConference' para la clave 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' o una restricción de identidad única.

Cuando se produce este error, no se aplica ningún cambio. El comando se debe ejecutar de nuevo sin la prueba duplicada.

Para quitar una transacción sintética de un nodo de monitor, use el método Remove en vez del método Add. Por ejemplo, este comando quita la prueba ABWQ de un nodo de monitor:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

También puede usar el método Replace para reemplazar todas las pruebas habilitadas actualmente por una o varias pruebas nuevas. Por ejemplo, si solo desea que un nodo de monitor ejecute la prueba IM, puede configurar esto con el siguiente comando:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

Al ejecutar el comando anterior, se deshabilitarán todas las transacciones sintéticas del nodo de monitor especificado, excepto para la prueba IM.

## Ver y probar la configuración de nodo de monitor

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

> [!TIP]  
> Para ver las transacciones sintéticas en orden alfabético, use este comando en su lugar:<br />
> Get-CsWatcherNodeConfiguration –Identity &quot;atl-cs-001.litwareinc.com&quot; | Select-Object –ExpandProperty Tests | Sort-Object


Para comprobar que se haya creado un nodo de monitor, escriba el siguiente comando desde el Shell de administración de Lync Server:

    Get-CsWatcherNodeConfiguration

Recibirá información similar a esta:

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Para comprobar que se haya configurado correctamente el nodo de monitor, escriba el siguiente comando desde el Shell de administración de Lync Server:

    Test-CsWatcherNodeConfiguration

El comando anterior probará cada nodo de monitor de la implementación y proporcionará información, por ejemplo, indicará si:

  - Se instaló el rol de registrador necesario.

  - Se creó automáticamente la clave del Registro necesaria al ejecutar Set-CsWatcherNodeConfiguration.

  - Los servidores ejecutan la versión correcta de Lync Server.

  - Se configuraron correctamente los puertos.

  - Los usuarios de prueba asignados tienen las credenciales necesarias.

