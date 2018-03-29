---
title: Instalar y configurar nodos de monitor
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 'Resumen: Instalar y configurar los nodos de observador para Skype para transacciones sintéticas Business Server.'
ms.openlocfilehash: 2ba6c6e0ac201d9721d281c87665fe9bf9c0407c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="install-and-configure-watcher-nodes"></a>Instalar y configurar nodos de monitor
 
**Resumen:** Instalar y configurar los nodos de observador de Skype para transacciones sintéticas Business Server.
  
Nodos de observador son equipos que ejecutan periódicamente Skype para transacciones sintéticas Business Server. Transacciones sintéticas son cmdlets de Windows PowerShell que compruebe que los escenarios clave de usuario, como la capacidad para iniciar sesión en o para intercambiar mensajes instantáneos, funcionan como se esperaba. Para Skype para Business Server 2015, System Center Operations Manager puede ejecutar las transacciones sintéticas que se muestra en la tabla siguiente, que incluye tres tipos de transacciones sintéticas:
  
- **Predeterminado** Transacciones sintéticas que un nodo Monitor se ejecuta de forma predeterminada. Cuando se crea un nuevo nodo de monitor, puede especificar qué sintético transacciones se ejecutará en ese nodo. (Que es el propósito del parámetro de pruebas utilizado por el cmdlet New-CsWatcherNodeConfiguration). Si no utiliza el parámetro de pruebas cuando se crea el nodo supervisora, se ejecutará automáticamente todas las transacciones sintéticas predeterminado y no se ejecutará ninguna de las transacciones sintéticas Non-default. Por ejemplo, esto significa que el nodo Monitor debe configurarse para ejecutar la prueba de CsAddressBookService de prueba, pero no se configurará para ejecutar la prueba de CsExumConnectivity de prueba.
    
- **No predeterminado** Pruebas de nodos de observador no se ejecutan de forma predeterminada. (Para obtener más información, consulte la descripción del tipo de forma predeterminada). Sin embargo, el nodo Monitor puede habilitarse para ejecutar cualquiera de las transacciones sintéticas Non-default. Esto se puede hacer cuando se crea el nodo de monitor (mediante el cmdlet New-CsWatcherNodeConfiguration) o en cualquier momento después de crear dicho nodo. Tenga en cuenta que muchas de las transacciones sintéticas que no son predeterminadas requieren pasos de configuración adicionales. Para obtener más información sobre estos pasos, consulte las instrucciones de configuración especiales para Las transacciones sintéticas. Para obtener más detalles sobre estos pasos, consulte [Las instrucciones de instalación especiales para transacciones sintéticas ](test-users-and-settings.md#special_synthetictrans).
    
- **Extendido** Un tipo especial de transacciones sintéticas Non-default. A diferencia de otras transacciones sintéticas, pruebas extendidas pueden ejecutar varias veces durante cada paso. Esto es útil cuando se comprueba el comportamiento, como para un grupo de múltiples rutas de voz de red (conmutada PSTN) de telefónica pública conmutada. Puede configurar esto agregando varias instancias de una prueba extensa a un nodo de monitor.
    
Para obtener más información sobre el proceso para agregar otras transacciones sintéticas a un nodo de monitor, consulte [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans). También puede utilizar Skype para negocios de Shell de administración de servidor para quitar transacciones sintéticas desde un nodo Monitor.
  
Las transacciones sintéticas disponibles para los nodos de monitor son las siguientes:
  
|**Cmdlet nombre (prueba)**|**Descripción**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Confirma que los usuarios son capaces de buscar los usuarios que no están en su lista de contactos.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Confirma que los usuarios son capaces de buscar los usuarios que no están en su lista de contactos a través de HTTP.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Confirma que los usuarios pueden crear conferencias de audio/vídeo y participar en ellas.  <br/> |
|Test-CsGroupIM (conferencia de mensajería instantánea)  <br/> |Confirma que los usuarios pueden enviar mensajes instantáneos durante las conferencias y participar en conversaciones de mensajes instantáneos con tres o más personas.  <br/> |
|Test-CsIM (P2P IM)  <br/> |Confirma que los usuarios pueden enviar mensajes instantáneos punto a punto.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Confirma que los usuarios pueden realizar llamadas de audio de punto a punto (solo señalización).  <br/> |
|Test-CsPresence (Presence)  <br/> |Confirma que los usuarios son capaces de ver la presencia de otros usuarios.  <br/> |
|Test-CsRegistration (Registration)  <br/> |Confirma que los usuarios sean capaz de iniciar sesión en Skype para el negocio.  <br/> |
|Test-CsPstnPeerToPeerCall (RTC)  <br/> |Confirma que los usuarios pueden hacer y recibir llamadas con gente ajena a la empresa (números de RTC).  <br/> |
|Test-CsASConference (ASConference)  <br/> |Confirma que los usuarios pueden crear conferencias de uso compartido de aplicaciones y participar en ellas.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Confirma que los servidores perimetrales A/V pueden aceptar conexiones para las llamadas de punto a punto y las llamadas de conferencia.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Confirma que los usuarios pueden participar en una conferencia de colaboración de datos (una reunión en línea que engloba actividades como pizarras y sondeos).  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma que los usuarios pueden marcar números de teléfono para participar en conferencias.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma que los usuarios pueden marcar números de teléfono para participar en conferencias.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Confirma que un usuario puede conectarse a Exchange Unified Messaging (UM).  <br/> |
|Test-CsGroupIM - TestJoinLauncher (JoinLauncher)  <br/> |Confirma que los usuarios pueden crear reuniones programadas y unirse a ellas (a través de un vínculo de dirección web).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Confirma que los usuarios de dispositivos móviles pueden registrarse y enviar mensajes instantáneos.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Confirma que servidor de interoperabilidad vídeo está activo y puede controlar las conexiones entrantes a través de un vídeo troncal SIP.  <br/> |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Confirma que los usuarios pueden intercambiar mensajes mediante el servicio de chat persistente.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Confirma que los usuarios pueden unirse a conferencias a través de la web.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Confirma que se puede acceder a los contactos de un usuario a través del almacén de contactos unificados. El almacén de contactos unificado proporciona una manera para que los usuarios mantener un único conjunto de contactos que puede tener acceso mediante Skype para Business Server 2015, mensajería de Outlook y el cliente de colaboración y Outlook Web Access.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Confirma que se pueden enviar mensajes instantáneos por la puerta de enlace XMPP (protocolo extensible de mensajería y presencia).  <br/> |
   
No es necesario instalar nodos de observador para usar System Center Operations Manager. Si no instala estos nodos, puede aún obtener alertas en tiempo real de Skype para los componentes de servidor de negocios 2015 siempre que se produzca un problema. (El componente y el módulo de administración de usuario no utiliza nodos de observador.) Sin embargo, los nodos de observador son necesarios si desea supervisar los escenarios end-to-end con el paquete de administración de supervisión activa.
  
> [!NOTE]
> Los administradores pueden ejecutar transacciones sintéticas de forma manual, sin usar o instalar Operations Manager. Dependiendo del tamaño de su Skype para la implementación de servidor de negocios, transacciones sintéticas pueden utilizar una gran cantidad de tiempo de procesador y memoria del equipo. Por este motivo, recomendamos usar un equipo dedicado como nodo de monitor. Por ejemplo, no debe configurar un Skype para Business Server servidor Front-End para que actúe como un nodo Monitor. Nodos de observador deben cumplir los mismos requisitos de hardware básico como cualquier otro equipo en su Skype para la topología de servidores de empresa. 
  
> [!NOTE]
> Un nodo Monitor de Lync Server 2013 heredado no puede ser ubicado en el mismo equipo que un Skype para nodo de Business Server 2015 watcher porque los archivos de sistema principales para Lync Server 2013 y Skype para Business Server 2015 no puede instalarse en el mismo equipo. Sin embargo, Skype para Business Server 2015 nodos de observador puede supervisar simultáneamente Skype para Business Server 2015 y Lync Server 2013. Las transacciones sintéticas predeterminadas son compatibles con ambas versiones de producto. 
  
Nodos de observador de Lync Server 2013 pueden implementarse dentro o fuera de la empresa para ayudar a comprobar:
  
- La conectividad con los grupos de servidores de usuarios de la empresa.
    
- La conectividad a través de redes perimetrales de los usuarios remotos que trabajan fuera de la empresa.
    
- La conectividad con aplicaciones de sucursal.
    
- Conectividad con Lync Server 2013 dentro de la empresa y a través de redes perimetrales.
    
Para ayudar a simplificar la administración, existen distintas opciones de autenticación desde dentro y fuera de la empresa. Para obtener más información, consulte [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).
  
Si desea configurar un equipo para que actúe como un nodo de monitor, primero debe completar los siguientes requisitos previos: 
  
- Instalar a System Center Operations Manager e importar el Skype para paquetes de administración de servidor de negocios 2015. En primer lugar también debe comprobar que el equipo de nodo Monitor cumple todos los requisitos previos para instalar Skype para Business Server 2015.
    
- Instale los elementos siguientes en el equipo que actúa como nodo de monitor:
    
  - La versión completa de.NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Una vez que se cumplan todos los requisitos previos, puede proceder a configurar el nodo de monitor siguiendo siga estos pasos:
  
1. Instale el Skype para Business Server 2015 archivos de núcleo en el equipo de nodo Monitor.
    
2. Instalar a agente de System Center Operations Manager en el equipo de nodo Monitor.
    
3. Ejecute el archivo Watchernode.msi.
    
4. Use el cmdlet **New-CsWatcherNodeConfiguration** para configurar las cuentas de usuario de prueba que se usarán en el nodo de monitor.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Instale los archivos principales de Skype Empresarial Server 2015 y la base de datos RTCLocal

Para instalar el Skype para Business Server 2015 archivos de núcleo en un equipo, complete el procedimiento siguiente. La base de datos RTCLocal se instalará automáticamente al instalar los archivos principales. Tenga en cuenta que no es necesario instalar SQL Server en los nodos de observador. SQL Server Express se instalará automáticamente.
  
Para instalar el Skype para los archivos de núcleo de Business Server 2015 y la base de datos de RTCLocal:
  
1. En el equipo que actúa como nodo de monitor, haga clic en Inicio, Todos los programas y Accesorios, haga clic con el botón secundario en Símbolo del sistema y, finalmente, haga clic en Ejecutar como administrador.
    
2. En la ventana de la consola, escriba el comando siguiente y presione ENTRAR. No olvide introducir la ruta de acceso apropiada a su Skype para archivos de instalación de Business Server: D:\Setup.exe /BootstrapLocalMgmtTo comprobar que el núcleo Skype para los componentes de Business Server está instalado correctamente, haga clic en **Inicio**, seleccione **Todos los programas**, Haga clic en **Skype para Business Server 2015**y, a continuación, haga clic en **Skype para el Shell de administración de servidor empresarial**. En Skype para negocios de Shell de administración de servidor, escriba el siguiente comando de Windows PowerShell y presione ENTRAR:
  
```
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> La primera vez que ejecute este comando, no se devolverá ningún dato porque todavía no ha configurado los equipos de nodo de monitor. Si el comando se ejecuta sin errores, se puede suponer que el Skype para el programa de instalación de Business Server se completó correctamente. 
  
Si el equipo de nodo de monitor se encuentra dentro del perímetro de su red, ejecute el comando siguiente para comprobar la instalación de Skype Empresarial Server 2015:
  
Get CsPinPolicyYou aparecerá información similar a ésta, dependiendo del número de directivas PIN configurado para su uso en la organización:
  
Identidad: Global
  
Descripción:
  
MinPasswordLength: 5
  
PINHistoryCount: 0
  
AllowCommonPatterns: False
  
PINLifetime: 0
  
MaximumLogonAttempts :
  
Si aparece información sobre las directivas de PIN, ello indica que los componentes principales se han instalado correctamente.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Instalar los archivos del agente Operations Manager en un nodo de monitor

Similar a Skype para el programa de instalación de Business Server por informar alertas de componentes, un Skype para nodo de watcher Business Server 2015 requiere que se instalen los archivos del agente de System Center Operations Manager. Esto permite las transacciones sintéticas para ejecutarse y alertas a ser informadas para el servidor de administración raíz de sistema Center Operations Manager.
  
Para instalar los archivos del agente, siga los procedimientos descritos en [Configurar el Skype para equipos Business Server que se va a supervisar](configure-computers-to-monitor.md).
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Configurar de un nodo de monitor para ejecutar transacciones sintéticas
<a name="enable_synthetic_trans"> </a>

Después de han instalado los archivos del agente de System Center Operations Manager, debe configurar el propio nodo Monitor. La configuración del nodo de monitor varía en función de si está dentro de la red perimetral o fuera de dicha red. 
  
Al configurar un nodo de monitor, también debe elegir el tipo de método de autenticación que se va a usar en ese nodo. Skype para el año 2015 de Business Server le permite elegir uno de dos métodos de autenticación: Trusted Server o credenciales de autenticación. La siguiente tabla muestra las diferencias entre estos dos métodos:
  
||**Descripción**|**Ubicaciones compatibles**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Utiliza un certificado para suplantar a un servidor interno y omitir los desafíos de autenticación.  <br/> Es útil para los administradores que prefieren administrar un certificado individual, en lugar de muchas contraseñas de usuario en cada nodo del monitor.  <br/> |Dentro de la empresa.  <br/> Con este método, el nodo de monitor debe estar en el mismo dominio que los grupos de servidores que se están supervisando. Si el nodo de monitor y los grupos de servidores están en dominios diferentes, use la autenticación de credenciales.  <br/> |
|Negotiate  <br/> |Almacena nombres de usuario y las contraseñas de forma segura en el Administrador de credenciales de Windows en cada nodo del monitor.  <br/> Este modo necesita más administración de contraseñas, pero es la única opción para los nodos de monitor ubicados fuera de la empresa. Estos nodos de monitor no se pueden tratar como un extremo de confianza para la autenticación.  <br/> |Fuera de la empresa.  <br/> Dentro de la empresa.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Configurar un nodo de monitor para usar la autenticación con servidores de confianza
<a name="enable_synthetic_trans"> </a>

Si el equipo del nodo de monitor se encuentra dentro de la red perimetral, con la autenticación de servidor de confianza puede reducir considerablemente las tareas de administración para mantener un único certificado, en lugar de varias contraseñas de cuentas de usuario.
  
Para configurar autenticación de servidor de confianza, primero debe crear un grupo de aplicaciones de confianza para alojar el equipo que actúa como nodo de monitor. Una vez creado el grupo de aplicaciones de confianza, a continuación, debe configurar transacciones sintéticas en ese nodo supervisora para ejecutarse como aplicaciones de confianza.
  
> [!NOTE]
> Una aplicación de confianza es una aplicación que se proporciona el estado de confianza para ejecutarse como parte de Skype para Business Server 2015, pero que no esté integrada en el producto. Estado de confianza significa que la aplicación no será desafiada para la autenticación cada vez que se ejecuta.
  
Para crear un grupo de aplicaciones de confianza, abra el Skype para el Shell de administración de servidor empresarial y ejecutar un comando similar a éste:
  
```
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Para obtener más información acerca de los parámetros en el comando anterior, escriba lo siguiente desde el Skype para el indicador de Shell de administración de servidor de negocios: 
  
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
  
Para comprobar que se ha creado la nueva aplicación de confianza, escriba lo siguiente en el Skype para el indicador de Shell de administración de servidor de negocios:
  
```
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Configurar un certificado predeterminado en el nodo de monitor
<a name="enable_synthetic_trans"> </a>

Cada nodo de monitor que utiliza autenticación TrustedServer debe tener un certificado de predeterminado asignado mediante el Skype para Business Server Deployment wizard. 
  
Para asignar un certificado predeterminado:
  
1. Haga clic en Inicio, seleccione todos los programas, haga clic en Skype para Business Server 2015 y, a continuación, haga clic en Skype para el Asistente para implementación de Business Server. 
    
2. En Skype para el Asistente para implementación de Business Server, haga clic en instalar o actualizar Skype para el sistema de servidor de Business y, a continuación, haga clic en ejecutar bajo el encabezado de la solicitud, instale o asigne el certificado. 
    
> [!NOTE]
> Si el botón Ejecutar está deshabilitado, puede que primero necesite hacer clic en Ejecutar en Instalar el almacén de configuración local. 
  
Siga uno de estos pasos:
  
- Si ya tiene un certificado que puede usarse como certificado predeterminado, haga clic en Predeterminado en el Asistente para certificados y luego haga clic en Asignar. Siga los pasos del Asistente para asignación de certificados para asignar ese certificado.
    
- Si necesita solicitar un certificado para usarlo como certificado predeterminado, haga clic en Solicitar y luego siga los pasos del Asistente para solicitar certificados para solicitar dicho certificado. Si usa los valores predeterminados para el certificado de servidor web, recibirá un certificado que puede asignar como certificado predeterminado.
    
## <a name="install-and-configure-a-watcher-node"></a>Para instalar y configurar un nodo de monitor
<a name="enable_synthetic_trans"> </a>

Después de haber reiniciado el equipo del nodo de monitor y haber configurado un certificado, debe ejecutar el archivo Watchernode.msi. (Debe ejecutar Watchernode.msi en cualquier equipo donde se instalan los archivos del agente Operations Manager y el Skype para los componentes de núcleo de Business Server 2015.) 
  
Para instalar y configurar un nodo de monitor:
  
1. Abra el Skype de Shell de administración de servidor empresarial haciendo clic en Inicio, en todos los programas, haciendo clic en Skype para Business Server 2015 y, a continuación, haciendo clic en Skype para el Shell de administración de servidor de Business. 
    
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
  

