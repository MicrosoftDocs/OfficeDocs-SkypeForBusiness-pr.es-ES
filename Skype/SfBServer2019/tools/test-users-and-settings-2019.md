---
title: Configuración de usuarios y opciones de prueba de nodo de monitor
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: configure las cuentas de usuario de prueba y las opciones del nodo de monitor para las transacciones sintéticas de Skype Empresarial Server.'
ms.openlocfilehash: 6edce666345e4691d8850e5806eedbebc98e3743
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812770"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Configuración de usuarios y opciones de prueba de nodo de monitor
 
**Resumen:** Configure las cuentas de usuario de prueba y las opciones del nodo de monitor para las transacciones sintéticas de Skype Empresarial Server.
  
Después de configurar el equipo que funcionará como nodo de monitor, debe hacer lo siguiente:
  
1. [Configure las cuentas de usuario de prueba](test-users-and-settings-2019.md#testuser) para que las utilicen estos nodos de monitor. Si usa el método de autenticación Negotiate, también debe usar el cmdlet **Set-CsTestUserCredential** para habilitar estas cuentas de prueba para su uso en el nodo de monitor.
    
2. Actualizar las opciones de configuración del nodo de monitor.
    
## <a name="configure-test-user-accounts"></a>Configurar cuentas de usuario de prueba
<a name="testuser"> </a>

Las cuentas de prueba no necesitan representar personas reales, pero deben ser cuentas válidas de Active Directory. Además, estas cuentas deben estar habilitadas para Skype Empresarial Server, deben tener direcciones SIP válidas y deben estar habilitadas para Telefonía IP empresarial (para usar la transacción sintética de Test-CsPstnPeerToPeerCall). 
  
Si usa el método de autenticación TrustedServer, todo lo que necesita hacer es asegurarse de que estas cuentas existen y configurarlas como se indica. Debe asignar al menos tres usuarios de prueba para cada grupo de servidores que desee probar. Si usa el método de autenticación Negotiate, también debe usar el cmdlet Set-CsTestUserCredential y el Shell de administración de Skype Empresarial Server para permitir que estas cuentas de prueba funcionen con las transacciones sintéticas. Para ello, ejecute un comando similar al siguiente (estos comandos suponen que se han creado las tres cuentas de usuario de Active Directory y que estas cuentas están habilitadas para Skype Empresarial Server):
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

Debe incluir no solo la dirección SIP, sino también el nombre de usuario y la contraseña. Si no incluye la contraseña, el cmdlet Set-CsTestUserCredential le pedirá que escriba esa información. El nombre de usuario se puede especificar mediante el formato nombre de dominio #A0 que se muestra en el bloque de código anterior.
  
Para comprobar que se crearon las credenciales de usuario de prueba, ejecute estos comandos desde el Shell de administración de Skype Empresarial Server:
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

Se devolverá información similar a esta para cada usuario:
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurar un nodo de monitor básico con las transacciones sintéticas predeterminadas

Una vez creados los usuarios de prueba, puede crear un nodo de monitor mediante un comando similar al siguiente:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

Este comando crea un nuevo nodo de monitor que usa la configuración predeterminada y ejecuta el conjunto predeterminado de transacciones sintéticas. El nuevo nodo de monitor también usa los usuarios de prueba watcher1@litwareinc.com, watcher2@litwareinc.com y watcher3@litwareinc.com. Si el nodo de monitor usa autenticación TrustedServer, las tres cuentas de prueba pueden ser cuentas de usuario válidas habilitadas para Active Directory y Skype Empresarial Server. Si el nodo de monitor usa el método de autenticación Negotiate, estas cuentas de usuario también deben estar habilitadas para el nodo de monitor mediante el cmdlet Set-CsTestUserCredential usuario.
  
Para validar que la detección automática del grupo de destino para iniciar sesión está configurada correctamente en lugar de dirigirse a un grupo directamente, siga estos pasos en su lugar:
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Configurar pruebas extendidas

Si desea habilitar la prueba rtc, que comprueba la conectividad con la red telefónica conmutada, debe realizar una configuración adicional al configurar el nodo de monitor. En primer lugar, debe asociar los usuarios de prueba con el tipo de prueba RTC ejecutando un comando similar al siguiente desde el Shell de administración de Skype Empresarial Server:
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Los resultados de este comando deben almacenarse en una variable. En este ejemplo, la variable se denomina $pstnTest. 
  
A continuación, puede usar el cmdlet **New-CsWatcherNodeConfiguration** para asociar el tipo de prueba (almacenado en la variable $pstnTest) a un grupo de Skype Empresarial Server. Por ejemplo, el siguiente comando crea una nueva configuración de nodo de monitor para el grupo de servidores atl-cs-001.litwareinc.com, agregando los tres usuarios de prueba creados anteriormente y agregando el tipo de prueba RTC:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Se producirá un error en el comando anterior si no ha instalado los archivos principales de Skype Empresarial Server y la base de datos RTCLocal en el equipo del nodo de monitor. 
  
Para probar varias directivas de voz, puede crear una prueba extendida para cada directiva mediante el cmdlet **New-CsExtendedTest.** Los usuarios proporcionados deben configurarse con las directivas de voz deseadas. Las pruebas extendidas se pasan al cmdlet **New-CsWatcherNodeConfiguration** mediante delimitadores de coma, como:
  
-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}
  
Dado que se llamó al cmdlet **New-CsWatcherNodeConfiguration** sin usar el parámetro Tests, solo se habilitarán las transacciones sintéticas predeterminadas (y la transacción sintética extendida especificada) para el nuevo nodo de monitor. Por lo tanto, el nodo de monitor probará los siguientes componentes:
  
- Registro
    
- Mensajería instantánea
    
- GroupIM
    
- P2PAV (sesiones de audio/vídeo punto a punto)
    
- AvConference (audio/conferencia)
    
- Presencia
    
- ABS (servicio de libreta de direcciones)
    
- ABWQ (servicio web de libreta de direcciones)
    
Los siguientes componentes no se probarán de forma predeterminada:
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (mensajería unificada de Exchange)
    
- JoinLauncher
    
- MCXP2PIM (mensajería instantánea de dispositivo móvil heredado)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- RTC (llamadas de puerta de enlace RTC, especificadas como prueba extendida)
    
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

Se producirá un error si ya se ha habilitado una o varias de estas pruebas (por ejemplo, DataConference) en el nodo de monitor. En este caso, aparecerá un mensaje de error similar al siguiente:
  
Set-CsWatcherNodeConfiguration: hay una secuencia de claves duplicada "DataConference" para la clave "urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName" o restricción de identidad única.
  
Cuando se produce este error, no se aplica ningún cambio. El comando debe volver a ejecutarse sin la prueba duplicada.
  
Para quitar una transacción sintética de un nodo de monitor, utilice el método Remove. Por ejemplo, este comando quita la prueba ABWQ de un nodo de monitor:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Puedes usar el método Replace para reemplazar todas las pruebas habilitadas actualmente por una o más pruebas nuevas. Por ejemplo, si desea que un nodo de monitor solo ejecute la prueba de mensajería instantánea, puede configurarlo mediante este comando:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Al ejecutar este comando, se deshabilitarán todas las transacciones sintéticas en el nodo de monitor especificado, excepto la mensajería instantánea.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Ver y probar la configuración de nodo de monitor

Si desea ver las pruebas que se asignaron a un nodo de monitor, use un comando similar a este:
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Este comando devolverá información similar a esta, en función de las transacciones sintéticas asignadas al nodo:
  
Registro de conferencia de datos persistentChatMessage de presencia de conferencias de mensajería instantánea de Mensajería instantánea P2PAV
> [!TIP]
> Para ver las transacciones sintéticas en orden alfabético, use este comando en su lugar: 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Para comprobar que se ha creado un nodo de monitor, escriba el siguiente comando desde el Shell de administración de Skype Empresarial Server:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Recibirá información similar a esta:
  
Identidad : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...} ExtendedTests : {TestUsers=IList<System.String>; Name=PSTN Test; Te...} TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Este comando probará cada nodo de monitor de la implementación y confirmará si se han completado las siguientes acciones:
  
- El rol de registrador necesario está instalado
    
- Se crea la clave del Registro necesaria (completada al ejecutar el cmdlet Set-CsWatcherNodeConfiguration)
    
- Los servidores ejecutan la versión correcta de Skype Empresarial Server
    
- Los puertos están configurados correctamente
    
- Los usuarios de prueba asignados tienen las credenciales necesarias
    
## <a name="managing-watcher-nodes"></a>Administración de nodos de monitor
<a name="testuser"> </a>

Además de modificar las transacciones sintéticas que se ejecutan en un nodo de monitor, también puede usar el cmdlet **Set-CsWatcherNodeConfiguration** para llevar a cabo otras dos tareas importantes: habilitar y deshabilitar el nodo de monitor y configurar el nodo de monitor para que use direcciones URL web internas o externas al ejecutar sus pruebas.
  
De forma predeterminada, los nodos de monitor están diseñados para ejecutar periódicamente todas sus transacciones sintéticas habilitadas. En ocasiones, sin embargo, es posible que desee suspender esas transacciones. Por ejemplo, si el nodo de monitor está desconectado temporalmente de la red, no hay ninguna razón para ejecutar las transacciones sintéticas. Sin conectividad de red, se producirá un error en las transacciones. Para deshabilitar temporalmente un nodo de monitor, ejecute un comando similar al siguiente desde el Shell de administración de Skype Empresarial Server:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Este comando deshabilitará la ejecución de transacciones sintéticas en el nodo de monitor atl watcher 001.litwareinc.com. Para volver a ejecutarlas, establezca la propiedad Enabled en True ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> La propiedad Enabled sirve para activar y desactivar nodos de monitor. En caso de que quiera eliminar un nodo de monitor permanentemente, use el cmdlet **Remove-CsWatcherNodeConfiguration**:
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Ese comando quita todas las opciones de configuración del nodo de monitor del equipo especificado, lo que impide que ese equipo ejecute automáticamente transacciones sintéticas. Sin embargo, el comando no desinstala los archivos de agente de System Center ni los archivos del sistema de Skype Empresarial Server.
  
De forma predeterminada, los nodos de monitor usan las direcciones URL web externas de una organización al realizar pruebas. Sin embargo, los nodos de monitor también se pueden configurar para usar las direcciones URL web internas de la organización. Esto permite a los administradores comprobar el acceso a la dirección URL de los usuarios ubicados dentro de la red perimetral. Para configurar un nodo de monitor para que use direcciones URL internas en lugar de externas, establezca la propiedad UseInternalWebURls en True ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

Restablecer esta propiedad al valor predeterminado de False ($False) hará que el monitor vuelva a usar las direcciones URL externas:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Instrucciones de configuración especiales para transacciones sintéticas
<a name="special_synthetictrans"> </a>

La mayoría de las transacciones sintéticas se pueden ejecutar en un nodo de monitor tal como está. En la mayoría de los casos, tan pronto como la transacción sintética se agrega a las opciones de configuración del nodo de monitor, el nodo de monitor puede empezar a usar esa transacción sintética durante los pases de prueba. Sin embargo, hay algunas transacciones sintéticas que requieren instrucciones de configuración especiales, como se describe en las secciones siguientes.
  
### <a name="data-conferencing-synthetic-transaction"></a>Transacción sintética de conferencia de datos

Si el equipo del nodo de monitor se encuentra fuera de la red perimetral, probablemente no podrá ejecutar la transacción sintética de conferencia de datos a menos que primero deshabilite la configuración de proxy de Explorador de Internet de Windows Internet Explorer® para la cuenta de servicio de red mediante los siguientes pasos:
  
1. En el equipo del nodo de monitor, haga clic en Inicio **,** todos los **programas,** accesorios **,** haga clic con el botón secundario en Símbolo del sistema **y,** a continuación, haga clic **en Ejecutar como administrador.**
    
2. En la ventana de la consola, escriba el siguiente comando y, a continuación, presione ENTRAR. 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

Verá el siguiente mensaje en la ventana de comandos:
  
BITSAdmin está en desuso y no se garantiza que esté disponible en versiones futuras de Windows. Las herramientas de administración para el servicio BITS ahora se proporcionan mediante cmdlets de PowerShell de BITS.
  
Configuración de proxy de Internet para la cuenta NetworkService establecida en NO_PROXY. 
  
(conexión = predeterminada)
  
Este mensaje indica que ha deshabilitado la configuración de proxy de Internet Explorer para la cuenta de servicio de red.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Transacción sintética de mensajería unificada de Exchange

La transacción sintética de mensajería unificada (UM) de Exchange comprueba que los usuarios de prueba pueden conectarse a cuentas de correo de voz que están en Exchange.
  
Los usuarios de prueba tendrán que estar preconfigurados con cuentas de correo de voz. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Transacción sintética de chat persistente

Para usar la transacción sintética de chat persistente, primero debe crear un canal y conceder a los usuarios de prueba permisos para usarlo.
  
Puede usar la transacción sintética de chat persistente para configurar este canal: 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Debe ejecutar esta tarea de configuración desde dentro de la empresa:
  
- Si se ejecuta desde un equipo que no es servidor, el usuario que ejecuta el cmdlet debe ser miembro del rol CsPersistentChatAdministrators para Role-Based Access Control (RBAC).
    
- Si se ejecuta desde el propio servidor, el usuario que ejecuta el cmdlet debe ser miembro del grupo RTCUniversalServerAdmins.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Transacción sintética de llamada punto a punto rtc

La Test-CsPstnPeerToPeerCall sintética comprueba la capacidad de realizar y recibir llamadas a través de una red telefónica conmutada (RTC).
  
Para ejecutar esta transacción sintética, debe configurar:
  
- Dos usuarios de prueba habilitados para UC (un autor de llamada y un receptor).
    
- Números de llamada directa a la extensión (DID) de cada cuenta de usuario.
    
- Directivas VoIP y rutas de voz que permiten que las llamadas al número del receptor lleguen a la puerta de enlace RTC.
    
- Una puerta de enlace RTC que acepta llamadas y medios que enrutarán las llamadas de vuelta al grupo de servidores principal de un receptor, en función del número marcado.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Transacción sintética del almacén de contactos unificado

La transacción sintética del almacén de contactos unificado comprueba la capacidad de Skype Empresarial Server para recuperar contactos en nombre de un usuario de Exchange.
  
Para ejecutar esta transacción, se deben cumplir las siguientes condiciones:
  
- Lyss-Exchange la autenticación de servidor a servidor debe configurarse.
    
- Los usuarios de prueba deben tener un buzón de Exchange válido.
    
Una vez que se cumplen estas condiciones, puede ejecutar el siguiente cmdlet Windows PowerShell para migrar las listas de contactos de los usuarios de prueba a Exchange:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

Las listas de contactos de usuario de prueba pueden tardar algún tiempo en migrarse a Exchange. Para supervisar el progreso de la migración, se puede ejecutar la misma línea de comandos sin la marca -Setup:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Esta línea de comandos se completará correctamente una vez completada la migración.
  
### <a name="xmpp-synthetic-transaction"></a>Transacción sintética XMPP

La transacción sintética de mensajería instantánea extensible de mensajería y presencia (XMPP) requiere que configure la característica XMPP con uno o más dominios federados.
  
Para habilitar la transacción sintética XMPP, debe proporcionar un parámetro XmppTestReceiverMailAddress con una cuenta de usuario en un dominio XMPP enrutable. Por ejemplo:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

En este ejemplo, debe existir una regla de Skype Empresarial Server para enrutar mensajes litwareinc.com una puerta de enlace XMPP.

> [!NOTE]
> Las puertas de enlace XMPP y los servidores proxy estaban disponibles en Skype Empresarial Server 2015, pero ya no son compatibles con Skype Empresarial Server 2019. Consulte [Migración de la federación XMPP](../migration/migrating-xmpp-federation.md) para obtener más información.
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Transacción sintética del servidor de interoperabilidad de vídeo (VIS)

La transacción sintética del servidor de interoperabilidad de vídeo (VIS) requiere que descargue e instale los archivos de compatibilidad con[ transacciones ](https://www.microsoft.com/download/details.aspx?id=46921)sintéticas (VISSTSupportPackage.msi). 
  
Para instalar VISSTSupportPackage.msi asegúrese de que las dependencias (en Requisitos del sistema) del msi ya están instaladas. Ejecute VISSTSupportPackage.msi para realizar una instalación sencilla. El archivo .msi instala todos los archivos en la siguiente ruta de acceso: "%ProgramFiles%\VIS Synthetic Transaction Support Package".
  
Para obtener más información sobre cómo ejecutar la transacción sintética vis, consulte la documentación del cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV.](https://technet.microsoft.com/library/dn985894.aspx)
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Cambio de la frecuencia de ejecución de las transacciones sintéticas
<a name="special_synthetictrans"> </a>

De forma predeterminada, las transacciones sintéticas se ejecutarán con los usuarios configurados cada 15 minutos. Las transacciones sintéticas se ejecutan secuencialmente dentro de un conjunto de usuarios para evitar que dos transacciones sintéticas entren en conflicto. Se necesita un intervalo más largo para proporcionar tiempo para que se completen todas las transacciones sintéticas.
  
Si es conveniente ejecutar transacciones sintéticas con más frecuencia, el número de transacciones sintéticas que se ejecutan con un conjunto determinado de usuarios debe reducirse para que las pruebas se puedan completar en el intervalo de tiempo deseado con algún búfer para retrasos ocasionales en la red. Si es conveniente ejecutar más transacciones sintéticas, cree más conjuntos de usuarios para ejecutar transacciones sintéticas adicionales.
  
Para cambiar la frecuencia con la que se ejecutan las transacciones sintéticas, siga estos pasos:
  
1. Abra System Center Operations Manager. Haga clic en la sección Creación. Sección Hacer clic en Reglas (en Creación)
    
2. En la sección Reglas, busque la regla con el nombre "Main Synthetic Transaction Runner Performance Collection Rule" (Regla de recopilación de rendimiento del ejecutor de transacciones sintéticas principal)
    
3. Haga clic con el botón secundario en la regla y, a continuación, seleccione Invalidar la regla y, a continuación, seleccione "Para todos los objetos de clase: Pool Watcher"
    
4. En la ventana Propiedades de reemplazo, seleccione El nombre del parámetro "Frecuencia" y establezca el valor de invalidación en el valor deseado.
    
5. En la misma ventana, seleccione el módulo de administración al que debe aplicarse este reemplazo.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Uso de registro enriquecido para transacciones sintéticas
<a name="special_synthetictrans"> </a>

Las transacciones sintéticas resultan extremadamente útiles para ayudar a identificar problemas con el sistema. Por ejemplo, el cmdlet Test-CsRegistration podría alertar a los administradores sobre el hecho de que los usuarios tenían dificultades para registrarse en Skype Empresarial Server. Sin embargo, es posible que se necesiten detalles adicionales para determinar la causa real de un error.
  
Por este motivo, las transacciones sintéticas proporcionan un registro enriquecido. Con el registro enriquecido, para cada actividad que realiza una transacción sintética, se registra la siguiente información:
  
- Hora en que se inició la actividad.
    
- Hora en que finalizó la actividad.
    
- La acción que se realizó (por ejemplo, crear, unirse o salir de una conferencia, iniciar sesión en Skype Empresarial Server, enviar un mensaje instantáneo).
    
- Mensajes de error o advertencias detalladas o informativas generadas cuando se ejecutó la actividad
    
- Mensajes de registro SIP.
    
- Registros de excepción o códigos de diagnóstico generados cuando se ejecutó la actividad.
    
- Resultado neto de la ejecución de la actividad.
    
Esta información se genera automáticamente cada vez que se ejecuta una transacción sintética, pero no se muestra ni se guarda automáticamente en un archivo de registro. Si ejecuta manualmente una transacción sintética, puede usar el parámetro OutLoggerVariable para especificar una variable Windows PowerShell en la que se almacenará la información. Desde allí, tiene la opción de usar uno de los dos métodos para guardar o ver mensajes de error en el registro enriquecido en formato XML o HTML. 
  
Para recuperar la información de solución de problemas, especifique el parámetro OutLoggerVariable, seguido del nombre de variable que elija:
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> : no antefies el nombre de la variable con el carácter $. Use un nombre de variable como RegistrationTest (no $RegistrationTest). 
  
Cuando ejecute este comando, verá un resultado similar al siguiente:
  
Fqdn de destino : atl-cs-001.litwareinc.com resultado : latencia de error : 00:00:00 Mensaje de error : Esta máquina no tiene ningún certificado asignado. Diagnóstico: puede obtener acceso a información mucho más detallada sobre este error que solo el mensaje de error que se muestra aquí. Para obtener acceso a esta información en formato HTML, use un comando similar a este para guardar la información almacenada en la variable RegistrationTest en un archivo HTML:
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Del mismo modo, puede usar el método ToXML() para guardar los datos en un archivo XML:
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Puede ver estos archivos mediante Windows Internet Explorer, Microsoft Visual Studio o cualquier otra aplicación capaz de abrir archivos HTML/XML.
  
Las transacciones sintéticas que se ejecutan desde dentro de System Center Operations Manager generarán automáticamente estos archivos de registro para los errores. Estos registros no se generarán si se produce un error en la ejecución antes de que PowerShell de Skype Empresarial Server pueda cargar y ejecutar la transacción sintética. 
  
> [!IMPORTANT]
> De forma predeterminada, Skype Empresarial Server guarda los archivos de registro en una carpeta que no se comparte. Para que estos registros estén accesibles fácilmente, debe compartir esta carpeta. Por ejemplo: \\ atl-watcher-001.litwareinc.com\WatcherNode. 
