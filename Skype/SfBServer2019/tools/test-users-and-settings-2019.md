---
title: Configurar los usuarios y las opciones de configuración de la prueba del nodo de monitor
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: configurar las opciones de las cuentas de usuario y del nodo de monitor para las transacciones sintéticas de Skype empresarial Server.'
ms.openlocfilehash: 991b78a4581d616e79aaa4f096a76aad8636b632
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989035"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Configurar los usuarios y las opciones de configuración de la prueba del nodo de monitor
 
**Resumen:** Configure las cuentas de usuario y la configuración del nodo de monitor para las transacciones sintéticas de Skype empresarial Server.
  
Después de configurar el equipo que funcionará como nodo de monitor, debe hacer lo siguiente:
  
1. [Configure las cuentas de usuario de prueba](test-users-and-settings-2019.md#testuser) que usarán estos nodos de monitor. Si usa el método de autenticación Negotiate, también debe usar el cmdlet **Set-CsTestUserCredential** para habilitar estas cuentas de prueba para su uso en el nodo de monitor.
    
2. Actualizar las opciones de configuración del nodo de monitor.
    
## <a name="configure-test-user-accounts"></a>Configurar cuentas de usuario de prueba
<a name="testuser"> </a>

Las cuentas de prueba no necesitan representar personas reales, pero deben ser cuentas de Active Directory válidas. Además, estas cuentas deben estar habilitadas para Skype empresarial Server, deben tener direcciones SIP válidas y deben estar habilitadas para telefonía IP empresarial (para usar la transacción sintética CsPstnPeerToPeerCall). 
  
Si está usando el método de autenticación TrustedServer, solamente debe asegurarse de que estas cuentas existen y configurarlas como se ha indicado. Debe asignar al menos tres usuarios de prueba para cada grupo que desee probar. Si usa el método de autenticación Negotiate, también debe usar el cmdlet Set-CsTestUserCredential y el shell de administración de Skype empresarial Server para habilitar estas cuentas de prueba para que funcionen con las transacciones sintéticas. Para ello, ejecute un comando similar al siguiente (estos comandos suponen que se han creado las tres cuentas de usuario de Active Directory y que estas cuentas están habilitadas para Skype empresarial Server):
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

Debe incluir no solo la dirección SIP, sino también el nombre de usuario y una contraseña. Si no incluye la contraseña, el cmdlet Set-CsTestUserCredential le pedirá que la escriba. El nombre de usuario se pueden especificar con el formato nombre de dominio\nombre de usuario que se muestra en el bloque de código anterior.
  
Para comprobar que se crearon las credenciales de usuario de prueba, ejecute estos comandos desde el shell de administración de Skype empresarial Server:
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

Se debería devolver información similar a la siguiente para cada usuario:
  
|**Nombre**|**Contraseña**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System. Security. SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurar un nodo de monitor básico con las transacciones sintéticas predeterminadas

Una vez creados los usuarios, puede crear un nodo de monitor con un comando similar a este:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

Este comando crea un nodo de monitor nuevo que usa la configuración predeterminada y ejecuta el conjunto predeterminado de transacciones sintéticas. El nuevo nodo de monitor también usa los usuarios de prueba watcher1@litwareinc.com, watcher2@litwareinc.com y watcher3@litwareinc.com. Si el nodo de monitor usa autenticación TrustedServer, las tres cuentas de prueba pueden ser cualquier cuenta de usuario válida habilitada para Active Directory y Skype Empresarial Server. Si el nodo de monitor usa el método de autenticación Negotiate, estas cuentas de usuario también deben estar habilitadas para el nodo de monitor con el cmdlet Set-CsTestUserCredential.
  
Para validar que la detección automática de grupo de servidores de destino para el inicio de sesión se ha configurado correctamente en lugar de que esté destinado a un grupo directamente, siga estos pasos:
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Configurar pruebas extendidas

Si desea habilitar la prueba de RTC, que comprueba la conectividad con la red telefónica pública conmutada, debe realizar tareas de configuración adicionales al establecer el nodo de monitor. En primer lugar, debe asociar los usuarios de prueba con el tipo de prueba RTC ejecutando un comando similar al siguiente desde el Shell de administración de Skype Empresarial Server:
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Tenga en cuenta que los resultados de este comando se deben almacenar en una variable. En este ejemplo, se trata de una variable denominada $pstnTest. 
  
A continuación, puede usar el cmdlet **New-CsWatcherNodeConfiguration** para asociar el tipo de prueba (almacenado en la variable $pstnTest) a un grupo de servidores de Skype empresarial. Por ejemplo, en el siguiente comando se crea una nueva configuración de nodo de monitor para el grupo atl-cs-001.litwareinc.com, y se agregan los tres usuarios de prueba que se crearon anteriormente y también el tipo de prueba RTC:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Tenga en cuenta que el comando anterior no se ejecutará correctamente si no instaló los archivos principales de Skype Empresarial Server y la base de datos RTCLocal en el equipo del nodo de monitor. 
  
Para probar varias directivas de voz, puede crear una prueba extendida para cada directiva con el cmdlet **New-CsExtendedTest**. Los usuarios siempre se deben configurar con las directivas de voz deseadas. Las pruebas extendidas se pasan al cmdlet **New-CsWatcherNodeConfiguration** con delimitadores de coma, como, por ejemplo:
  
-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}
  
Dado que el cmdlet **New-CsWatcherNodeConfiguration** se ha invocado sin usar el parámetro Tests, para el nodo de monitor solo se habilitarán las transacciones sintéticas predeterminadas (y la transacción sintética extendida especificada). Por lo tanto, el nodo de monitor probará estos componentes:
  
- Registration
    
- IM
    
- GroupIM
    
- P2PAV (sesiones de audio/vídeo punto a punto)
    
- AvConference (audio/conferencia)
    
- Presence
    
- ABS (servicio de libreta de direcciones)
    
- ABWQ (servicio web de libreta de direcciones)
    
Los siguientes componentes no se probarán de manera predeterminada:
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (mensajería unificada de Exchange)
    
- JoinLauncher
    
- MCXP2PIM (mensajería instantánea de dispositivos móviles heredados)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (llamadas de puerta de enlace RTC, especificadas como una prueba extendida)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>Agregar y quitar transacciones sintéticas

Una vez configurado el nodo de monitor, puede usar el cmdlet Set-CsWatcherNodeConfiguration para agregar o quitar transacciones sintéticas en el nodo. Por ejemplo, para agregar la prueba PersistentChatMessage al nodo de monitor, use el método Add y un comando similar al siguiente:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

Es posible agregar varias pruebas si se separan los nombres de las pruebas con comas. Por ejemplo:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

Tenga en cuenta que se generará un error si ya se habilitaron una o varias de estas pruebas (por ejemplo, DataConference) en el nodo de monitor. En este caso, aparecerá un mensaje de error similar al siguiente:
  
Set-CsWatcherNodeConfiguration: hay una secuencia de teclas duplicada 'DataConference' para la clave 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' o restricción de identidad identidad.
  
Cuando se produce este error, no se aplica ningún cambio. Es necesario volver a ejecutar el comando sin la prueba duplicada.
  
Para quitar una transacción sintética de un nodo de monitor, use el método Remove. Por ejemplo, este comando quita la prueba ABWQ de un nodo de monitor:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

También puede usar el método Replace para reemplazar todas las pruebas habilitadas actualmente por una o varias pruebas nuevas. Por ejemplo, si solo desea que un nodo de monitor ejecute la prueba IM, puede configurar esto con el siguiente comando:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Al ejecutar el comando anterior, se deshabilitarán todas las transacciones sintéticas del nodo de monitor especificado, excepto para la prueba IM.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Ver y probar la configuración de nodo de monitor

Si desea ver las pruebas que se asignaron a un nodo de monitor, use un comando similar a este:
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

El comando anterior devolverá información similar a la siguiente, según las transacciones sintéticas que se hayan asignado al nodo:
  
Registro de mensajes instantáneos de GroupIM P2PAV AvConference Presence PersistentChatMessage congresos
> [!TIP]
> Para ver las transacciones sintéticas en orden alfabético, use este comando en su lugar: 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Para comprobar que se haya creado un nodo de monitor, escriba el siguiente comando desde el Shell de administración de Skype Empresarial Server:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Obtendrá una información similar a la siguiente:
  
Identity: atl-cs-001.litwareinc.com TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...} ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...} TargetFqdn: atl-cs-001.litwareinc.com númeroDePuerto: 5061To comprobar que el nodo de monitor se ha configurado correctamente, escriba el siguiente comando desde el shell de administración de Skype empresarial Server:
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Este comando probará cada nodo de monitor de la implementación y confirmará si se han completado las siguientes acciones:
  
- Se ha instalado el rol de registrador necesario
    
- Se ha creado la clave de registro necesaria (completado al ejecutar el cmdlet Set-Cs WatcherNodeConfiguration)
    
- Los servidores ejecutan la versión correcta de Skype Empresarial Server
    
- Los puertos están bien configurados
    
- Los usuarios de prueba asignados tienen las credenciales necesarias
    
## <a name="managing-watcher-nodes"></a>Administración de nodos de monitor
<a name="testuser"> </a>

Aparte de modificar las transacciones sintéticas que se ejecutan en un nodo de monitor, los administradores también pueden usar el cmdlet **Set-CsWatcherNodeConfiguration**para llevar a cabo otras tareas importantes, como habilitar y deshabilitar el nodo de monitor o configurarlo para que use direcciones URL internas o externas cuando ejecute sus pruebas.
  
De forma predeterminada, los nodos de monitor están diseñadas para ejecutar periódicamente todas sus transacciones sintéticas habilitadas. En ocasiones, sin embargo, es posible que desee suspender esas operaciones. Por ejemplo, si el nodo de monitor está desconectado temporalmente de la red y, a continuación, no hay ningún motivo para ejecutar las transacciones sintéticas. Estas transacciones darán lugar a un error si no hay conectividad de red. Para deshabilitar temporalmente un nodo de monitor, ejecute un comando similar al siguiente desde el Shell de administración de Skype Empresarial Server:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Con este comando deshabilitará la ejecución de transacciones sintéticas en el nodo de monitor atl watcher 001.litwareinc.com. Para volver a ejecutarlas, establezca la propiedad Enabled en True ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> La propiedad Enabled sirve para activar y desactivar nodos de monitor. En caso de que quiera eliminar un nodo de monitor permanentemente, use el cmdlet **Remove-CsWatcherNodeConfiguration**:
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Con este comando se elimina toda la configuración de nodo de monitor del equipo en cuestión, lo que evita que se ejecuten transacciones sintéticas automáticamente. Sin embargo, el comando no desinstala los archivos del agente de System Center ni los archivos de sistema de Skype empresarial Server.
  
Cuando realizan pruebas, los nodos de monitor usan de forma predeterminada las direcciones URL externas de una organización, aunque se pueden configurar para que usen las direcciones URL internas. Esto permite que los administradores comprueben el acceso a la dirección URL de los usuarios de dentro de la red perimetral. Para configurar un nodo de monitor para que use direcciones URL internas en lugar de externas, establezca la propiedad UseInternalWebURls en True ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

Restablecer esta propiedad en el valor predeterminado de False ($False) hará que el monitor vuelva a usar las direcciones URL externas:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Instrucciones de configuración especiales para transacciones sintéticas
<a name="special_synthetictrans"> </a>

La mayor parte de las transacciones sintéticas se pueden ejecutar en un nodo de monitor tal cual está. En la mayoría de los casos, en cuanto la transacción sintética se agrega a los valores de configuración del nodo de monitor, el nodo de monitor puede empezar a usar la transacción sintética durante las fases de prueba. Sin embargo, hay algunas transacciones sintéticas que requieren instrucciones de configuración especiales, como se indica en las siguientes secciones.
  
### <a name="data-conferencing-synthetic-transaction"></a>Transacciones sintéticas de conferencia de datos

Si el equipo que actúa como nodo de monitor no está en la red perimetral, lo más seguro es que no pueda ejecutar transacciones sintéticas de conferencia de datos, a menos que deshabilite la configuración de proxy del explorador Windows Internet Explorer® para la cuenta de servicio de red siguiendo estos pasos:
  
1. En el equipo que actúa como nodo de monitor, haga clic sucesivamente en **Inicio**, **Todos los programas** y **Accesorios**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. En la ventana de la consola, escriba el siguiente comando y presione ENTRAR: 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

Verá el siguiente mensaje que se muestra en la ventana de línea de comandos:
  
BITSAdmin está en desuso y no se garantiza que esté disponible en futuras versiones de Windows. Las herramientas de administración para el servicio BITS ahora se proporcionan a través de cmdlets de BITS PowerShell.
  
Configuración de proxy para la cuenta NetworkService establecida en NO_PROXY. 
  
(conexión = predeterminada)
  
Este mensaje indica que ha deshabilitado la configuración de proxy de Internet Explorer para la cuenta de servicio de red.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Transacción sintética de mensajería unificada de Exchange

La transacción sintética de Mensajería unificada de Exchange (UM) comprueba que los usuarios de prueba se pueden conectar a las cuentas de correo de voz hospedadas en Exchange.
  
Los usuarios de prueba deben estar configurados previamente con cuentas de correo de voz. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Transacción sintética de chat persistente

Para usar la transacción sintética de chat persistente, en primer lugar se debe crear un canal y conceder permiso a los usuarios de prueba para que puedan usarlo.
  
Puede usar la transacción sintética de chat persistente para configurar este canal: 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Esta tarea de configuración debe realizarse desde la empresa:
  
- Si se realiza en un equipo que no es servidor, el usuario que ejecuta el cmdlet debe pertenecer al rol CsPersistentChatAdministrators de control de acceso basado en roles (RBAC).
    
- Si se realiza desde el propio servidor, el usuario que ejecuta el cmdlet debe pertenecer al grupo RTCUniversalServerAdmins.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Transacción sintética de llamada punto a punto de RTC

La transacción sintética Test-CsPstnPeerToPeerCall confirma que es posible realizar y recibir llamadas a través de la Red telefónica conmutada (RTC).
  
Para ejecutar esta transacción sintética, se debe configurar lo siguiente:
  
- Dos usuarios de prueba habilitados para UC (el autor y el receptor).
    
- Números de llamada directa a la extensión (DID) de cada cuenta de usuario.
    
- Directivas de VoIP y rutas de voz que permiten que las llamadas al número del receptor lleguen a la puerta de enlace PSTN.
    
- Una puerta de enlace RTC que acepta llamadas y medios que van a enrutar las llamadas al grupo de servidores principales de un destinatario, según el número marcado.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Transacción sintética de almacén de contactos unificados

La transacción sintética de tienda de contactos unificada verifica la capacidad de Skype empresarial Server para recuperar contactos en nombre de un usuario de Exchange.
  
Para ejecutar esta transacción, se deben cumplir las siguientes condiciones:
  
- Autenticación de servidor a servidor Lyss-Exchange debe estar configurada.
    
- Los usuarios de prueba deben tener un buzón de Exchange válido.
    
Después de que se cumplan estas condiciones, puede ejecutar el siguiente cmdlet de Windows PowerShell para migrar las listas de contactos de los usuarios de prueba a Exchange:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

El proceso de migración de las listas de contactos de los usuarios de prueba a Exchange puede tardar un tiempo. Para supervisar el progreso de la migración, se puede ejecutar la misma línea de comandos sin la marca-Setup:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

La ejecución de estas línea de comandos será correcta una vez finalizada la migración.
  
### <a name="xmpp-synthetic-transaction"></a>Transacción sintética XMPP

La transacción sintética de mensajería instantánea XMPP (Extensible Messaging and Presence Protocol) requiere que la característica XMPP esté configurada con uno o más dominios federados.
  
Para habilitar la transacción sintética XMPP, se debe incluir un parámetro XmppTestReceiverMailAddress con una cuenta de usuario en un dominio XMPP que pueda enrutarse. Por ejemplo:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

En este ejemplo, tendrá que existir una regla de Skype empresarial Server para enrutar mensajes para litwareinc.com a una puerta de enlace XMPP.

> [!NOTE]
> Las puertas de enlace y los servidores proxy XMPP estaban disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019. Para obtener más información, consulte [migrar la Federación XMPP](../migration/migrating-xmpp-federation.md) .
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Transacción sintética de Video Interop Server (VIS)

La transacción sintética del servidor de interoperabilidad de vídeo requiere que descargue e instale los archivos de compatibilidad con transacciones sintéticas ([VISSTSupportPackage. msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)). 
  
Para instalar VISSTSupportPackage.msi, asegúrese de que las dependencias (en los requisitos del sistema) para el archivo msi ya estén instaladas. Ejecute VISSTSupportPackage.msi para realizar una instalación sencilla. El archivo. msi instala todos los archivos en la siguiente ruta de acceso: "paquete de compatibilidad con la transacción sintética de%ProgramFiles%\VIS".
  
Para obtener más información sobre cómo ejecutar la transacción sintética, consulte la documentación del cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) .
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Cambiar la frecuencia de ejecución para transacciones sintéticas
<a name="special_synthetictrans"> </a>

De forma predeterminada, las transacciones sintéticas se ejecutarán con los usuarios configurados cada 15 minutos. Las transacciones sintéticas se ejecutan de forma secuencial en un conjunto de usuarios para evitar que dos transacciones sintéticas entren en conflicto. Se necesita un intervalo más largo para dar tiempo para que finalice todas las transacciones sintéticas.
  
Si es conveniente ejecutar transacciones sintéticas más a menudo, deberá reducir el número de transacciones sintéticas que se ejecutan con un conjunto de usuarios determinado para que las pruebas puedan completarse en el intervalo de tiempo que desee con un tiempo de margen de flexibilidad para posibles retrasos en la red. Si es necesario ejecutar más transacciones sintéticas, cree más conjuntos de usuarios para ejecutar transacciones sintéticas adicionales.
  
Para cambiar la frecuencia de ejecución de las transacciones, siga estos pasos:
  
1. Abra System Center Operations Manager. Haga clic en la sección creación. Haga clic en la sección reglas (en creación)
    
2. En la sección reglas, busque la regla con el nombre "regla principal de colección de rendimiento del Ejecutor de transacciones sintéticas"
    
3. Haga clic con el botón derecho en la regla y seleccione reemplazos, seleccione invalidar la regla y, a continuación, seleccione "para todos los objetos de clase: monitor de grupo"
    
4. En la ventana Propiedades de reemplazo, seleccione nombre de parámetro "frecuencia" y establezca el valor de invalidación en el valor que desee.
    
5. En la misma ventana, seleccione el módulo de administración al que se debe aplicar esta invalidación.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Uso de registro enriquecido para transacciones sintéticas
<a name="special_synthetictrans"> </a>

Las transacciones sintéticas son de gran utilidad para identificar problemas con el sistema. Por ejemplo, el cmdlet Test-CsRegistration podría alertar a los administradores sobre posibles problemas de los usuarios para registrarse en Skype Empresarial Server. Sin embargo, puede que se necesiten más detalles para determinar la causa real del error.
  
Por este motivo, las transacciones sintéticas proporcionan registros enriquecidos que, para cada una acciones que lleva a cabo una transacción sintética, registran la siguiente información:
  
- La hora a la que se inició la actividad.
    
- La hora a la que finalizó la actividad.
    
- La acción que se ha realizado (por ejemplo, crear, unirse o abandonar una conferencia, iniciar sesión en Skype Empresarial Server o enviar mensaje instantáneo).
    
- Mensajes de error o advertencias detalladas o informativas generadas cuando se ejecutó la actividad.
    
- Mensajes de registro SIP.
    
- Códigos de diagnóstico o registros de excepción generados cuando se ejecutó la actividad.
    
- Resultado neto de la ejecución de la actividad.
    
Esta información se genera automáticamente cada vez que se ejecuta una transacción sintética, pero no se muestra ni se guarda automáticamente en un archivo de registro. Si está ejecutando manualmente una transacción sintética, puede usar el parámetro OutLoggerVariable para especificar la variable de Windows PowerShell en la que se va a almacenar la información. Desde allí, tiene la opción de usar uno de estos dos métodos para guardar y ver mensajes de error en los registros enriquecidos en formato XML o HTML. 
  
Para recuperar la información de solución, especifique el parámetro OutLoggerVariable, seguido de un nombre de variable que elija:
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> : No anteponga el carácter $ al nombre de la variable. Use, por ejemplo, el nombre de variable RegistrationTest, no $RegistrationTest. 
  
Cuando ejecute este comando, verá una salida similar a esta:
  
FQDN de destino: atl-cs-001.litwareinc.com resultado: latencia de error: 00:00:00 mensaje de error: este equipo no tiene ningún certificado asignado. Diagnóstico: puede obtener acceso a información mucho más detallada sobre este error que solo el mensaje de error que se muestra aquí. Para acceder a esta información en formato HTML, use un comando similar a este para guardar la información almacenada en la variable RegistrationTest en un archivo HTML:
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Del mismo modo, puede usar el método ToXML() para guardar los datos en un archivo XML:
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Puede ver estos archivos con Windows Internet Explorer, Microsoft Visual Studio o con cualquier otra aplicación capaz de abrir archivos HTML/XML.
  
Las transacciones sintéticas ejecutadas desde dentro de System Center Operations Manager generarán automáticamente estos archivos de registro por si se producen errores. Estos registros no se generarán si se produce un error en la ejecución antes de que Skype Empresarial Server PowerShell pueda cargar y ejecutar la transacción sintética. 
  
> [!IMPORTANT]
> De forma predeterminada, Skype empresarial Server guarda los archivos de registro en una carpeta que no está compartida. Para que estos registros sean fácilmente accesibles, debe compartir esta carpeta. Por ejemplo: \\ATL-watcherer-001. litwareinc. com\WatcherNode. 
