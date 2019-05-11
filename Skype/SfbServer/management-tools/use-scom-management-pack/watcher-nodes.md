---
title: Instalar y configurar nodos de monitor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 'Resumen: Instale y configure los nodos de monitor para Skype para las transacciones sintéticas Business Server.'
ms.openlocfilehash: 5a4733175352af8c18cab20f7f8649c53275be7f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904205"
---
# <a name="install-and-configure-watcher-nodes"></a>Instalar y configurar nodos de monitor
 
**Resumen:** Instalar y configurar los nodos de monitor para Skype para las transacciones sintéticas Business Server.
  
Nodos de monitor son equipos que ejecutan periódicamente Skype para las transacciones sintéticas Business Server. Las transacciones sintéticas son los cmdlets de Windows PowerShell que compruebe que los escenarios de usuario clave, como la capacidad para iniciar sesión o para intercambiar mensajes instantáneos, funcionan según lo previsto. Para Skype para Business Server 2015, System Center Operations Manager puede ejecutar las transacciones sintéticas que se muestra en la tabla siguiente, que incluye tres tipos de transacción:
  
- **Valor predeterminado** Transacciones sintéticas que un nodo de monitor se ejecuta de forma predeterminada. Cuando se crea un nuevo nodo de monitor, puede especificar qué sintéticas transacciones se ejecutará en ese nodo. (Que es el propósito de los parámetros de prueba que usa el cmdlet New-CsWatcherNodeConfiguration). Si no usa el parámetro de pruebas cuando se crea el nodo de monitor, se ejecutará automáticamente todas las transacciones sintéticas de forma predeterminada y no se ejecutará ninguna de las transacciones sintéticas Non-default. Por ejemplo, esto significa que el nodo de monitor se configurarán para ejecutar la prueba Test-CsAddressBookService, pero no se configurarán para ejecutar la prueba Test-CsExumConnectivity.
    
- **No predeterminado** Pruebas de nodos de monitor no se ejecute de forma predeterminada. (Para obtener información detallada, vea la descripción del tipo de forma predeterminada). Sin embargo, se puede habilitar el nodo de monitor para ejecutar cualquiera de las transacciones sintéticas Non-default. Esto se puede hacer cuando se crea el nodo de monitor (mediante el cmdlet New-CsWatcherNodeConfiguration) o en cualquier momento después de crear dicho nodo. Tenga en cuenta que muchas de las transacciones sintéticas que no son predeterminadas requieren pasos de configuración adicionales. Para obtener más información sobre estos pasos, consulte las instrucciones de configuración especiales para Las transacciones sintéticas. Para obtener más detalles acerca de estos pasos, consulte [Las instrucciones de configuración especiales para transacciones sintéticas ](test-users-and-settings.md#special_synthetictrans).
    
- **Extendido** Un tipo especial de transacciones sintéticas Non-default. A diferencia de otras transacciones sintéticas, Extended pruebas se pueden ejecutar varias veces durante cada paso. Esto es útil cuando se comprueba el comportamiento, como varias rutas de voz de (RTC) de la red telefónica conmutada pública para un grupo de servidores. Puede configurar esto agregando varias instancias de una prueba extendida a un nodo de monitor.
    
Para obtener más información sobre el proceso para agregar otras transacciones sintéticas a un nodo de monitor, consulte [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans). También puede usar Skype para Business Server Management Shell para quitar las transacciones sintéticas de un nodo de monitor.
  
Las transacciones sintéticas disponibles para los nodos de monitor son las siguientes:
  
|**Nombre del cmdlet (nombre de la prueba)**|**Descripción**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Confirma que los usuarios pueden buscar los usuarios que no están en su lista de contactos.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Confirma que los usuarios pueden buscar los usuarios que no están en su lista de contactos a través de HTTP.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Confirma que los usuarios pueden crear conferencias de audio/vídeo y participar en ellas.  <br/> |
|Test-CsGroupIM (conferencia de mensajería instantánea)  <br/> |Confirma que los usuarios pueden enviar mensajes instantáneos durante las conferencias y participar en conversaciones de mensajes instantáneos con tres o más personas.  <br/> |
|Test-CsIM (P2P IM)  <br/> |Confirma que los usuarios pueden enviar mensajes instantáneos punto a punto.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Confirma que los usuarios pueden realizar llamadas de audio de punto a punto (solo señalización).  <br/> |
|Test-CsPresence (Presence)  <br/> |Confirma que los usuarios pueden ver la presencia de los demás usuarios.  <br/> |
|Test-CsRegistration (Registration)  <br/> |Confirma que los usuarios pueden iniciar sesión en Skype para la empresa.  <br/> |
|Test-CsPstnPeerToPeerCall (RTC)  <br/> |Confirma que los usuarios pueden hacer y recibir llamadas con gente ajena a la empresa (números de RTC).  <br/> |
|Test-CsASConference (ASConference)  <br/> |Confirma que los usuarios pueden crear conferencias de uso compartido de aplicaciones y participar en ellas.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Confirma que los servidores perimetrales A/V pueden aceptar conexiones para las llamadas de punto a punto y las llamadas de conferencia.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Confirma que los usuarios pueden participar en una conferencia de colaboración de datos (una reunión en línea que engloba actividades como pizarras y sondeos).  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma que los usuarios pueden marcar números de teléfono para participar en conferencias.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma que los usuarios pueden marcar números de teléfono para participar en conferencias.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Confirma que un usuario puede conectarse a Exchange mensajería unificada (UM).  <br/> |
|Test-CsGroupIM - TestJoinLauncher (JoinLauncher)  <br/> |Confirma que los usuarios pueden crear reuniones programadas y unirse a ellas (a través de un vínculo de dirección web).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Confirma que los usuarios de dispositivos móviles pueden registrarse y enviar mensajes instantáneos.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Confirma que el servidor de interoperabilidad vídeo es de seguridad y puede controlar las conexiones entrantes a través de un tronco SIP vídeo.  <br/> **Nota:** Compatibilidad con MCX para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Confirma que los usuarios pueden intercambiar mensajes mediante el servicio de chat persistente.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Confirma que los usuarios pueden unirse a conferencias a través de la web.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Confirma que se puede acceder a los contactos de un usuario a través del almacén de contactos unificados. El almacén de contactos unificados proporciona una manera para que los usuarios mantener un único conjunto de contactos a los que se puede tener acceso mediante el uso de Skype para Business Server 2015, mensajería de Outlook y el cliente de colaboración, y Outlook Web Access.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Confirma que se pueden enviar mensajes instantáneos por la puerta de enlace XMPP (protocolo extensible de mensajería y presencia).  <br/> Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype para Business Server 2015, pero ya no se admiten en Skype para Business Server 2019.  |

No es necesario instalar nodos de monitor para usar System Center Operations Manager. Si no instala estos nodos, puede seguir obtener alertas en tiempo real de Skype para los componentes de Business Server 2015 siempre que se produce un problema. (El componente y el módulo de administración de usuario no utiliza nodos de monitor.) Sin embargo, los nodos de monitor son necesarios si desea supervisar los escenarios de extremo a otro mediante el paquete de administración de supervisión activa.
  
> [!NOTE]
> Los administradores pueden ejecutar transacciones sintéticas de forma manual, sin usar o instalar Operations Manager. Según el tamaño de su Skype para la implementación de servidor empresarial, las transacciones sintéticas pueden usar una gran cantidad de tiempo de procesador y memoria del equipo. Por este motivo, recomendamos usar un equipo dedicado como nodo de monitor. Por ejemplo, no debe configurar un Skype para profesionales Front-End Server para que actúe como un nodo de monitor. Nodos de monitor deben cumplir los mismos requisitos básicos de hardware como cualquier otro equipo en su Skype de topología de servidores de negocio. 
  
> [!NOTE]
> Un nodo de Monitor de Lync Server 2013 heredado no se pueden combinar en el mismo equipo como un Skype para el nodo de monitor Business Server 2015 debido a que los archivos de sistema principales para Lync Server 2013 y Skype para Business Server 2015 no se puede instalar en el mismo equipo. Sin embargo, Skype para nodos de monitor Business Server 2015 simultáneamente puede supervisar Skype para Business Server 2015 y Lync Server 2013. Las transacciones sintéticas predeterminadas son compatibles con ambas versiones de producto. 
  
Nodos de Monitor de Lync Server 2013 se pueden implementar dentro o fuera de una empresa para ayudar a comprobar:
  
- La conectividad con los grupos de servidores de usuarios de la empresa.
    
- La conectividad a través de redes perimetrales de los usuarios remotos que trabajan fuera de la empresa.
    
- La conectividad con aplicaciones de sucursal.
    
- Conectividad con Lync Server 2013 dentro de la empresa y a través de redes perimetrales.
    
Para ayudar a simplificar la administración, existen distintas opciones de autenticación desde dentro y fuera de la empresa. Para obtener más información, consulte [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).
  
Si desea configurar un equipo para que actúe como un nodo de monitor, primero debe completar los siguientes requisitos previos: 
  
- Instalación de System Center Operations Manager e importar el Skype para los paquetes de administración empresarial Server 2015. En primer lugar también debe comprobar que el equipo de nodo de monitor cumple todos los requisitos previos para la instalación de Skype para Business Server 2015.
    
- Instale los elementos siguientes en el equipo que actúa como nodo de monitor:
    
  - La versión completa de .NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Una vez que se cumplan todos los requisitos previos, puede proceder a configurar el nodo de monitor siguiendo siga estos pasos:
  
1. Instale el Skype para archivos de Business Server 2015 principales en el equipo de nodo de monitor.
    
2. Instalar al agente de System Center Operations Manager en el equipo de nodo de monitor.
    
3. Ejecute el archivo Watchernode.msi.
    
4. Use el cmdlet **New-CsWatcherNodeConfiguration** para configurar las cuentas de usuario de prueba que se usarán en el nodo de monitor.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Instale los archivos principales de Skype Empresarial Server 2015 y la base de datos RTCLocal

Para instalar el Skype para los archivos de núcleo de Business Server 2015 en un equipo, realice el procedimiento siguiente. La base de datos RTCLocal se instalará automáticamente al instalar los archivos principales. Tenga en cuenta que no es necesario instalar a SQL Server en los nodos de monitor. SQL Server Express se instalará automáticamente.
  
Para instalar el Skype para los archivos principales de Business Server 2015 y la base de datos RTCLocal:
  
1. En el equipo que actúa como nodo de monitor, haga clic en Inicio, Todos los programas y Accesorios, haga clic con el botón secundario en Símbolo del sistema y, finalmente, haga clic en Ejecutar como administrador.
    
2. En la ventana de la consola, escriba el comando siguiente y presione ENTRAR. Asegúrese de escribir la ruta de acceso apropiado para su Skype para los archivos del programa de instalación de Business Server: D:\Setup.exe /BootstrapLocalMgmtTo Compruebe que el principal de Skype para los componentes de Business Server se instaló correctamente, haga clic en **Inicio**, haga clic en **Todos los programas**, Haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**. En Skype para Shell de administración de servidor empresarial, escriba el siguiente comando de Windows PowerShell y presione ENTRAR:
  
```
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> La primera vez que ejecute este comando, no se devolverá ningún dato porque todavía no ha configurado los equipos de nodo de monitor. Si el comando se ejecuta sin devolver un error, se puede asumir que la Skype para el programa de instalación de Business Server se completó correctamente. 
  
Si el equipo de nodo de monitor se encuentra dentro del perímetro de su red, ejecute el comando siguiente para comprobar la instalación de Skype Empresarial Server 2015:
  
Get-CsPinPolicyYou recibirá información similar a la siguiente, dependiendo del número de directivas de PIN configuradas para su uso en la organización:
  
Identidad: Global
  
Descripción:
  
MinPasswordLength: 5
  
Fijar: 0
  
AllowCommonPatterns: False
  
PINLifetime: 0
  
MaximumLogonAttempts :
  
Si aparece información sobre las directivas de PIN, ello indica que los componentes principales se han instalado correctamente.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Instalar los archivos del agente Operations Manager en un nodo de monitor

Al igual que Skype para el programa de instalación de Business Server para informes de alertas de componentes, un Skype para el nodo de monitor Business Server 2015 requiere que se instalen los archivos del agente de System Center Operations Manager. Esto permite que las transacciones sintéticas que se ejecutará y alertas a ser informadas para el servidor de administración de System Center Operations Manager raíz.
  
Para instalar los archivos del agente, siga los procedimientos que aparecen en [Configure el Skype para los equipos de servidor empresarial que se van a supervisar](configure-computers-to-monitor.md).
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Configurar de un nodo de monitor para ejecutar transacciones sintéticas
<a name="enable_synthetic_trans"> </a>

Una vez instalados los archivos del agente System Center Operations Manager, debe configurar el propio nodo de monitor. La configuración del nodo de monitor varía en función de si está dentro de la red perimetral o fuera de dicha red. 
  
Al configurar un nodo de monitor, también debe elegir el tipo de método de autenticación que se va a usar en ese nodo. Skype para Business Server 2015 le permite elegir uno de los dos métodos de autenticación: servidor de confianza o credenciales de autenticación. La siguiente tabla muestra las diferencias entre estos dos métodos:
  
||**Descripción**|**Ubicaciones admitidas**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Usa un certificado para representar a un servidor interno y evitar problemas de autenticación.  <br/> Es útil para los administradores que prefieran administrar un solo certificado en vez de varias contraseñas de usuario en cada nodo de monitor.  <br/> |Dentro de la empresa.  <br/> Con este método, el nodo de monitor debe estar en el mismo dominio que los grupos de servidores que se están supervisando. Si el nodo de monitor y los grupos de servidores están en dominios diferentes, use la autenticación de credenciales.  <br/> |
|Negotiate  <br/> |Almacena los nombres de usuario y las contraseñas con seguridad en Windows Credential Manager en cada nodo de monitor.  <br/> Este modo necesita más administración de contraseñas, pero es la única opción para los nodos de monitor ubicados fuera de la empresa. Estos nodos de monitor no se pueden tratar como un extremo de confianza para la autenticación.  <br/> |Fuera de la empresa.  <br/> Dentro de la empresa.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Configurar un nodo de monitor para usar la autenticación con servidores de confianza
<a name="enable_synthetic_trans"> </a>

Si el equipo del nodo de monitor se encuentra dentro de la red perimetral, con la autenticación de servidor de confianza puede reducir considerablemente las tareas de administración para mantener un único certificado, en lugar de varias contraseñas de cuentas de usuario.
  
Para configurar autenticación de servidor de confianza, primero debe crear un grupo de aplicaciones de confianza para alojar el equipo que actúa como nodo de monitor. Una vez que haya creado el grupo de aplicaciones de confianza, a continuación, debe configurar las transacciones sintéticas en ese nodo de monitor para que se ejecute como las aplicaciones de confianza.
  
> [!NOTE]
> Una aplicación de confianza es una aplicación que se asignó el estado de confianza para ejecutarse como parte de Skype con Business Server 2015, pero no es una parte integrada del producto. El estado de confianza significa que no se desafiará a la aplicación cada vez que se ejecute la autenticación.
  
Para crear un grupo de servidores de aplicaciones de confianza, abra el Skype para Shell de administración de servidor empresarial y ejecute un comando similar al siguiente:
  
```
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Para obtener información detallada acerca de los parámetros en el comando anterior, escriba lo siguiente desde el Skype para el símbolo del sistema del Shell de administración de servidor empresarial: 
  
```
Get-Help New-CsTrustedApplicationPool -Full | more
```

Después de crear el grupo de aplicaciones de confianza, configure el equipo de nodo de monitor para que ejecute las transacciones sintéticas como una aplicación de confianza. Esto se realiza con el cmdlet  **New-CsTrustedApplication** y un comando similar a este:
  
```
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Cuando este comando finaliza y se crea la aplicación de confianza, se debe ejecutar el cmdlet **Enable-CsTopology** para garantizar que los cambios sean efectivos:
  
```
Enable-CsTopology
```

Después de ejecutar Enable-CsTopology, reinicie el equipo.
  
Para comprobar que se ha creado la nueva aplicación de confianza, escriba lo siguiente en el Skype para el símbolo del sistema del Shell de administración de servidor empresarial:
  
```
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Configurar un certificado predeterminado en el nodo de monitor
<a name="enable_synthetic_trans"> </a>

Cada nodo de monitor que usa la autenticación TrustedServer debe tener un certificado predeterminado asignado mediante la Skype para el Asistente para la implementación de servidor empresarial. 
  
Para asignar un certificado predeterminado:
  
1. Haga clic en Inicio, haga clic en todos los programas, haga clic en Skype para Business Server 2015 y, a continuación, haga clic en Skype para el Asistente para la implementación de servidor de negocio. 
    
2. En Skype para el Asistente para la implementación de Business Server, haga clic en instalar o actualizar Skype para Business Server System y, a continuación, haga clic en ejecutar en el encabezado de la solicitud, instalar o asignar el certificado. 
    
> [!NOTE]
> Si el botón Ejecutar está deshabilitado, puede que primero necesite hacer clic en Ejecutar en Instalar el almacén de configuración local. 
  
Siga uno de estos pasos:
  
- Si ya tiene un certificado que puede usarse como certificado predeterminado, haga clic en Predeterminado en el Asistente para certificados y luego haga clic en Asignar. Siga los pasos del Asistente para asignación de certificados para asignar ese certificado.
    
- Si necesita solicitar un certificado para usarlo como certificado predeterminado, haga clic en Solicitar y luego siga los pasos del Asistente para solicitar certificados para solicitar dicho certificado. Si usa los valores predeterminados para el certificado de servidor web, recibirá un certificado que puede asignar como certificado predeterminado.
    
## <a name="install-and-configure-a-watcher-node"></a>Para instalar y configurar un nodo de monitor
<a name="enable_synthetic_trans"> </a>

Después de haber reiniciado el equipo del nodo de monitor y haber configurado un certificado, debe ejecutar el archivo Watchernode.msi. (Debe ejecutar Watchernode.msi en cualquier equipo donde se instalan los archivos del agente Operations Manager y la Skype para los componentes principales de Business Server 2015.) 
  
Para instalar y configurar un nodo de monitor:
  
1. Abra el Skype para Shell de administración de servidor empresarial haciendo clic en Inicio, haciendo clic en todos los programas, haciendo clic en Skype para Business Server 2015, y, a continuación, haciendo clic en Skype para Shell de administración de servidor empresarial. 
    
2. En el shell de administración, escriba el siguiente comando y, a continuación, presione ENTRAR (asegúrese de especificar la ruta de acceso real a su copia de Watchernode.msi):
    
```
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> También puede ejecutar Watchernode.msi desde una ventana de comandos. Para abrir una ventana de comandos, haga clic en Inicio, haga clic con el botón secundario en Símbolo del sistema y luego en Ejecutar como administrador. Cuando se abra la ventana de comandos, escriba el comando indicado en el paso 2. 
  
> [!IMPORTANT]
> En el comando anterior, el par nombre-valor Authentication=TrustedServer distingue mayúsculas y minúsculas. Debe escribirse tal como se muestra. Por ejemplo, este comando producirá un error porque no usa las letras mayúsculas y minúsculas correctas: 
  
```
C:\Tools\Watchernode.msi authentication=trustedserver
```

El modo TrustedServer solo se puede usar con equipos que se encuentran dentro de la red perimetral. Cuando un nodo de monitor se ejecuta en modo TrustedServer, los administradores no tienen que mantener las contraseñas de usuario de prueba en el equipo.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Configurar un nodo de monitor para usar la negociación
<a name="enable_synthetic_trans"> </a>

Si el equipo del nodo del observador se encuentra fuera de la red perimetral, debe seguir un procedimiento ligeramente diferente para configurar el nodo del observador a fin de que ejecute las transacciones sintéticas: en particular, no debe crear un grupo de aplicaciones de confianza ni una aplicación de confianza. Esto significa que tendrá que completar las dos tareas siguientes.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Actualizar la pertenencia al grupo Administradores de solo lectura local de RTC

Si su nodo de monitor se encuentra fuera de la red perimetral, debe agregar la cuenta del servicio de red al grupo Administradores de solo lectura local de RTC del equipo del nodo de observador. Para ello, complete el siguiente procedimiento en el nodo de observador:
  
1. Haga clic en Inicio, haga clic con el botón secundario en Equipo y, a continuación, haga clic en Administrar .
    
2. En Administrador de servidores, expanda Configuración, expanda Usuarios y grupos locales y, a continuación, haga clic en Grupos.
    
3. En el panel Grupos, haga doble clic en RTC Local Read-only Administrators.
    
4. En el cuadro de diálogo Propiedades de RTC Local Read-only Administrators, haga clic en Agregar.
    
5. En el cuadro de diálogo para seleccionar usuarios, equipos, cuentas de servicio o grupos, haga clic en Ubicaciones.
    
6. En el cuadro de diálogo Ubicaciones, seleccione el nombre del equipo del nodo de observador y, a continuación, haga clic en Aceptar.
    
7. En el cuadro Escribir los nombres de objeto para seleccionar, escriba Servicio de red y, a continuación, haga clic en Aceptar.
    
8. En el cuadro de diálogo Propiedades de RTC Local Read-only Administrators, haga clic en Aceptar y, a continuación, cierre Administrador de servidores.
    
9. Reinicie el equipo del nodo de observador.
    
### <a name="install-the-watcher-node-configuration-files"></a>Instalar los archivos de configuración del nodo de monitor

El siguiente consiste en ejecutar el archivo Watchernode.msi: 
  
1. Abra el Shell de administración de Microsoft de Skype Empresarial Server 2015. Haga clic en Inicio, Todos los programas, Microsoft de Skype Empresarial Server 2015 y, a continuación, haga clic en Shell de administración de Skype Empresarial Server. 
    
2. En el Shell de administración de Skype Empresarial Server, escriba el siguiente comando y, a continuación, presione ENTRAR (asegúrese de especificar la ruta de acceso real a la copia del archivo Watchernode.msi):
    
   ```
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Como se ha descrito con anterioridad, Watchernode.msi también se puede ejecutar desde una ventana Comandos. Para abrir una ventana Comandos, haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y, a continuación, haga clic en **Ejecutar como administrador**. Cuando se abra la ventana Comandos, escriba el mismo comando que se ha mostrado en el paso 2. 
  
El modo Negotiate se usa en cualquier momento que el nodo de monitor no se puede configurar como un grupo de servidores de aplicaciones de confianza. En este modo, los administradores tendrán que administrar contraseñas de usuario de prueba en el nodo de monitor.
  

