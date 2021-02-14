---
title: Administrar Skype Empresarial Server 2019 con el módulo de administración de SCOM
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/26/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Resumen: obtenga información sobre cómo configurar la infraestructura de Skype Empresarial Server 2019 para que funcione con System Center Operations Manager.'
ms.openlocfilehash: 21493a0d49281405b4d9d25d732f9c80c6c9dff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812780"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>Administrar Skype Empresarial Server 2019 con el módulo de administración de SCOM
 
**Resumen:** Obtenga información sobre cómo configurar la infraestructura de Skype Empresarial Server 2019 para que funcione con System Center Operations Manager.
  
In an ideal world, you'd never encounter issues with Skype for Business Server 2019. Sin embargo, Skype Empresarial Server puede verse afectado por factores externos, por ejemplo, bloqueos de red y errores de hardware. Al usar los módulos de administración de Skype Empresarial Server 2019, puede identificar y solucionar posibles problemas de forma proactiva. De este modo, los módulos de administración de Skype Empresarial Server 2019 amplían las capacidades de System Center Operations Manager.
  
Esta información se escribió basándose en la versión 9319.0 del módulo de supervisión para el software de comunicaciones de Skype Empresarial Server 2019.
  
## <a name="configuration-overview"></a>Descripción general de la configuración

 Para configurar la infraestructura de Skype Empresarial Server 2019 para que funcione con System Center Operations Manager, debe hacer tres cosas:
  
Identifique y [configure el servidor de administración principal.](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md) Para ello, debe instalar System Center Operations Manager 2012 SP1 o R2. 
  
 Identifique y [configure los equipos de Skype Empresarial Server que se supervisarán.](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md) Para supervisar un equipo de Skype Empresarial Server mediante System Center Operations Manager, debe instalar los archivos de agente de System Center Operations Manager y configurar cada servidor para que actúe como proxy. 
  
 Identificar e [instalar y configurar nodos de monitor.](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md) Los nodos de monitor son equipos que ejecutan periódicamente transacciones sintéticas de Skype Empresarial Server( cmdlets Windows PowerShell que comprueban que los componentes clave de Skype Empresarial Server, como la capacidad de iniciar sesión en el sistema o la capacidad de intercambiar mensajes instantáneos, funcionan según lo esperado. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Servidor de administración raíz de System Center Operations Manager y compatibilidad con agentes

Los módulos de administración se pueden usar con System Center Operations Manager 2007 R2 (64 bits) o System Center Operations Manager 2012 SP1 &amp; R2 (64 bits). En la tabla siguiente se muestran las configuraciones admitidas para los módulos de administración de Skype Empresarial Server 2019: 
  
|**Configuración**|**¿Se admite?**|
|:-----|:-----|
|Sistema operativo Windows Server 2008 R2  <br/> Sistema operativo Windows Server 2012 R2  <br/> |Sí. Tanto en el servidor de Skype Empresarial Server 2019 como en los nodos de monitor de transacciones sintéticas.  <br/> |
|Servidores agrupados  <br/> |No admitida.  <br/> |
|Supervisión sin agente  <br/> |No admitida.  <br/> |
|Entorno virtual  <br/> |Sí.  <br/> |
|Roles de servidor unidos a un dominio  <br/> |Todos los roles de servidor internos de Skype Empresarial Server 2019 deben estar unidos a un dominio.  <br/> |
|Roles de servidor independientes  <br/> |No es necesario que los servidores perimetrales de Skype Empresarial Server 2019 estén unidos a un dominio.  <br/> |
|Limitaciones de topología  <br/> |Todos los roles de servidor de una implementación deben supervisarse desde el mismo grupo de administración de Operations Manager.  <br/> |
|Nodo de monitor de transacciones sintéticas  <br/> |Se admite la disponibilidad del escenario de supervisión con un nodo de monitor de transacciones sintéticas (se requiere configuración adicional). No es necesario que los nodos de monitor estén unidos a un dominio.  <br/> |
   
En la tabla siguiente se muestran los requisitos de capacidad y sistema operativo para un nodo de monitor de transacciones sintéticas:
  
|**Componente de hardware**|**Requisito mínimo**|
|:-----|:-----|
|CPU  <br/> |Uno de los siguientes:  <br/> Procesador de 64 bits, cuatro núcleos, 2,33 GHz o superior  <br/> Procesador 2 vías de 64 bits, doble núcleo, 2,33 GHz o superior  <br/> |
|Memoria  <br/> |8 GB  <br/> |
|Sistema operativo  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Red  <br/> |1 adaptador de red a 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>Requisitos previos

Para ejecutar un nodo de monitor de transacciones sintéticas, primero debe instalar lo siguiente:
  
- System Center Operations Manager Agent 
    
-  Microsoft .NET Framework 4.5
    
- Archivos de instalación principales de Skype Empresarial Server (OcsCore.msi) y API administrada de comunicaciones unificadas (UCMA) (las versiones deben coincidir con la versión WatcherNode.msi Skype Empresarial Server)
    
## <a name="files-in-this-monitoring-pack"></a>Archivos de este módulo de supervisión

El módulo de supervisión de Skype Empresarial Server 2019 incluye los siguientes archivos:
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Novedades

Las siguientes características son nuevas en los módulos de administración de Skype Empresarial Server 2019.

- **Cambios en [la actualización de septiembre de 2019](https://www.microsoft.com/download/details.aspx?id=57511)** Algunas alertas han quitado caracteres especiales. En algunos casos, los caracteres especiales interfieren con la característica de notificación del canal de comandos SCOM.

- **Detección automática para el inicio de sesión de cliente** Las aplicaciones cliente que inician sesión en Skype Empresarial Server 2019 suelen detectar automáticamente el servidor en el que iniciar sesión. Las transacciones sintéticas ahora admiten la comprobación de que la detección automática está configurada correctamente.
    
- **Intervalos de ejecución de transacciones sintéticas personalizados** Para simplificar el proceso de configuración de los nodos de monitor, las transacciones sintéticas pueden compartir cuentas de usuario. Esto ralentiza la frecuencia con la que se ejecutan las pruebas a medida que se serializan para evitar conflictos. De forma predeterminada, las transacciones sintéticas se ejecutan cada 15 minutos para garantizar que todas las pruebas tengan tiempo de ejecución. Los administradores que eligen usar más usuarios o menos pruebas por usuario también pueden reducir el intervalo de ejecución.
    
- **Transacción sintética de servicios de interoperabilidad de vídeo** Los clientes que migran a Skype Empresarial Server 2019 desde otras soluciones de proveedores a menudo desean seguir usando los dispositivos de teleconferencia de vídeo (VTC) de estos otros proveedores. El servidor de interoperabilidad de vídeo es un nuevo rol de servidor de Skype Empresarial Server 2019 que permite a los clientes seguir usando VTC de Cisco en sus salas de conferencias conectándose a Cisco CUCM a través de un tronco SIP de vídeo. Esta característica también agrega una transacción sintética para ayudar a comprobar que el servidor de interoperabilidad de vídeo está funcionando y puede controlar las conexiones entrantes a través de un tronco SIP de vídeo.
    
- **Transacción sintética de conferencia de uso compartido de aplicaciones** Ahora se admite la validación de un escenario de un extremo a otro para conferencias de uso compartido de aplicaciones.
    
## <a name="monitoring-scenarios"></a>Escenarios de supervisión

El módulo de administración de Skype Empresarial Server 2019 aprovecha una variedad de características para ayudarle a detectar y diagnosticar problemas. Estas características proporcionan visibilidad en tiempo real del estado de un entorno de Skype Empresarial Server 2019.
  
|**Escenario de supervisión**|**Descripción**|
|:-----|:-----|
|Transacciones sintéticas  <br/> | Windows PowerShell cmdlets para probar y ayudar a garantizar la alta disponibilidad de escenarios como el inicio de sesión, la presencia, la mensajería instantánea y las conferencias para los usuarios. <br/> Las transacciones sintéticas se pueden ejecutar desde cualquier ubicación geográfica, incluso dentro de la empresa, fuera de la empresa y en las sucursales.  <br/> Cuando se produce un error en una transacción sintética, los registros HTML se crean para ayudar a determinar la naturaleza exacta del error. Esto incluye comprender qué acción produjo un error, la latencia de cada acción, la línea de comandos usada para ejecutar la prueba y el error específico que se produjo.  <br/> |
|Alertas de confiabilidad de llamadas  <br/> |Los registros de detalles de llamadas (CDR) escritos por los servidores de Skype Empresarial Server 2019 reflejan si los usuarios pueden conectarse a una llamada o por qué se termina una llamada. Las alertas de confiabilidad de llamadas consultan la base de datos de CDR para generar alertas que indican cuándo un gran número de usuarios experimentan problemas de conectividad para las llamadas punto a punto o la funcionalidad de conferencia básica.  <br/> La cobertura de escenarios incluye llamadas de audio, mensajería instantánea (MI) punto a punto y otras características de conferencia.  <br/> |
|Alertas de calidad de medios  <br/> |Consultas de base de datos que buscan informes de calidad de la experiencia (QoE) publicados por clientes de Skype Empresarial Server 2019 al final de cada llamada. Estas consultas producen alertas que localizan escenarios en los que es más probable que los usuarios experimente una calidad de medios comprometida durante las llamadas y conferencias. Los datos se basa en métricas clave, como la latencia de paquetes y la pérdida, que contribuyen directamente a la calidad de la experiencia del usuario.  <br/> |
|Alertas de mantenimiento de componentes  <br/> |Los componentes de servidor individuales elevan alertas a través de registros de eventos y contadores de rendimiento para indicar condiciones de error que pueden afectar significativamente a los escenarios de usuario. Estas alertas indican una variedad de condiciones, como servicios que no se ejecutan, altas tasas de errores, latencia de mensajes alta o problemas de conectividad.  <br/> |
|Supervisión del estado de dependencia  <br/> |Skype Empresarial Server puede producir errores por diversos motivos externos. El módulo de administración supervisa y recopila datos de dependencias externas críticas que pueden indicar problemas graves. Estas dependencias incluyen la disponibilidad de Internet Information Services (IIS) y la CPU de los servidores usados para Skype Empresarial Server.  <br/> |
   
### <a name="alert-prioritization"></a>Priorización de alertas

Las alertas se clasifican en las siguientes categorías: 
  
 **Alertas de prioridad alta:** Estas alertas indican condiciones que provocan interrupciones del servicio para grandes grupos de usuarios y requieren una acción inmediata. Las interrupciones detectadas por transacciones sintéticas y servicios sin conexión (como las conferencias de audio y vídeo de Skype Empresarial Server) se califican como alertas de prioridad alta. Por el contrario, un error de componente en una sola máquina no es una alerta de prioridad alta. Skype Empresarial Server 2019 tiene características de alta disponibilidad integradas para estas situaciones, por ejemplo, varios servidores front-end detrás de equilibradores de carga.
  
 **Alertas de prioridad media:** Estas alertas indican condiciones que afectan a un subconjunto de usuarios o indican problemas en la calidad de la llamada, por ejemplo, errores de componentes, latencia en el establecimiento de llamadas o menor calidad de audio en las llamadas. Las alertas de esta categoría son con estado (es decir, la naturaleza de la alerta cambia en función del estado de la conexión de red). Por ejemplo, si los tiempos de establecimiento de llamadas indican latencia pero, a continuación, vuelven a un umbral normal, esta alerta de prioridad media se resolvería automáticamente en System Center Operations Manager y los administradores no tendrían que realizar ninguna acción. Los administradores suelen abordar las alertas que no se pueden resolver automáticamente en el mismo día laborable.
  
 **Otras alertas:** Estas alertas se generan a partir de componentes que pueden afectar a un usuario específico o a un subconjunto de usuarios. Por ejemplo, una alerta típica sería que el servicio de libreta de direcciones no puede analizar la entrada de Active Directory® Domain Services (AD DS) para el usuario: testuser@contoso.com. Los administradores pueden abordar estas alertas siempre que tengan tiempo disponible.
  
### <a name="synthetic-transactions"></a>Transacciones sintéticas

Los módulos de administración de Skype Empresarial Server 2019 proporcionan mayor cobertura para las alertas a través de transacciones sintéticas. Las transacciones sintéticas Windows PowerShell cmdlets integrados en el módulo de administración de Operations Manager para probar escenarios de usuario de un extremo a otro. Cuando designa un servidor para ejecutar transacciones sintéticas, el módulo de administración desencadena periódicamente estos cmdlets. Los errores resultantes de una transacción sintética generan una alerta con estado. Estas son las transacciones sintéticas compatibles con Skype Empresarial Server 2019:
  
**Transacciones sintéticas admitidas para el registro, la presencia y los contactos**

||||
|:-----|:-----|:-----|
|1   <br/> |Registro (inicio de sesión de usuario)  <br/> |Lync Server 2010 y posteriores disponibles  <br/> |
|2   <br/> |Servicio de libreta de direcciones (descarga de archivos)  <br/> |Lync Server 2010 y posteriores disponibles  <br/> |
|3   <br/> |Consulta web de la libreta de direcciones  <br/> |Lync Server 2010 y posteriores disponibles  <br/> |
|4   <br/> |Presencia  <br/> |Lync Server 2010 y posteriores disponibles  <br/> |
|5   <br/> |Almacén de contactos unificado  <br/> |Lync Server 2013 y posteriores disponibles  <br/> |
   
**Transacciones sintéticas admitidas para servicios punto a punto**

||||
|:-----|:-----|:-----|
|6   <br/> |Mensajería instantánea punto a punto  <br/> |Disponible en Lync Server 2010 y posteriores  <br/> |
|7   <br/> |Vídeo de audio punto a punto  <br/> |Disponible en Lync Server 2010 y posteriores  <br/> |
|8   <br/> |Mensaje instantáneo punto a punto de MCX (móvil)  <br/> |Disponible en la versión de septiembre de 2011 de Lync Server 2010 para Skype Empresarial 2019  <br/> |
 
> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes móviles actuales de Skype Empresarial ya usan la API web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (MI), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
**Transacciones sintéticas admitidas para conferencias y chat persistente**

||||
|:-----|:-----|:-----|
|9   <br/> |Conferencia de audio y videoconferencia  <br/> |Disponible en Lync Server 2010 y posteriores  <br/> |
|10    <br/> |Conferencia de datos  <br/> |Disponible en Lync Server 2013 y posteriores  <br/> |
|11   <br/> |Conferencia de mensajes instantáneos  <br/> |Disponible en Lync Server 2010 y posteriores  <br/> |
|12   <br/> | Chat persistente <br/> |Disponible en Lync Server 2013 y posteriores  <br/> |
|13   <br/> |Unirse Selector (reuniones programadas)  <br/> |Disponible en Lync Server 2013 y posteriores  <br/> |
|14   <br/> |Conferencias de acceso telefónico local  <br/> |Disponible en Skype Empresarial Server 2015 y posteriores <br/> |
|15   <br/> |Conferencia de uso compartido de aplicaciones  <br/> |Disponible en Skype Empresarial Server 2015 y posteriores <br/> |
|16   <br/> |Conferencia de UCWA (participación en reuniones web)  <br/> |Disponible en Skype Empresarial Server 2015 y posteriores <br/> |
   
**Transacciones sintéticas admitidas para dependencias de socios y redes**

||||
|:-----|:-----|:-----|
|17   <br/> |Conectividad perimetral av  <br/> |Disponible en Lync Server 2013 y posteriores  <br/> |
|18   <br/> |Conectividad perimetral av Conectividad de mensajes unificados de Exchange (correo de voz)  <br/> |Disponible en Lync Server 2013 y posteriores  <br/> |
|19  <br/> |Llamada punto a punto rtc  <br/> |Disponible en Lync Server 2010 y posteriores  <br/> |
|20  <br/> |Mensajería instantánea XMPP (federación)  <br/> |Disponible en Lync Server 2013 y posteriores  <br/> |
| 21  <br/> |Servidor de interoperabilidad de vídeo  <br/> |Disponible en Skype Empresarial Server 2015 y posteriores  <br/> |
   
## <a name="how-health-rolls-up"></a>Cómo se revierte el mantenimiento

En la tabla siguiente se muestran los estados de mantenimiento de los objetos del módulo de supervisión de Skype Empresarial Server.
  
|**Management Pack (objeto)**|**Descripción**|
|:-----|:-----|
|Implementación de Skype Empresarial Server  <br/> |Representa la implementación de Skype Empresarial Server 2019 en la organización.  <br/> |
|Sitio de Skype Empresarial Server  <br/> |Representa diferentes ubicaciones geográficas donde se implementan los servicios.  <br/> |
|Grupo de servidores de Skype Empresarial  <br/> |Un grupo de servidores (dentro de un sitio) que proporciona servicios de comunicación, como mensajería instantánea y conferencias, a los usuarios. Se aplica a grupos de servidores front-end, grupos de servidores perimetrales y grupos de directores, incluso si solo hay un único equipo en un grupo determinado.  <br/> |
|Rol de Skype Empresarial Server  <br/> |Un rol de servidor que hospeda el servicio Skype Empresarial Server.  <br/> |
|Servicio de Skype Empresarial Server  <br/> |Representa una funcionalidad implementada en un equipo específico (por ejemplo, servicio de usuario en fp01.contoso.com).  <br/> |
|Componente de Skype Empresarial Server  <br/> |Un componente del servicio (por ejemplo, el componente de descarga de libreta de direcciones forma parte del servicio web).  <br/> |
|Watcher del grupo de servidores de Skype Empresarial Server  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo de servidores.  <br/> |
|Watcher de registrador de Skype Empresarial Server  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo de registradores.  <br/> |
|Watcher del grupo de servicios de usuario de Skype Empresarial Server  <br/> |Una instancia de transacciones sintéticas que se ejecutan en un grupo de servicios de usuario.  <br/> |
|Watcher del grupo de voz de Skype Empresarial Server  <br/> |Una instancia de transacciones sintéticas que se ejecutan en un grupo de servidores de voz.  <br/> |
|Portabilidad de Skype Empresarial Server  <br/> |Una instancia de comprobaciones de puerto que se ejecuta en un grupo de servidores.  <br/> |
|Simple URL Watcher  <br/> |Realiza el sondeo HTTPS de las direcciones URL sencillas configuradas en una implementación.  <br/> |
   
![Paquete acumulativo de SCOM](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Un grupo de Skype Empresarial Server puede contener varios sistemas individuales de Skype Empresarial Server (con más de un rol de Skype Empresarial Server, servicio Skype Empresarial Server y componente de Skype Empresarial Server). Por lo tanto, el error de un componente o servidor individual es menos crítico para el mantenimiento general del grupo de Skype Empresarial Server, ya que otros servidores del mismo grupo pueden proporcionar el servicio de aplicación al cliente. The health will roll up on a percentage level to the Skype for Business Server pool. 
  
El watcher del grupo de servidores de Skype Empresarial Server realiza transacciones sintéticas en un grupo de Skype Empresarial Server. Si se produce un error consecutivo en una o más transacciones sintéticas (un proceso conocido como intervalo de sondeo consecutivo), el estado de mantenimiento crítico se revertirá al nivel del grupo de servidores (el peor de cualquier transacción sintética), como se muestra en el siguiente diagrama. 
  
![Sondeo consecutivo del paquete acumulativo de SCOM](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Procedimiento recomendado: Crear un módulo de administración para personalizaciones

De forma predeterminada, Operations Manager guarda todas las personalizaciones, como invalidaciones en el módulo de administración predeterminado. Como procedimiento recomendado, debe crear un módulo de administración independiente para cada módulo de administración sellado que desee personalizar. 
  
Al crear un módulo de administración para almacenar la configuración personalizada de un módulo de administración sellado, se recomienda asignar un nombre adecuado al nuevo módulo de administración, como "Personalizaciones de Skype Empresarial Server 2019".
  
La creación de un nuevo módulo de administración para almacenar las personalizaciones de cada módulo de administración sellado facilita la exportación de las personalizaciones de un entorno de prueba a un entorno de producción. Esto también facilita la eliminación de un módulo de administración, ya que debe eliminar las dependencias antes de poder eliminar un módulo de administración. Si las personalizaciones de todos los módulos de administración se guardan en el módulo de administración predeterminado y necesita eliminar un único módulo de administración, primero debe eliminar el módulo de administración predeterminado, que también elimina las personalizaciones de otros módulos de administración. 
  
## <a name="links"></a>Vínculos

Los siguientes vínculos le conectan a información sobre tareas comunes asociadas a System Center 2012 módulos de supervisión:
  
- [Ciclo de vida del módulo de administración](https://technet.microsoft.com/library/hh212732.aspx)
    
- [Cómo importar un módulo de administración en Operations Manager 2012](https://technet.microsoft.com/library/hh212691.aspx)
    
- [Cómo invalidar una regla o un monitor](https://technet.microsoft.com/library/hh212869.aspx)
    
- [Cómo crear una cuenta ejecutar como en Operations Manager 2012](https://technet.microsoft.com/library/hh321655.aspx)
    
- [Administración de cuentas y perfiles ejecutados como](https://technet.microsoft.com/library/hh212714.aspx)
    
- [Cómo exportar un módulo de administración de Operations Manager](https://technet.microsoft.com/library/hh320149.aspx)
    
- [Cómo quitar un módulo de administración de Operations Manager](https://technet.microsoft.com/library/hh230746.aspx)
    
Los siguientes vínculos le conectan a información sobre tareas comunes asociadas con los módulos de supervisión de System Center 2007:
  
- [Administración del ciclo de vida del módulo de administración](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Cómo importar un módulo de administración en Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Cómo supervisar el uso de invalidaciones](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Cómo crear una cuenta ejecutar como en Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Cómo modificar un perfil de ejecución existente](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Cómo exportar personalizaciones del módulo de administración](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Cómo quitar un módulo de administración](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Para obtener preguntas sobre Operations Manager y los paquetes de supervisión, consulte el foro de la comunidad de [System Center Operations Manager.](https://go.microsoft.com/fwlink/p/?LinkID=179635)
  
Un recurso útil es el blog [de System Center Operations Manager Unleashed,](https://opsmgrunleashed.wordpress.com/) que contiene entradas "Por ejemplo" para paquetes de supervisión específicos.
  
Para obtener información adicional acerca de Operations Manager, consulte los blogs siguientes: 
  
- [Blog del equipo de Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog de OpsMgr de Diego Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Ideas sobre OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog de Arrai Burri](https://rburri.wordpress.com/)
    
- [Espacio de administración de BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Toda la información y el contenido de los sitios que no sean propiedad de Microsoft han sido proporcionados por el propietario o los usuarios del sitio web. Microsoft no ofrece ninguna garantía, expresa, implícita o legal, en cuanto a la información de este sitio web. 
  
## <a name="see-also"></a>Vea también

[Herramientas de administración de Skype Empresarial Server 2019](../management-tools-2019.md)
