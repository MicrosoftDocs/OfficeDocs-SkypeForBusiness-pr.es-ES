---
title: Instalar y configurar nodos de monitor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 'Resumen: Instale y configure nodos de monitor para transacciones sintéticas de Skype empresarial Server.'
ms.openlocfilehash: f95803f61d527196c97c7a6a17b8e0bfcfdfbc7a
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221521"
---
# <a name="install-and-configure-watcher-nodes"></a>Instalar y configurar nodos de monitor
 
**Resumen:** Instalar y configurar nodos de monitor para las transacciones sintéticas de Skype empresarial Server.
  
Los nodos de monitor son equipos que ejecutan periódicamente transacciones sintéticas de Skype empresarial Server. Las transacciones sintéticas son cmdlets de Windows PowerShell que comprueban que los escenarios clave del usuario, como la capacidad de iniciar sesión o de intercambiar mensajes instantáneos, funcionan de la manera esperada. Para Skype empresarial Server 2015, System Center Operations Manager puede ejecutar las transacciones sintéticas que se muestran en la tabla siguiente, que incluye tres tipos de transacción sintética:
  
- **Valor predeterminado** Transacciones sintéticas que un nodo de observador ejecuta de forma predeterminada. Al crear un nuevo nodo de monitor, puede especificar qué transacciones sintéticas se ejecutarán. (Este es el propósito del parámetro tests usado por el cmdlet New-CsWatcherNodeConfiguration). Si no usa el parámetro tests cuando se crea el nodo de monitor, se ejecutarán automáticamente todas las transacciones sintéticas predeterminadas y no se ejecutará ninguna de las transacciones sintéticas no predeterminadas. Esto significa que, por ejemplo, el nodo de supervisor se configurará para ejecutar la prueba de prueba de CsAddressBookService, pero no se configurará para ejecutar la prueba de CsExumConnectivity de prueba.
    
- **No predeterminado** Prueba que los nodos de los monitores no se ejecutan de forma predeterminada. Para obtener información detallada, vea la descripción del tipo predeterminado. Sin embargo, el nodo de monitor puede estar habilitado para ejecutar cualquiera de las transacciones sintéticas no predeterminadas. Esto se puede hacer cuando se crea el nodo de monitor (mediante el cmdlet New-CsWatcherNodeConfiguration) o en cualquier momento después de crear dicho nodo. Tenga en cuenta que muchas de las transacciones sintéticas que no son predeterminadas requieren pasos de configuración adicionales. Para obtener más información sobre estos pasos, consulte [Special Setup Instructions for Synthetic Transactions](test-users-and-settings.md#special_synthetictrans).
    
- **Ampliado** Un tipo especial de transacción sintética no predeterminada. A diferencia de otras transacciones sintéticas, las pruebas extendidas se pueden ejecutar varias veces durante cada pasada. Esto es útil para comprobar el comportamiento, como varias rutas de voz de red telefónica conmutada (RTC) para un grupo. Puede configurarlo simplemente agregando varias instancias de una prueba extendida a un nodo de monitor.
    
Para obtener más información sobre el proceso para agregar otras transacciones sintéticas a un nodo de monitor, consulte [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans). También puede usar el shell de administración de Skype empresarial para quitar las transacciones sintéticas de un nodo de monitor.
  
Las transacciones sintéticas disponibles para los nodos de monitor son las siguientes:
  
|**Nombre del cmdlet (nombre de la prueba)**|**Descripción**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Confirma que los usuarios pueden buscar usuarios que no se encuentran en su lista de contactos.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Confirma que los usuarios pueden buscar usuarios que no se encuentran en su lista de contactos a través de HTTP.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Confirma que los usuarios pueden crear conferencias de audio/vídeo y participar en ellas.  <br/> |
|Test-CsGroupIM (conferencia de mensajería instantánea)  <br/> |Confirma que los usuarios pueden enviar mensajes instantáneos durante las conferencias y participar en conversaciones de mensajes instantáneos con tres o más personas.  <br/> |
|Test-CsIM (P2P IM)  <br/> |Confirma que los usuarios pueden enviar mensajes instantáneos punto a punto.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Confirma que los usuarios pueden realizar llamadas de audio de punto a punto (solo señalización).  <br/> |
|Test-CsPresence (Presence)  <br/> |Confirma que los usuarios pueden ver la presencia de otros usuarios.  <br/> |
|Test-CsRegistration (Registration)  <br/> |Confirma que los usuarios pueden iniciar sesión en Skype empresarial.  <br/> |
|Test-CsPstnPeerToPeerCall (RTC)  <br/> |Confirma que los usuarios pueden hacer y recibir llamadas con gente ajena a la empresa (números de RTC).  <br/> |
|Test-CsASConference (ASConference)  <br/> |Confirma que los usuarios pueden crear conferencias de uso compartido de aplicaciones y participar en ellas.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Confirma que los servidores perimetrales A/V pueden aceptar conexiones para las llamadas de punto a punto y las llamadas de conferencia.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Confirma que los usuarios pueden participar en una conferencia de colaboración de datos (una reunión en línea que engloba actividades como pizarras y sondeos).  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma que los usuarios pueden marcar números de teléfono para participar en conferencias.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma que los usuarios pueden marcar números de teléfono para participar en conferencias.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Confirma que un usuario puede conectarse a la mensajería unificada de Exchange (UM).  <br/> |
|Prueba-CsGroupIM-TestJoinLauncher (JoinLauncher)  <br/> |Confirma que los usuarios pueden crear reuniones programadas y unirse a ellas (a través de un vínculo de dirección web).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Confirma que los usuarios de dispositivos móviles pueden registrarse y enviar mensajes instantáneos.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Confirma que el servidor de interoperabilidad de video está en marcha y puede manejar conexiones entrantes a través de un tronco del SIP de video.  <br/> **Nota:** La compatibilidad MCX para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Confirma que los usuarios pueden intercambiar mensajes mediante el servicio de chat persistente.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Confirma que los usuarios pueden unirse a conferencias a través de la web.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Confirma que se puede acceder a los contactos de un usuario a través del almacén de contactos unificados. El almacén de contactos unificado proporciona a los usuarios una manera de mantener un único conjunto de contactos al que se puede obtener acceso mediante Skype empresarial Server 2015, el cliente de mensajería y colaboración de Outlook y/o Outlook Web Access.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Confirma que se pueden enviar mensajes instantáneos por la puerta de enlace XMPP (protocolo extensible de mensajería y presencia).  <br/> Las puertas de enlace y los servidores proxy XMPP están disponibles en Skype empresarial Server 2015, pero ya no son compatibles con Skype empresarial Server 2019.  |

No es necesario instalar nodos de monitor para usar System Center Operations Manager. Si no instala estos nodos, aún podrá recibir alertas en tiempo real de los componentes de Skype empresarial Server 2015 siempre que se produzca un problema. (El paquete de administración de componentes y usuarios no usa nodos de monitor). Sin embargo, se necesitan nodos de monitor si desea supervisar escenarios descentralizados mediante el módulo de administración de supervisión activa.
  
> [!NOTE]
> Los administradores pueden ejecutar transacciones sintéticas de forma manual, sin usar o instalar Operations Manager. En función del tamaño de su implementación de Skype empresarial Server, las transacciones sintéticas pueden usar una gran cantidad de memoria del equipo y tiempo de procesador. Por este motivo, recomendamos usar un equipo dedicado como nodo de monitor. Por ejemplo, no debe configurar un servidor front-end de Skype empresarial Server para que actúe como nodo de monitor. Los nodos de monitor deben cumplir los mismos requisitos de hardware básicos que cualquier otro equipo de su topología de Skype empresarial Server. 
  
> [!NOTE]
> No se puede colocar un nodo de monitor antiguo de Lync Server 2013 en el mismo equipo que un nodo de monitor de Skype empresarial Server 2015 porque los archivos de sistema principales para Lync Server 2013 y Skype empresarial Server 2015 no se pueden instalar en el mismo equipo. Sin embargo, los nodos de monitor de Skype empresarial Server 2015 pueden supervisar simultáneamente Skype empresarial Server 2015 y Lync Server 2013. Las transacciones sintéticas predeterminadas son compatibles con ambas versiones de producto. 
  
Los nodos de monitor de Lync Server 2013 se pueden implementar dentro o fuera de una empresa para ayudar a comprobar:
  
- La conectividad con los grupos de servidores de usuarios de la empresa.
    
- La conectividad a través de redes perimetrales de los usuarios remotos que trabajan fuera de la empresa.
    
- La conectividad con aplicaciones de sucursal.
    
- Conectividad con Lync Server 2013 dentro de la empresa y a través de redes perimetrales.
    
Para ayudar a simplificar la administración, existen distintas opciones de autenticación desde dentro y fuera de la empresa. Para obtener más información, consulte [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).
  
Si desea configurar un equipo para que actúe como un nodo de monitor, primero debe completar los siguientes requisitos previos: 
  
- Instale System Center Operations Manager e importe los paquetes de administración de Skype empresarial Server 2015. También debe comprobar primero que el equipo del nodo de supervisor cumple todos los requisitos previos para instalar Skype empresarial Server 2015.
    
- Instale los elementos siguientes en el equipo que actúa como nodo de monitor:
    
  - La versión completa de .NET Framework 4,5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Una vez que se cumplan todos los requisitos previos, puede proceder a configurar el nodo de monitor siguiendo siga estos pasos:
  
1. Instale los archivos básicos de Skype empresarial Server 2015 en el equipo del nodo de monitor.
    
2. Instale el agente de System Center Operations Manager en el equipo del nodo de monitor.
    
3. Ejecute el archivo Watchernode.msi.
    
4. Use el cmdlet **New-CsWatcherNodeConfiguration** para configurar las cuentas de usuario de prueba que se usarán en el nodo de monitor.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Instale los archivos principales de Skype Empresarial Server 2015 y la base de datos RTCLocal

Para instalar los archivos principales de Skype empresarial Server 2015 en un equipo, complete el siguiente procedimiento. La base de datos RTCLocal se instalará automáticamente al instalar los archivos principales. Tenga en cuenta que no es necesario instalar SQL Server en los nodos de los monitores. SQL Server Express se instalará automáticamente.
  
Para instalar los archivos básicos de Skype empresarial Server 2015 y la base de datos RTCLocal:
  
1. En el equipo que actúa como nodo de monitor, haga clic en Inicio, Todos los programas y Accesorios, haga clic con el botón secundario en Símbolo del sistema y, finalmente, haga clic en Ejecutar como administrador.
    
2. En la ventana de la consola, escriba el comando siguiente y presione ENTRAR. Asegúrese de escribir la ruta de acceso adecuada a los archivos de instalación de Skype empresarial Server: D:\Setup.exe/BootstrapLocalMgmtTo Compruebe que los componentes básicos de Skype empresarial Server se instalan correctamente, haga clic en **Inicio**, haga clic en **todos los programas**, Haga clic en **Skype empresarial server 2015**y, a continuación, haga clic en **consola de administración de Skype empresarial Server**. En el shell de administración de Skype empresarial Server, escriba el siguiente comando de Windows PowerShell y presione ENTRAR:
  
```
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> La primera vez que ejecute este comando, no se devolverá ningún dato porque todavía no ha configurado los equipos de nodo de monitor. Si el comando se ejecuta sin devolver un error, puede suponer que la configuración de Skype empresarial Server se ha completado correctamente. 
  
Si el equipo de nodo de monitor se encuentra dentro del perímetro de su red, ejecute el comando siguiente para comprobar la instalación de Skype Empresarial Server 2015:
  
Get-CsPinPolicyYou recibirá información similar a la siguiente, según la cantidad de directivas de PIN configuradas para su uso en su organización:
  
Identidad: global
  
Texto
  
MinPasswordLength: 5
  
PINHistoryCount: 0
  
AllowCommonPatterns: falso
  
PINLifetime: 0
  
MaximumLogonAttempts :
  
Si aparece información sobre las directivas de PIN, ello indica que los componentes principales se han instalado correctamente.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Instalar los archivos del agente Operations Manager en un nodo de monitor

De forma similar al programa de instalación de Skype empresarial Server por informar de alertas de componentes, un nodo de monitor de Skype empresarial Server 2015 requiere que se instalen los archivos del agente de System Center Operations Manager. Esto permite que se ejecuten las transacciones sintéticas y se notifiquen al servidor de administración de raíz de System Center Operations Manager.
  
Para instalar los archivos del agente, siga los procedimientos que se indican en [configurar los equipos servidor de Skype empresarial que](configure-computers-to-monitor.md)se supervisarán.
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Configurar de un nodo de monitor para ejecutar transacciones sintéticas
<a name="enable_synthetic_trans"> </a>

Una vez instalados los archivos del agente System Center Operations Manager, debe configurar el nodo de monitor en sí. La configuración del nodo de monitor varía en función de si está dentro de la red perimetral o fuera de dicha red. 
  
Al configurar un nodo de monitor, también debe elegir el tipo de método de autenticación que se va a usar en ese nodo. Skype empresarial Server 2015 le permite elegir uno de los dos métodos de autenticación: servidor de confianza o autenticación de credenciales. La siguiente tabla muestra las diferencias entre estos dos métodos:
  
||**Descripción**|**Ubicaciones admitidas**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Usa un certificado para representar a un servidor interno y evitar problemas de autenticación.  <br/> Es útil para los administradores que prefieran administrar un solo certificado en vez de varias contraseñas de usuario en cada nodo de monitor.  <br/> |Dentro de la empresa.  <br/> Con este método, el nodo de monitor debe estar en el mismo dominio que los grupos de servidores que se están supervisando. Si el nodo de monitor y los grupos de servidores están en dominios diferentes, use la autenticación de credenciales.  <br/> |
|Negotiate  <br/> |Almacena los nombres de usuario y las contraseñas con seguridad en Windows Credential Manager en cada nodo de monitor.  <br/> Este modo necesita más administración de contraseñas, pero es la única opción para los nodos de monitor ubicados fuera de la empresa. Estos nodos de monitor no se pueden tratar como un extremo de confianza para la autenticación.  <br/> |Fuera de la empresa.  <br/> Dentro de la empresa.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Configurar un nodo de monitor para usar la autenticación con servidores de confianza
<a name="enable_synthetic_trans"> </a>

Si el equipo del nodo de monitor se encuentra dentro de la red perimetral, con la autenticación de servidor de confianza puede reducir considerablemente las tareas de administración para mantener un único certificado, en lugar de varias contraseñas de cuentas de usuario.
  
Para configurar autenticación de servidor de confianza, primero debe crear un grupo de aplicaciones de confianza para alojar el equipo que actúa como nodo de monitor. Una vez que haya creado el grupo de aplicaciones de confianza, debe configurar las transacciones sintéticas en ese nodo de observador para que se ejecuten como aplicaciones de confianza.
  
> [!NOTE]
> Una aplicación de confianza es una aplicación que recibe el estado de confianza para ejecutarse como parte de Skype empresarial Server 2015, pero no es una parte integrada del producto. El estado de confianza significa que no se desafiará a la aplicación cada vez que se ejecute la autenticación.
  
Para crear un grupo de aplicaciones de confianza, abra el shell de administración de Skype empresarial Server y ejecute un comando similar a este:
  
```
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Para más información sobre los parámetros del comando anterior, escriba lo siguiente en el símbolo del sistema de la consola de administración de Skype empresarial Server: 
  
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
  
Para comprobar que se ha creado la nueva aplicación de confianza, escriba lo siguiente en el símbolo del sistema de la administración de Skype empresarial Server:
  
```
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Configurar un certificado predeterminado en el nodo de monitor
<a name="enable_synthetic_trans"> </a>

Cada nodo de monitor que usa la autenticación TrustedServer debe tener un certificado predeterminado asignado mediante el Asistente para la implementación de Skype empresarial Server. 
  
Para asignar un certificado predeterminado:
  
1. Haga clic en Inicio, haga clic en todos los programas, haga clic en Skype empresarial Server 2015 y, a continuación, haga clic en asistente de implementación de Skype empresarial Server. 
    
2. En el Asistente para la implementación de Skype empresarial Server, haga clic en instalar o actualizar el sistema de Skype empresarial Server y, a continuación, haga clic en ejecutar en la solicitud de título, instalar o asignar certificado. 
    
> [!NOTE]
> Si el botón Ejecutar está deshabilitado, puede que primero necesite hacer clic en Ejecutar en Instalar el almacén de configuración local. 
  
Siga uno de estos pasos:
  
- Si ya tiene un certificado que puede usarse como certificado predeterminado, haga clic en Predeterminado en el Asistente para certificados y luego haga clic en Asignar. Siga los pasos del Asistente para asignación de certificados para asignar ese certificado.
    
- Si necesita solicitar un certificado para usarlo como certificado predeterminado, haga clic en Solicitar y luego siga los pasos del Asistente para solicitar certificados para solicitar dicho certificado. Si usa los valores predeterminados para el certificado de servidor web, recibirá un certificado que puede asignar como certificado predeterminado.
    
## <a name="install-and-configure-a-watcher-node"></a>Para instalar y configurar un nodo de monitor
<a name="enable_synthetic_trans"> </a>

Después de haber reiniciado el equipo del nodo de monitor y haber configurado un certificado, debe ejecutar el archivo Watchernode.msi. (Debe ejecutar Watchernode. msi en cualquier equipo donde estén instalados los dos archivos del agente de Operations Manager y los componentes principales de Skype empresarial Server 2015). 
  
Para instalar y configurar un nodo de monitor:
  
1. Para abrir el shell de administración de Skype empresarial, haga clic en Inicio, haga clic en todos los programas, haga clic en Skype empresarial Server 2015 y, a continuación, haga clic en consola de administración de Skype empresarial Server. 
    
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
  

