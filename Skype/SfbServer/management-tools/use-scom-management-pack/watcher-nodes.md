---
title: Cómo instalar y configurar nodos de monitor
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: Cómo instalar y configurar nodos de monitor para Skype Empresarial Server transacciones sintéticas.
ms.openlocfilehash: aca051b005c3ec9a901c5366a7788af5e95d06f0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766218"
---
# <a name="how-to-install-and-configure-watcher-nodes"></a>Cómo instalar y configurar nodos de monitor
 
**Resumen:** Instale y configure nodos de monitor para Skype Empresarial Server transacciones sintéticas.
  
Los nodos de monitor son equipos que ejecutan periódicamente Skype Empresarial Server transacciones sintéticas. Las transacciones sintéticas Windows PowerShell cmdlets que comprueban que los escenarios clave del usuario, como la capacidad de iniciar sesión o intercambiar mensajes instantáneos, funcionan según lo esperado. Para Skype Empresarial Server 2015, System Center Operations Manager puede ejecutar las transacciones sintéticas que se muestran en la tabla siguiente, que incluye tres tipos de transacciones sintéticas:
  
- **Valor predeterminado** Transacciones sintéticas que se ejecuta un nodo de monitor de forma predeterminada. Al crear un nuevo nodo de monitor, puede especificar qué transacciones sintéticas se ejecutarán en ese nodo. (Ese es el propósito del parámetro Tests usado por el cmdlet New-CsWatcherNodeConfiguration). Si no usa el parámetro Tests cuando se crea el nodo de monitor, ejecutará automáticamente todas las transacciones sintéticas predeterminadas y no ejecutará ninguna de las transacciones sintéticas no predeterminadas. Esto significa, por ejemplo, que el nodo de monitor se configurará para ejecutar la prueba Test-CsAddressBookService, pero no se configurará para ejecutar la Test-CsExumConnectivity prueba.
    
- **No predeterminado** Pruebas que los nodos de monitor no se ejecutan de forma predeterminada. (Para obtener más información, vea la descripción del tipo Predeterminado). Sin embargo, el nodo de monitor se puede habilitar para ejecutar cualquiera de las transacciones sintéticas no predeterminadas. Puede hacerlo cuando cree el nodo de monitor (mediante el cmdlet New-CsWatcherNodeConfiguration) o en cualquier momento después de que se haya creado el nodo de monitor. Tenga en cuenta que muchas de las transacciones sintéticas no predeterminadas requieren pasos de configuración adicionales. Para obtener más información acerca de estos pasos, vea [Special Setup Instructions for Synthetic Transactions](test-users-and-settings.md#special_synthetictrans).
    
- **Extendido** Un tipo especial de transacción sintética no predeterminada. A diferencia de otras transacciones sintéticas, las pruebas extendidas se pueden ejecutar varias veces durante cada pase. Esto es útil al comprobar el comportamiento, como varias rutas de voz de red telefónica conmutada (RTC) para un grupo de servidores. Puede configurar esto simplemente agregando varias instancias de una prueba extendida a un nodo de monitor.
    
Para obtener información detallada sobre el proceso para agregar otras transacciones sintéticas a un nodo de monitor, vea [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans). También puede usar el Shell Skype Empresarial Server administración para quitar transacciones sintéticas de un nodo de monitor.
  
Las transacciones sintéticas disponibles para los nodos de monitor son las siguientes:
  
|**Nombre del cmdlet (nombre de la prueba)**|**Descripción**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Confirma que los usuarios pueden buscar usuarios que no están en su lista de contactos.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Confirma que los usuarios pueden buscar usuarios que no están en su lista de contactos a través de HTTP.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Confirma que los usuarios pueden crear conferencias de audio/vídeo y participar en ellas.  <br/> |
|Test-CsGroupIM (conferencia de mensajería instantánea)  <br/> |Confirma que los usuarios pueden enviar mensajes instantáneos durante las conferencias y participar en conversaciones de mensajes instantáneos con tres o más personas.  <br/> |
|Test-CsIM (P2P IM)  <br/> |Confirma que los usuarios pueden enviar mensajes instantáneos punto a punto.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Confirma que los usuarios pueden realizar llamadas de audio punto a punto (solo señalización).  <br/> |
|Test-CsPresence (Presence)  <br/> |Confirma que los usuarios pueden ver la presencia de otros usuarios.  <br/> |
|Test-CsRegistration (Registration)  <br/> |Confirma que los usuarios pueden iniciar sesión en Skype Empresarial.  <br/> |
|Test-CsPstnPeerToPeerCall (RTC)  <br/> |Confirma que los usuarios pueden hacer y recibir llamadas con gente ajena a la empresa (números de RTC).  <br/> |
|Test-CsASConference (ASConference)  <br/> |Confirma que los usuarios pueden crear y participar en una conferencia de uso compartido de aplicaciones.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Confirma que los servidores perimetrales de audio y vídeo pueden aceptar conexiones para llamadas punto a punto y llamadas de conferencia.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Confirma que los usuarios pueden participar en una conferencia de colaboración de datos (una reunión en línea que incluye actividades como pizarras y sondeos).  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma que los usuarios pueden marcar números de teléfono para unirse a conferencias.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma que los usuarios pueden marcar números de teléfono para unirse a conferencias.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Confirma que un usuario puede conectarse a Exchange mensajería unificada (MU).  <br/> |
|Test-CsGroupIM -TestJoinLauncher (JoinLauncher)  <br/> |Confirma que los usuarios pueden crear y unirse a reuniones programadas (mediante un vínculo de dirección web).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Confirma que los usuarios de dispositivos móviles pueden registrarse y enviar mensajes instantáneos.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Confirma que el servidor de interoperabilidad de vídeo está funcionando y puede controlar las conexiones entrantes a través de un tronco SIP de vídeo.  <br/> **Nota:** La compatibilidad con MCX para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Confirma que los usuarios pueden intercambiar mensajes mediante el servicio de chat persistente.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Confirma que los usuarios pueden unirse a conferencias a través de la web.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Confirma que se puede acceder a los contactos de un usuario a través del almacén de contactos unificados. El almacén de contactos unificado proporciona a los usuarios una forma de mantener un único conjunto de contactos a los que se puede acceder mediante Skype Empresarial Server 2015, un cliente de mensajería y colaboración Outlook y/o Outlook Web Access.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Confirma que se puede enviar un mensaje instantáneo a través de la puerta de enlace del Protocolo extensible de mensajería y presencia (XMPP).  <br/> Las puertas de enlace XMPP y los servidores proxy están disponibles en Skype Empresarial Server 2015, pero ya no se admiten en Skype Empresarial Server 2019.  |

No es necesario instalar nodos de monitor para usar System Center Operations Manager. Si no instala estos nodos, puede recibir alertas en tiempo real de los componentes Skype Empresarial Server 2015 siempre que se produzca un problema. (El módulo de administración de componentes y usuarios no usa nodos de monitor). Sin embargo, los nodos de monitor son necesarios si desea supervisar escenarios de un extremo a otro mediante el módulo de administración de supervisión activa.
  
> [!NOTE]
> Los administradores también pueden ejecutar transacciones sintéticas manualmente, sin usar o instalar Operations Manager. Según el tamaño de la implementación Skype Empresarial Server, las transacciones sintéticas pueden usar una gran cantidad de memoria del equipo y tiempo de procesador. Debido a esto, se recomienda usar un equipo dedicado como nodo de monitor. Por ejemplo, no debe configurar un servidor Skype Empresarial Server front-end para que actúe como nodo de monitor. Los nodos de monitor deben cumplir los mismos requisitos de hardware básicos que cualquier otro equipo de Skype Empresarial Server topología. 
  
> [!NOTE]
> Un nodo de monitor de Lync Server 2013 heredado no se puede instalar en el mismo equipo que un nodo de monitor de Skype Empresarial Server 2015 porque los archivos principales del sistema para Lync Server 2013 y Skype Empresarial Server 2015 no se pueden instalar en el mismo equipo. Sin embargo, Skype Empresarial Server nodos de monitor de 2015 pueden supervisar simultáneamente Skype Empresarial Server 2015 y Lync Server 2013. Las transacciones sintéticas predeterminadas son compatibles con ambas versiones de producto. 
  
Los nodos de monitor de Lync Server 2013 pueden implementarse dentro o fuera de una empresa para ayudar a comprobar:
  
- La conectividad con los grupos de servidores de usuarios de la empresa.
    
- Conectividad a través de redes perimetrales para usuarios remotos que trabajan fuera de la empresa.
    
- La conectividad con aplicaciones de sucursal.
    
- Conectividad a Lync Server 2013 dentro de la empresa y a través de redes perimetrales.
    
Para simplificar la administración, hay diferentes opciones de autenticación disponibles para dentro y fuera de la empresa. Para obtener más información, [vea Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).
  
Para configurar un equipo para que actúe como nodo de monitor, primero debe completar los siguientes requisitos previos: 
  
- Instale System Center Operations Manager e importe los Skype Empresarial Server de administración de 2015. También debe comprobar primero que el equipo del nodo de monitor cumple todos los requisitos previos para instalar Skype Empresarial Server 2015.
    
- Instale los siguientes elementos en el equipo del nodo de monitor:
    
  - La versión completa de .NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Una vez que se cumplan los requisitos previos, puede configurar el nodo de monitor siguiendo estos pasos:
  
1. Instale los Skype Empresarial Server principales de 2015 en el equipo del nodo de monitor.
    
2. Instale System Center de Operations Manager en el equipo del nodo de monitor.
    
3. Ejecute el Watchernode.msi archivo ejecutable.
    
4. Use el cmdlet **New-CsWatcherNodeConfiguration** para configurar las cuentas de usuario de prueba que usará el nodo de monitor.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Instalar los Skype Empresarial Server principales de 2015 y la base de datos RTCLocal

Para instalar los Skype Empresarial Server principales de 2015 en un equipo, realice el siguiente procedimiento. La base de datos RTCLocal se instalará automáticamente al instalar los archivos principales. Tenga en cuenta que no es necesario instalar SQL Server en los nodos de monitor. SQL Server Express se instalará automáticamente.
  
Para instalar los Skype Empresarial Server principales de 2015 y la base de datos RTCLocal:
  
1. En el equipo nodo de supervisor, haga clic en Inicio, Todos los programas, Accesorios, haga clic con el botón secundario en Símbolo del sistema y haga clic en Ejecutar como administrador.
    
2. En la ventana de consola, escriba el siguiente comando y presione ENTRAR. Asegúrese de escribir la ruta de acceso adecuada a los archivos de instalación de Skype Empresarial Server: D:\Setup.exe /BootstrapLocalMgmtTo comprobar que los componentes principales de Skype Empresarial Server se han instalado correctamente, haga clic en Inicio **,** haga clic en Todos los programas **,** haga clic en **Skype Empresarial Server 2015**, y, a **continuación, haga clic Skype Empresarial Server Shell de administración**. En el Shell Skype Empresarial Server administración, escriba el siguiente comando Windows PowerShell y presione ENTRAR:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> La primera vez que ejecute este comando, no se devolverán datos porque aún no ha configurado ningún equipo de nodo de monitor. Si el comando se ejecuta sin devolver un error, puede suponer que el Skype Empresarial Server la instalación se completó correctamente. 
  
Si el equipo de nodo de monitor se encuentra dentro de la red perimetral, puede ejecutar el siguiente comando para comprobar la instalación de Skype Empresarial Server 2015:
  
Get-CsPinPolicyYou recibirá información similar a esta, según el número de directivas de PIN configuradas para su uso en la organización:
  
Identity : Global
  
Descripción :
  
MinPasswordLength : 5
  
PINHistoryCount : 0
  
AllowCommonPatterns : False
  
PINLifetime : 0
  
MaximumLogonAttempts :
  
Si ve información sobre las directivas de PIN, los componentes principales se han instalado correctamente.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Instalar los archivos del agente de Operation Manager en un nodo de monitor

Al igual que Skype Empresarial Server configuración para notificar alertas de componentes, un nodo de monitor Skype Empresarial Server 2015 requiere System Center archivos de agente de Operations Manager que se instalen. Esto permite ejecutar las transacciones sintéticas y las alertas se notifican al System Center de administración raíz de Operations Manager.
  
Para instalar los archivos de agente, siga los procedimientos que se indican en [Configure the Skype Empresarial Server computers that will be monitored](configure-computers-to-monitor.md).
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Configurar un nodo de monitor para ejecutar transacciones sintéticas
<a name="enable_synthetic_trans"> </a>

Después de System Center los archivos del agente de Operations Manager, debe configurar el propio nodo de monitor. Los pasos que realices para hacerlo variarán en función de si el equipo del nodo de monitor está dentro de la red perimetral o fuera de la red perimetral. 
  
Cuando configure un nodo de monitor, elija también el tipo de método de autenticación que el nodo empleará. Skype Empresarial Server 2015 permite elegir uno de los dos métodos de autenticación: Servidor de confianza o Autenticación de credenciales. En la tabla siguiente se muestran las diferencias entre estos dos métodos:
  
|&nbsp;|**Descripción**|**Ubicaciones admitidas**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Usa un certificado para representar a un servidor interno y evitar los problemas de autenticación.  <br/> Es útil para los administradores que prefieren administrar un solo certificado, en lugar de muchas contraseñas de usuario en cada nodo de monitor.  <br/> |Dentro de la empresa.  <br/> Con este método, el nodo de monitor debe estar en el mismo dominio que los grupos de servidores que se supervisan. Si el nodo de monitor y los grupos de servidores están en dominios diferentes, use la autenticación de credenciales en su lugar.  <br/> |
|Negociar  <br/> |Almacena los nombres de usuario y las contraseñas con seguridad en Windows Credential Manager en cada nodo de monitor.  <br/> Este modo requiere más administración de contraseñas, pero es la única opción para nodos de monitor fuera de la empresa. Estos nodos de monitor no se pueden tratar como un extremo de confianza para la autenticación.  <br/> |Fuera de la empresa.  <br/> Dentro de la empresa.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Configurar un nodo de monitor para usar la autenticación de servidor de confianza
<a name="enable_synthetic_trans"> </a>

Si el equipo del nodo de monitor se encuentra dentro de la red perimetral, el uso de la autenticación de servidor de confianza puede reducir considerablemente las tareas de administración manteniendo un solo certificado, en lugar de usar numerosas contraseñas de cuenta de usuario.
  
Para configurar la autenticación de servidor de confianza, primero debe crear un grupo de aplicaciones de confianza para hospedar el equipo del nodo de monitor. Después de crear el grupo de aplicaciones de confianza, debe configurar transacciones sintéticas en ese nodo de monitor para que se ejecuten como aplicaciones de confianza.
  
> [!NOTE]
> Una aplicación de confianza es una aplicación que tiene el estado de confianza para ejecutarse como parte de Skype Empresarial Server 2015, pero no es una parte integrada del producto. El estado de confianza significa que no se desafiará a la aplicación cada vez que se ejecute la autenticación.
  
Para crear un grupo de aplicaciones de confianza, abra Skype Empresarial Server Shell de administración y ejecute un comando similar al siguiente:
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Para obtener información detallada sobre los parámetros del comando anterior, escriba lo siguiente en el símbolo del Shell de administración Skype Empresarial Server: 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

Después de crear el grupo de aplicaciones de confianza, puede configurar el equipo del nodo de monitor para ejecutar transacciones sintéticas como una aplicación de confianza mediante el cmdlet **New-CsTrustedApplication** y un comando similar al siguiente:
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Cuando se complete este comando y se cree la aplicación de confianza, debe ejecutar el cmdlet **Enable-CsTopology** para asegurarse de que los cambios tienen efecto:
  
```PowerShell
Enable-CsTopology
```

La cuenta del equipo del nodo de monitor requiere la capacidad de consultar CMS para algunas transacciones sintéticas. Para permitir esta capacidad, agregue la cuenta de equipo del nodo de monitor al grupo de seguridad RTCUniversalReadOnlyAdmins. Una vez que se haya producido la replicación de AD, reinicie el equipo.
  
Para comprobar que se ha creado la nueva aplicación de confianza, escriba lo siguiente en el Skype Empresarial Server del Shell de administración:
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Configurar un certificado predeterminado en el nodo monitor
<a name="enable_synthetic_trans"> </a>

Cada nodo de monitor que use la autenticación de TrustedServer debe tener asignado un certificado predeterminado mediante el asistente Skype Empresarial Server implementación. 
  
Para asignar un certificado predeterminado:
  
1. Haga clic en Inicio, en Todos los programas, Skype Empresarial Server 2015 y, a continuación, haga clic en Skype Empresarial Server de implementación. 
    
2. En el Asistente Skype Empresarial Server implementación, haga clic en Instalar o actualizar Skype Empresarial Server Sistema y, a continuación, haga clic en Ejecutar bajo el encabezado Solicitud, Instalación o Asignar certificado. 
    
> [!NOTE]
> Si el botón Ejecutar está deshabilitado, puede que primero necesite hacer clic en Ejecutar en Instalar el almacén de configuración local. 
  
Realice una de las siguientes acciones:
  
- Si ya tiene un certificado que se puede usar como certificado predeterminado, haga clic en Predeterminado en el Asistente para certificados y, a continuación, haga clic en Asignar. Siga los pasos del Asistente para asignación de certificados para asignar ese certificado.
    
- Si necesita solicitar un certificado para usar el certificado predeterminado, haga clic en Solicitar y, a continuación, siga los pasos del Asistente para solicitud de certificado para solicitar dicho certificado. Si usa los valores predeterminados para el certificado de servidor web, recibirá un certificado que puede asignar como certificado predeterminado.
    
## <a name="install-and-configure-a-watcher-node"></a>Instalar y configurar un nodo de monitor
<a name="enable_synthetic_trans"> </a>

Después de reiniciar el equipo del nodo de monitor y configurar un certificado, debe ejecutar el archivo Watchernode.msi. (Debe ejecutar Watchernode.msi en cualquier equipo donde estén instalados tanto los archivos de agente de Operations Manager como los Skype Empresarial Server componentes principales de 2015). 
  
Para instalar y configurar un nodo de monitor:
  
1. Abra el Shell Skype Empresarial Server administración haciendo clic en Inicio, haciendo clic en Todos los programas, haciendo clic en Skype Empresarial Server 2015 y, a continuación, haciendo clic Skype Empresarial Server Shell de administración. 
    
2. En el Shell de administración, escriba el siguiente comando y, a continuación, presione ENTRAR (asegúrese de especificar la ruta de acceso real a la copia de Watchernode.msi):
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> También puede ejecutar Watchernode.msi n desde una ventana de comandos. Para abrir una ventana de comandos, haga clic en Inicio, haga clic con el botón secundario en Símbolo del sistema y luego en Ejecutar como administrador. Cuando se abra la ventana de comandos, escriba el mismo comando que se muestra en el paso 2 anterior. 
  
> [!IMPORTANT]
> En el comando anterior, el par nombre/valor Authentication=TrustedServer distingue mayúsculas de minúsculas. Debe escribirse exactamente como se muestra. Por ejemplo, este comando producirá un error porque no usa la mayúscula y minúscula correcta: 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

El modo TrustedServer solo se puede usar con equipos que se encuentran dentro de la red perimetral. Cuando un nodo de monitor se ejecuta en modo TrustedServer, los administradores no tienen que mantener las contraseñas de usuario de prueba en el equipo.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Configurar un nodo de monitor para usar Negotiate
<a name="enable_synthetic_trans"> </a>

Si el equipo de nodo de monitor se encuentra fuera de la red perimetral, debe seguir un procedimiento ligeramente diferente para configurar ese nodo de monitor para ejecutar transacciones sintéticas: en particular, no debe crear un grupo de aplicaciones de confianza o una aplicación de confianza. Esto significa que tendrá que completar las dos siguientes tareas.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Actualizar pertenencia al grupo de administradores Read-Only RTC

Si el nodo de monitor se encuentra fuera de la red perimetral, debe agregar la cuenta de servicio de red al grupo Administradores de solo lectura local rtc en el equipo del nodo de monitor completando el siguiente procedimiento en el nodo de monitor:
  
1. Haga clic en  Inicio , haga clic con el botón secundario en  Equipo  y, a continuación, haga clic en  Administrar .
    
2. En Administrador de servidores, expanda Configuración, expanda Usuarios y grupos locales y, a continuación, haga clic en Grupos.
    
3. En el panel Grupos, haga doble clic en RTC Local Read-only Administrators.
    
4. En el cuadro de diálogo Propiedades de RTC Local Read-only Administrators, haga clic en Agregar.
    
5. En el cuadro de diálogo para seleccionar usuarios, equipos, cuentas de servicio o grupos, haga clic en Ubicaciones.
    
6. En el cuadro de diálogo Ubicaciones, seleccione el nombre del equipo del nodo de observador y, a continuación, haga clic en Aceptar.
    
7. En el cuadro Escribir los nombres de objeto para seleccionar, escriba Servicio de red y, a continuación, haga clic en Aceptar.
    
8. En el cuadro de diálogo Propiedades de RTC Local Read-only Administrators, haga clic en Aceptar y, a continuación, cierre Administrador de servidores.
    
9. Reinicie el equipo del nodo de observador.
    
### <a name="install-the-watcher-node-configuration-files"></a>Instalar los archivos de configuración de nodo de monitor

El siguiente paso es ejecutar el archivo Watchernode.msi: 
  
1. Abra el Shell de administración de Microsoft Skype Empresarial Server 2015. Haga clic en Inicio, todos los programas, Microsoft Skype Empresarial Server 2015 y, a continuación, haga clic Skype Empresarial Server Shell de administración. 
    
2. En Skype Empresarial Server Shell de administración, escriba el siguiente comando y, a continuación, presione ENTRAR (asegúrese de especificar la ruta de acceso real a la copia de Watchernode.msi):
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Como se mencionó anteriormente, Watchernode.msi también se puede ejecutar desde una ventana de comandos. Para abrir una ventana de comandos, haga clic en **Inicio**, haga clic con el botón secundario en **Símbolo del sistema** y luego en **Ejecutar como administrador**. Cuando se abra la ventana de comandos, escriba el mismo comando que se muestra en el paso 2 anterior. 
  
El modo Negotiate se usa en cualquier momento que el nodo de observador no se puede configurar como un grupo de servidores de aplicaciones de confianza. En este modo, los administradores tendrá que administrar contraseñas de usuario de prueba en el nodo de observador.
  

