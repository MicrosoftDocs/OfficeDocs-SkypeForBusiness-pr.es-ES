---
title: Configurar los usuarios y la configuración de prueba de nodos de monitor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 'Resumen: configurar las cuentas de usuario de prueba y la configuración de nodo de monitor para las transacciones sintéticas de Skype empresarial Server.'
ms.openlocfilehash: 8b586cf4c1d003bb54afa050469a10eee8d113e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005955"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>Configurar los usuarios y la configuración de prueba de nodos de monitor
 
**Resumen:** Configurar las cuentas de usuario de prueba y la configuración de nodo de monitor para las transacciones sintéticas de Skype empresarial Server.
  
Después de configurar el equipo que funcionará como nodo de monitor, debe hacer lo siguiente:
  
1. [Configure las cuentas de usuario de prueba](test-users-and-settings.md#testuser) que deben usar estos nodos de monitor. Si usa el método de autenticación Negotiate, también debe usar el cmdlet **Set-CsTestUserCredential** para habilitar estas cuentas de prueba para su uso en el nodo de monitor.
    
2. Actualizar las opciones de configuración del nodo de monitor.
    
## <a name="configure-test-user-accounts"></a>Configurar cuentas de usuario de prueba
<a name="testuser"> </a>

Las cuentas de prueba no necesitan representar a personas reales, pero deben ser cuentas de Active Directory válidas. Además, estas cuentas deben estar habilitadas para Skype empresarial Server, deben tener direcciones SIP válidas y deben estar habilitadas para telefonía IP empresarial (para usar la transacción sintética test-CsPstnPeerToPeerCall). 
  
Si usa el método de autenticación TrustedServer, todo lo que debe hacer es asegurarse de que existen estas cuentas y configurarlas tal y como se indica. Debe asignar al menos dos usuarios de prueba para cada grupo de servidores que quiera probar. Si usa el método de autenticación Negotiate, también debe usar el cmdlet Set-CsTestUserCredential y el shell de administración de Skype empresarial Server para habilitar estas cuentas de prueba para que funcionen con las transacciones sintéticas. Para ello, ejecute un comando similar al siguiente (estos comandos suponen que las dos cuentas de usuario de Active Directory se han creado y que estas cuentas están habilitadas para Skype empresarial Server):
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

Debe incluir no solo la dirección SIP, sino también el nombre de usuario y la contraseña. Si no incluye la contraseña, el cmdlet Set-CsTestUserCredential le pedirá que escriba la información. El nombre de usuario se puede especificar mediante el formato de nombre de dominio\nombre de usuario que se muestra en el bloque de código anterior.
  
Para comprobar que se han creado las credenciales de usuario de prueba, ejecute estos comandos desde el shell de administración de Skype empresarial Server:
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

Se devolverá información similar a la siguiente para cada usuario:
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System. Security. SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurar un nodo de monitor básico con las transacciones sintéticas predeterminadas

Una vez creados los usuarios de prueba, puede crear un nodo de monitor con un comando similar al siguiente:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

Este comando crea un nuevo nodo de monitor que usa la configuración predeterminada y ejecuta el conjunto predeterminado de transacciones sintéticas. El nuevo nodo de monitor también usa los usuarios de prueba watcher1@litwareinc.com y watcher2@litwareinc.com. Si el nodo de monitor usa la autenticación TrustedServer, las dos cuentas de prueba pueden ser cualquier cuenta de usuario válida habilitada para Active Directory y Skype empresarial Server. Si el nodo de monitor usa el método de autenticación Negotiate, estas cuentas de usuario también deben estar habilitadas para el nodo de monitor mediante el cmdlet Set-CsTestUserCredential.
  
Para validar que la detección automática del grupo de servidores de destino en el que iniciar sesión está correctamente configurada en lugar de dirigirse directamente a un grupo de servidores, siga estos pasos en su lugar:
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>Configurar pruebas extendidas

Si desea habilitar la prueba de RTC, que comprueba la conectividad con la red telefónica pública conmutada, debe realizar una configuración adicional al configurar el nodo de monitor. En primer lugar, debe asociar los usuarios de prueba al tipo de prueba RTC ejecutando un comando similar al siguiente desde el shell de administración de Skype empresarial Server:
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> Los resultados de este comando deben almacenarse en una variable. En este ejemplo, la variable se denomina $pstnTest. 
  
A continuación, puede usar el cmdlet **New-CsWatcherNodeConfiguration** para asociar el tipo de prueba (almacenado en la variable $pstnTest) a un grupo de servidores de Skype empresarial Server. Por ejemplo, el siguiente comando crea una nueva configuración de nodo de monitor para el grupo atl-cs-001.litwareinc.com, agregando los dos usuarios de prueba creados anteriormente y agregando el tipo de prueba de RTC:
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

Se producirá un error en el comando anterior si no ha instalado los archivos principales de Skype empresarial Server y la base de datos RTCLocal en el equipo del nodo de monitor. 
  
Para probar varias directivas de voz, puede crear una prueba extendida para cada directiva con el cmdlet **New-CsExtendedTest** . Los usuarios proporcionados deben configurarse con las directivas de voz deseadas. Las pruebas extendidas se pasan al cmdlet **New-CsWatcherNodeConfiguration** mediante delimitadores de coma, como:
  
-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}
  
Debido a que se ha llamado al cmdlet **New-CsWatcherNodeConfiguration** sin usar el parámetro tests, solo se habilitarán las transacciones sintéticas predeterminadas (y la transacción sintética extendida especificada) para el nuevo nodo de monitor. Por lo tanto, el nodo de monitor probará los siguientes componentes:
  
- Registro
    
- Mensajería instantánea
    
- GroupIM
    
- P2PAV (sesiones de audio/vídeo punto a punto)
    
- AvConference (audio/conferencia)
    
- Presencia
    
- ABS (servicio de libreta de direcciones)
    
- ABWQ (servicio web de libreta de direcciones)
    
Los siguientes componentes no se probarán de manera predeterminada:
  
- Asconferencia
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (mensajería unificada de Exchange)
    
- JoinLauncher
    
- MCXP2PIM (mensajería instantánea de dispositivos móviles heredados)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- RTC (llamadas de puerta de enlace RTC, especificadas como una prueba extendida)
    
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

Se producirá un error si ya se ha habilitado una o varias de estas pruebas (por ejemplo, Conference) en el nodo de monitor. En este caso, aparecerá un mensaje de error similar al siguiente:
  
Set-CsWatcherNodeConfiguration: hay una secuencia de teclas duplicada ' Conference ' para la clave ' urn: Schema: Microsoft. RTC. Management. Settings. WatcherNode. 2010: nombrePrueba ' o la restricción de identidad única.
  
Cuando se produce este error, no se aplica ningún cambio. El comando debe volver a ejecutarse con la prueba duplicada quitada.
  
Para quitar una transacción sintética de un nodo de monitor, use el método Remove. Por ejemplo, este comando quita la prueba ABWQ de un nodo de monitor:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Puede usar el método replace para reemplazar todas las pruebas habilitadas actualmente con una o más pruebas nuevas. Por ejemplo, si desea que un nodo de monitor solo ejecute la prueba de mi, puede configurarlo con este comando:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

Al ejecutar este comando, se deshabilitarán todas las transacciones sintéticas del nodo de monitor especificado, excepto para la mensajería instantánea.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>Ver y probar la configuración de nodo de monitor

Si desea ver las pruebas que se asignaron a un nodo de monitor, use un comando similar a este:
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

Este comando devolverá información similar a la siguiente, según las transacciones sintéticas que se hayan asignado al nodo:
  
Inscripción de mensajería instantánea GroupIM P2PAV AvConference de presencia PersistentChatMessage de la Conferencia
> [!TIP]
> Para ver las transacciones sintéticas en orden alfabético, use este comando en su lugar: 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

Para comprobar que se ha creado un nodo de monitor, escriba el siguiente comando desde el shell de administración de Skype empresarial Server:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

Obtendrá una información similar a la siguiente:
  
Identidad: atl-cs-001.litwareinc.com <br/>
TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}<br/>
ExtendedTests: {TestUsers = IList<System. String>; Name = prueba RTC; Te...}<br/>
TargetFqdn: atl-cs-001.litwareinc.com<br/>
PortNumber: 5061<br/>

Para comprobar que el nodo de monitor se ha configurado correctamente, escriba el siguiente comando desde el shell de administración de Skype empresarial Server:
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

Este comando probará cada nodo de monitor de la implementación y confirmará si se han completado las siguientes acciones:
  
- El rol de registrador necesario está instalado.
    
- Se crea la clave del registro necesaria (se completa cuando se ejecutó el cmdlet Set-CsWatcherNodeConfiguration).
    
- Los servidores ejecutan la versión correcta de Skype empresarial Server.
    
- Los puertos están configurados correctamente.
    
- Los usuarios de prueba asignados tienen las credenciales necesarias.
    
## <a name="managing-watcher-nodes"></a>Administración de nodos de monitor
<a name="testuser"> </a>

Además de modificar las transacciones sintéticas que se ejecutan en un nodo de monitor, también puede usar el cmdlet **set-CsWatcherNodeConfiguration** para llevar a cabo otras dos tareas importantes: habilitar y deshabilitar el nodo de monitor y configurar el nodo de monitor para usar direcciones URL web internas o direcciones URL web externas al ejecutar sus pruebas.
  
De forma predeterminada, los nodos de monitor están diseñados para ejecutar periódicamente todas sus transacciones sintéticas habilitadas. Sin embargo, en ocasiones, es posible que desee suspender esas transacciones. Por ejemplo, si el nodo de monitor se desconecta temporalmente de la red, no hay ninguna razón para ejecutar las transacciones sintéticas. Sin la conectividad de red, se producirá un error en esas transacciones. Para deshabilitar temporalmente un nodo de monitor, ejecute un comando similar al siguiente desde el shell de administración de Skype empresarial Server:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

Este comando deshabilitará la ejecución de transacciones sintéticas en el nodo de monitor ATL Watcher 001.litwareinc.com. Para volver a ejecutarlas, establezca la propiedad Enabled en True ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> La propiedad Enabled sirve para activar y desactivar nodos de monitor. En caso de que quiera eliminar un nodo de monitor permanentemente, use el cmdlet **Remove-CsWatcherNodeConfiguration**:
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

Este comando quita todas las opciones de configuración de nodo de monitor del equipo especificado, lo que impide que el equipo ejecute automáticamente transacciones sintéticas. Sin embargo, el comando no desinstala los archivos del agente de System Center ni los archivos del sistema de Skype empresarial Server.
  
De forma predeterminada, los nodos de monitor usan direcciones URL de web externas de la organización al realizar las pruebas. Sin embargo, los nodos de monitor también se pueden configurar para usar las direcciones URL web internas de la organización. Esto permite a los administradores comprobar el acceso a direcciones URL para los usuarios que se encuentran dentro de la red perimetral. Para configurar un nodo de monitor para que use direcciones URL internas en lugar de direcciones URL externas, establezca la propiedad UseInternalWebURls en true ($True):
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

Restablecer esta propiedad en el valor predeterminado de false ($False) hará que el monitor vuelva a usar las direcciones URL externas:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>Instrucciones de configuración especiales para transacciones sintéticas
<a name="special_synthetictrans"> </a>

La mayoría de las transacciones sintéticas se pueden ejecutar en un nodo de monitor tal cual. En la mayoría de los casos, en cuanto la transacción sintética se agrega a las opciones de configuración de nodo de monitor, el nodo de monitor puede empezar a usar esa transacción sintética durante la prueba. Sin embargo, hay algunas transacciones sintéticas que requieren instrucciones de configuración especiales, como se describe en las secciones siguientes.
  
### <a name="data-conferencing-synthetic-transaction"></a>Transacción sintética de conferencia de datos

Si el equipo de nodo de monitor está ubicado fuera de la red perimetral, es probable que no pueda ejecutar la transacción sintética de conferencia de datos a menos que deshabilite primero la configuración de Windows Internet Explorer® el proxy de explorador de Internet de la red. Cuenta de servicio; para ello, siga estos pasos:
  
1. En el equipo nodo de monitor, haga clic en **Inicio**, en **todos los programas**, en **accesorios**, haga clic con el botón secundario en **símbolo del sistema**y, a continuación, haga clic en **Ejecutar como administrador**.
    
2. En la ventana de la consola, escriba el siguiente comando y, a continuación, presione Entrar. 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    Verá el siguiente mensaje mostrado en la ventana de comandos:

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    Este mensaje indica que ha deshabilitado la configuración de proxy de Internet Explorer para la cuenta de servicio de red.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Transacción sintética de mensajería unificada de Exchange

La transacción sintética de mensajería unificada (UM) de Exchange comprueba que los usuarios de prueba se pueden conectar a cuentas de correo de voz hospedadas en Exchange.
  
Los usuarios de prueba deberán preconfigurarse con cuentas de correo de voz. 
  
### <a name="persistent-chat-synthetic-transaction"></a>Transacción sintética de chat persistente

Para usar la transacción sintética de chat persistente, primero debe crear un canal y conceder a los usuarios de prueba permisos para usarlos.
  
Puede usar la transacción sintética de chat persistente para configurar este canal: 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

Debe ejecutar esta tarea de configuración debe ejecutarse desde dentro de la empresa:
  
- Si se ejecuta desde un equipo que no sea un servidor, el usuario que ejecuta el cmdlet debe ser miembro del rol CsPersistentChatAdministrators para el control de acceso basado en roles (RBAC).
    
- Si se ejecuta desde el propio servidor, el usuario que ejecuta el cmdlet debe ser miembro del grupo RTCUniversalServerAdmins.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>Transacción sintética de llamada punto a punto de RTC

La transacción sintética de test-CsPstnPeerToPeerCall comprueba la capacidad de realizar y recibir llamadas a través de una red telefónica conmutada (RTC).
  
Para ejecutar esta transacción sintética, debe configurar:
  
- Dos usuarios de prueba habilitados para UC (una persona que llama y un receptor).
    
- Números de llamada directa a la extensión (DID) de cada cuenta de usuario.
    
- Directivas de VoIP y rutas de voz que permiten llamadas al número del receptor para llegar a la puerta de enlace RTC.
    
- Una puerta de enlace RTC que acepta llamadas y medios que redirigen las llamadas de vuelta al grupo de servidores principales de un receptor, en función del número marcado.
    
### <a name="unified-contact-store-synthetic-transaction"></a>Transacción sintética de almacén de contactos unificado

La transacción sintética de almacén de contactos unificado comprueba la capacidad de Skype empresarial Server para recuperar los contactos en nombre de un usuario de Exchange.
  
Para ejecutar esta transacción, se deben cumplir las siguientes condiciones:
  
- Se debe configurar la autenticación de Lyss-Exchange Server a Server.
    
- Los usuarios de prueba deben tener un buzón de Exchange válido.
    
Una vez que se cumplen estas condiciones, puede ejecutar el siguiente cmdlet de Windows PowerShell para migrar las listas de contactos de los usuarios de prueba a Exchange:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

La migración de las listas de contactos de los usuarios de prueba a Exchange puede tardar algún tiempo. Para supervisar el progreso de la migración, se puede ejecutar la misma línea de comandos sin la marca-Setup:
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

Esta línea de comandos se realizará correctamente una vez completada la migración.
  
### <a name="xmpp-synthetic-transaction"></a>Transacción sintética XMPP

La transacción sintética IM del protocolo extensible de mensajería y presencia (XMPP) requiere que configure la característica XMPP con uno o más dominios federados.
  
Para habilitar la transacción sintética XMPP, debe proporcionar un parámetro XmppTestReceiverMailAddress con una cuenta de usuario en un dominio XMPP enrutable. Por ejemplo:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

En este ejemplo, tendrá que existir una regla de Skype empresarial Server para enrutar los mensajes de litwareinc.com a una puerta de enlace XMPP.

> [!NOTE]
> Las puertas de enlace y los servidores proxy XMPP están disponibles en Skype empresarial Server 2015, pero ya no se admiten en Skype empresarial Server 2019. Consulte [migrar la Federación XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obtener más información. 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>Transacción sintética del servidor de interoperabilidad de vídeo (VIS)

La transacción sintética del servidor de interoperabilidad de vídeo (VIS) requiere que descargue e instale los archivos de compatibilidad de transacción sintética ([VISSTSupportPackage. msi](https://www.microsoft.com/download/details.aspx?id=46921)). 
  
Para instalar VISSTSupportPackage. msi, asegúrese de que las dependencias (en requisitos del sistema) para el MSI ya están instaladas. Ejecute VISSTSupportPackage. msi para realizar una instalación sencilla. El archivo. msi instala todos los archivos en la siguiente ruta de acceso: "paquete de compatibilidad con transacción sintética de%ProgramFiles%\VIS".
  
Para obtener más información sobre cómo ejecutar la transacción sintética VIS, consulte la documentación del cmdlet [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) .
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>Cambio de la frecuencia de ejecución para transacciones sintéticas
<a name="special_synthetictrans"> </a>

De forma predeterminada, las transacciones sintéticas se ejecutarán con los usuarios configurados cada 15 minutos. Las transacciones sintéticas se ejecutan secuencialmente en un conjunto de usuarios para evitar que dos transacciones sintéticas entren en conflicto entre sí. Se necesita un intervalo más largo para proporcionar tiempo para completar todas las transacciones sintéticas.
  
Si es deseable ejecutar transacciones sintéticas con más frecuencia, se debe reducir el número de transacciones sintéticas que se ejecutan con un conjunto determinado de usuarios, de modo que las pruebas puedan completarse en el intervalo de tiempo deseado con un búfer para retrasos en la red ocasionados. Si es conveniente ejecutar más transacciones sintéticas, cree más conjuntos de usuarios para ejecutar transacciones sintéticas adicionales.
  
Para cambiar la frecuencia con la que se ejecutan las transacciones sintéticas, siga estos pasos:
  
1. Abra System Center Operations Manager. Haga clic en sección de creación. Haga clic en la sección reglas (en creación).
    
2. En la sección reglas, busque la regla con el nombre "regla de recopilación de rendimiento del Ejecutor de transacciones sintéticas principales".
    
3. Haga clic con el botón secundario en la regla y seleccione reemplazos, seleccione invalidar la regla y, a continuación, seleccione "para todos los objetos de la clase: monitor de grupo".
    
4. En la ventana Propiedades de reemplazo, seleccione el nombre de parámetro "Frequency" y establezca el valor de invalidación en el valor deseado.
    
5. En la misma ventana, seleccione el módulo de administración en el que se debe aplicar esta invalidación.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>Uso de registro enriquecido para transacciones sintéticas
<a name="special_synthetictrans"> </a>

Las transacciones sintéticas resultan muy útiles para ayudar a identificar problemas con el sistema. Por ejemplo, el cmdlet test-CsRegistration podría avisar a los administradores del hecho de que los usuarios tenían problemas para registrarse con Skype empresarial Server. Sin embargo, es posible que se necesiten más detalles para determinar la causa real de un error.
  
Por este motivo, las transacciones sintéticas proporcionan un registro enriquecido. Con el registro enriquecido, para cada actividad que se consiga con una transacción sintética, se registra la siguiente información:
  
- Hora a la que se inició la actividad.
    
- Hora a la que finalizó la actividad.
    
- La acción que se ha realizado (por ejemplo, crear, unirse o abandonar una conferencia; iniciar sesión en Skype empresarial Server; enviar un mensaje instantáneo).
    
- Mensajes informativos, detallados, de advertencia o de error generados cuando se ejecutó la actividad.
    
- Mensajes de registro SIP.
    
- Códigos de diagnóstico o registros de excepción generados cuando se ejecutó la actividad.
    
- El resultado neto de la ejecución de la actividad.
    
Esta información se genera automáticamente cada vez que se ejecuta una transacción sintética, pero no se muestra ni se guarda automáticamente en un archivo de registro. Si ejecuta manualmente una transacción sintética, puede usar el parámetro OutLoggerVariable para especificar una variable de Windows PowerShell en la que se almacenará la información. Desde allí, tiene la opción de usar uno de estos dos métodos para guardar o ver los mensajes de error en el registro enriquecido, en formato XML o HTML. 
  
Para recuperar la información de solución de problemas, especifique el parámetro OutLoggerVariable seguido de un nombre de variable que elija:
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> Asegúrese de no anteponer el carácter $ al nombre de la variable. Use un nombre de variable como el (no $RegistrationTest). 
  
Cuando ejecute este comando, verá un resultado similar al siguiente:
  
FQDN de destino: resultado de atl-cs-001.litwareinc.com: latencia de error: 00:00:00 mensaje de error: este equipo no tiene ningún certificado asignado. Diagnóstico: puede obtener acceso a información mucho más detallada sobre este error que solo el mensaje de error que se muestra aquí.

Para tener acceso a esta información en formato HTML, use un comando similar al siguiente para guardar la información almacenada en la variable el en un archivo HTML:
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

Del mismo modo, puede usar el método ToXML() para guardar los datos en un archivo XML:
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Puede ver estos archivos con Windows Internet Explorer, Microsoft Visual Studio o cualquier otra aplicación capaz de abrir archivos HTML/XML.
  
Las transacciones sintéticas que se ejecutan desde dentro de System Center Operations Manager generarán automáticamente estos archivos de registro para los errores. Estos registros no se generarán si se produce un error en la ejecución antes de que Skype empresarial Server PowerShell pueda cargar y ejecutar la transacción sintética. 
  
> [!IMPORTANT]
> De forma predeterminada, Skype empresarial Server guarda los archivos de registro en una carpeta que no está compartida. Para que estos registros sean accesibles fácilmente, debe compartir esta carpeta. Por ejemplo: \\ATL-Watcher-001. litwareinc. com\WatcherNode. 
