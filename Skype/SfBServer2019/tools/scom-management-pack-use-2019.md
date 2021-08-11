---
title: Administrar Skype Empresarial Server 2019 con SCOM Management Pack
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
description: 'Summary: Learn how to configure your Skype Empresarial Server 2019 infrastructure to work with System Center Operations Manager.'
ms.openlocfilehash: 2bb6e5600430cf8222d799fd42bade275d4e2f6d27fc6f6c4bfc05faad0e486d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277505"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>Administrar Skype Empresarial Server 2019 con SCOM Management Pack
 
**Resumen:** Obtenga información sobre cómo configurar la infraestructura Skype Empresarial Server 2019 para que funcione con System Center Operations Manager.
  
In an ideal world, you'd never encounter issues with Skype Empresarial Server 2019. Sin embargo, Skype Empresarial Server pueden verse afectados por factores externos, por ejemplo, bloqueos de red y errores de hardware. Al usar Skype Empresarial Server de administración de 2019, puede identificar y solucionar posibles problemas de forma proactiva. De este modo, los Skype Empresarial Server de administración de 2019 amplían las capacidades de System Center Operations Manager.
  
Esta información se escribió basándose en la versión 9319.0 del módulo de supervisión para Skype Empresarial Server de comunicaciones de 2019.
  
## <a name="configuration-overview"></a>Descripción general de la configuración

 Para configurar la infraestructura Skype Empresarial Server 2019 para que funcione con System Center Operations Manager, debe hacer tres cosas:
  
Identificar y [configurar el servidor de administración principal](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md). Para ello, debe instalar System Center Operations Manager 2012 SP1 o R2. 
  
 Identifique y [configure los Skype Empresarial Server equipos que se supervisarán.](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md) Para supervisar un equipo Skype Empresarial Server mediante System Center Operations Manager, debe instalar los archivos de agente de System Center Operations Manager y configurar cada servidor para que actúe como proxy. 
  
 Identificar e [instalar y configurar nodos de monitor.](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md) Los nodos de monitor son equipos que ejecutan periódicamente transacciones sintéticas Windows PowerShell cmdlets que comprueban que los componentes clave de Skype Empresarial Server, como la capacidad de iniciar sesión en el sistema o la capacidad de intercambiar mensajes instantáneos, funcionan según lo esperado. Skype Empresarial Server 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Soporte técnico de agente y servidor de administración raíz de Operations Manager

Los módulos de administración se pueden usar con System Center Operations Manager 2007 R2 (64 bits) (compatible solo con fines de migración) o System Center Operations Manager 2012 SP1 &amp; R2 (64 bits). En la tabla siguiente se muestran las configuraciones admitidas para los módulos de administración para Skype Empresarial Server 2019: 
  
|**Configuración**|**¿Es compatible?**|
|:-----|:-----|
|Sistema operativo Windows Server 2008 R2  <br/> Windows Server 2012 Sistema operativo R2  <br/> |Sí. Tanto en Skype Empresarial Server servidor de 2019 como en nodos de monitor de transacciones sintéticas.  <br/> |
|Servidores agrupados  <br/> |No admitida.  <br/> |
|Supervisión sin agente  <br/> |No admitida.  <br/> |
|Entorno virtual  <br/> |Sí.  <br/> |
|Roles de servidor unidos a un dominio  <br/> |Todos los Skype Empresarial Server servidores internos de 2019 deben estar unidos a un dominio.  <br/> |
|Roles de servidor independientes  <br/> |Skype Empresarial Server no es necesario que los servidores perimetrales de 2019 estén unidos a un dominio.  <br/> |
|Limitaciones de topología  <br/> |Todos los roles de servidor de una implementación deben supervisarse desde el mismo grupo de administración de Operations Manager.  <br/> |
|Nodo de monitor de transacciones sintéticas  <br/> |Se admite la disponibilidad de escenarios de supervisión con un nodo de monitor de transacciones sintéticas (se requiere una configuración adicional). Los nodos de monitor no son necesarios para unirse a un dominio.  <br/> |
   
En la tabla siguiente se muestran los requisitos de capacidad y sistema operativo para un nodo de monitor de transacciones sintéticas:
  
|**Componente de hardware**|**Requisito mínimo**|
|:-----|:-----|
|CPU  <br/> |Uno de los siguientes:  <br/> Procesador de 64 bits, cuatro núcleos, 2,33 GHz o superior  <br/> Procesador de 2 vías de 64 bits, doble núcleo, 2,33 GHz o superior  <br/> |
|Memoria  <br/> |8 GB  <br/> |
|Sistema operativo  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Red  <br/> |1 adaptador de red a 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>Requisitos previos

Para ejecutar un nodo de monitor de transacciones sintéticas, primero debe instalar lo siguiente:
  
- System Center Agente de Operations Manager 
    
-  Microsoft .NET Framework 4.5
    
- Skype Empresarial Server archivos de instalación principales (OcsCore.msi) y LA API administrada de comunicaciones unificadas (UCMA) (las versiones deben coincidir con la Skype Empresarial Server WatcherNode.msi anterior)
    
## <a name="files-in-this-monitoring-pack"></a>Archivos de este módulo de supervisión

El paquete de supervisión para Skype Empresarial Server 2019 incluye los siguientes archivos:
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Novedades

Las siguientes características son nuevas para Skype Empresarial Server de administración de 2019.

- **Cambios en [la actualización de septiembre de 2019](https://www.microsoft.com/download/details.aspx?id=57511)** Algunas alertas han quitado caracteres especiales. En algunos casos, los caracteres especiales interfieren con la característica de notificación del canal de comandos SCOM.

- **Detección automática para inicio de sesión de cliente** Las aplicaciones cliente que inician sesión en Skype Empresarial Server 2019 suelen detectar automáticamente el servidor al que iniciar sesión. Las transacciones sintéticas ahora admiten la comprobación de que la detección automática está configurada correctamente.
    
- **Intervalos de ejecución de transacciones sintéticas personalizadas** Para simplificar el proceso de configuración de los nodos de monitor, las transacciones sintéticas pueden compartir cuentas de usuario. Esto ralentiza la frecuencia con la que se ejecutan las pruebas a medida que se serializan las pruebas para evitar conflictos. De forma predeterminada, las transacciones sintéticas se ejecutan cada 15 minutos para garantizar que todas las pruebas tienen tiempo para ejecutarse. Los administradores que decidan usar más usuarios o menos pruebas por usuario también pueden reducir el intervalo de ejecución.
    
- **Transacción sintética de Servicios de interoperabilidad de vídeo** Los clientes que migran a Skype Empresarial Server 2019 desde otras soluciones de proveedores a menudo desean seguir usando los dispositivos de videoconferencia (VTC) de estos otros proveedores. Video Interop Server es un nuevo rol de servidor Skype Empresarial Server 2019 que permite a los clientes seguir usando Cisco VTCs en sus salas de conferencias mediante la conexión a Cisco CUCM a través de un tronco SIP de vídeo. Esta característica también agrega una transacción sintética para ayudar a comprobar que el servidor de interoperabilidad de vídeo está funcionando y puede controlar las conexiones entrantes a través de un tronco SIP de vídeo.
    
- **Transacción sintética de conferencia de uso compartido de aplicaciones** Ahora se admite la validación de escenarios de extremo a extremo para conferencias de uso compartido de aplicaciones.
    
## <a name="monitoring-scenarios"></a>Escenarios de supervisión

El Skype Empresarial Server 2019 Management Pack aprovecha una variedad de características para ayudarle a detectar y diagnosticar problemas. Estas características proporcionan visibilidad en tiempo real del estado de un Skype Empresarial Server de 2019.
  
|**Escenario de supervisión**|**Description**|
|:-----|:-----|
|Transacciones sintéticas  <br/> | Windows PowerShell cmdlets para probar y ayudar a garantizar la alta disponibilidad de escenarios como inicio de sesión, presencia, mensajería instantánea y conferencias para los usuarios. <br/> Las transacciones sintéticas se pueden ejecutar desde cualquier ubicación geográfica, incluso dentro de la empresa, fuera de la empresa y en sucursales.  <br/> Cuando se produce un error en una transacción sintética, los registros HTML se crean para ayudar a determinar la naturaleza exacta del error. Esto incluye comprender qué acción falló, la latencia de cada acción, la línea de comandos usada para ejecutar la prueba y el error específico que se produjo.  <br/> |
|Alertas de confiabilidad de llamadas  <br/> |Los registros de detalles de llamadas (CDR) escritos por Skype Empresarial Server servidores de 2019 reflejan si los usuarios pueden conectarse a una llamada o por qué finaliza una llamada. Las alertas de confiabilidad de llamadas consultan la base de datos de CDR para producir alertas que indican cuándo un gran número de usuarios experimentan problemas de conectividad para las llamadas punto a punto o la funcionalidad básica de conferencia.  <br/> La cobertura del escenario incluye llamadas de audio, mensajería instantánea punto a punto (MI) y otras características de conferencia.  <br/> |
|Alertas de calidad de medios  <br/> |Consultas de base de datos que miran los informes de calidad de la experiencia (QoE) publicados por Skype Empresarial Server 2019 al final de cada llamada. Estas consultas producen alertas que localizan escenarios en los que es más probable que los usuarios experimente una calidad de medios comprometida durante las llamadas y conferencias. Los datos se basa en métricas clave, como la latencia y la pérdida de paquetes, que contribuyen directamente a la calidad de la experiencia del usuario.  <br/> |
|Alertas de estado de componentes  <br/> |Los componentes de servidor individuales elevan alertas a través de registros de eventos y contadores de rendimiento para indicar condiciones de error que pueden afectar significativamente a los escenarios de usuario. Estas alertas indican una variedad de condiciones, como servicios que no se ejecutan, tasas de error elevadas, latencia de mensajes alta o problemas de conectividad.  <br/> |
|Supervisión del estado de dependencia  <br/> |Skype Empresarial Server puede producir un error por diversos motivos externos. El Módulo de administración supervisa y recopila datos de dependencias externas críticas que pueden indicar problemas graves. Estas dependencias incluyen Internet Information Services (IIS) y CPU de servidores usados para Skype Empresarial Server.  <br/> |
   
### <a name="alert-prioritization"></a>Priorización de alertas

Las alertas se clasifican en las siguientes categorías: 
  
 **Alertas de prioridad alta:** Estas alertas indican condiciones que causan interrupciones del servicio para grupos grandes de usuarios y requieren una acción inmediata. Las interrupciones detectadas por transacciones sintéticas y servicios sin conexión (como Skype Empresarial Server conferencias de audio y vídeo) se califican como alertas de alta prioridad. En cambio, un error de componente en una sola máquina no es una alerta de prioridad alta. Skype Empresarial Server 2019 tiene características integradas de alta disponibilidad para estas situaciones, por ejemplo, varios servidores front-end detrás de equilibradores de carga.
  
 **Alertas de prioridad media:** Estas alertas indican condiciones que afectan a un subconjunto de usuarios o indican problemas en la calidad de la llamada, por ejemplo, errores de componentes, latencia en el establecimiento de llamadas o menor calidad de audio en las llamadas. Las alertas de esta categoría son con estado (es decir, la naturaleza de los cambios de alerta en función del estado de la conexión de red). Por ejemplo, si los tiempos de establecimiento de llamadas indican latencia pero, a continuación, vuelven a un umbral normal, esta alerta de prioridad media se resolvería automáticamente en System Center Operations Manager y los administradores no tendrían que tomar medidas. Las alertas que no se pueden resolver automáticamente suelen ser dirigidas por los administradores en el mismo día laborable.
  
 **Otras alertas:** Estas alertas se generan a partir de componentes que pueden afectar a un usuario específico o subconjunto de usuarios. Por ejemplo, una alerta típica sería que el servicio de libreta de direcciones no podía analizar la entrada de Active Directory® Domain Services (AD DS) para el usuario: testuser@contoso.com. Los administradores pueden abordar estas alertas siempre que tengan tiempo disponible.
  
### <a name="synthetic-transactions"></a>Transacciones sintéticas

Skype Empresarial Server módulos de administración de 2019 proporcionan una mayor cobertura para las alertas a través de transacciones sintéticas. Las transacciones sintéticas Windows PowerShell cmdlets integrados en el módulo de administración de Operations Manager para probar escenarios de usuario de extremo a extremo. Cuando designa un servidor para ejecutar transacciones sintéticas, el módulo de administración desencadena periódicamente estos cmdlets. Los errores resultantes de una transacción sintética generan una alerta con estado. Aquí se admiten transacciones sintéticas para Skype Empresarial Server 2019:
  
**Transacciones sintéticas admitidas para registro, presencia y contactos**

||||
|:-----|:-----|:-----|
|1  <br/> |Registro (inicio de sesión de usuario)  <br/> |Lync Server 2010 y posteriores disponibles  <br/> |
|2  <br/> |Servicio de libreta de direcciones (descarga de archivos)  <br/> |Lync Server 2010 y posteriores disponibles  <br/> |
|3  <br/> |Consulta web de la libreta de direcciones  <br/> |Lync Server 2010 y posteriores disponibles  <br/> |
|4   <br/> |Presencia  <br/> |Lync Server 2010 y posteriores disponibles  <br/> |
|5   <br/> |Almacén de contactos unificado  <br/> |Lync Server 2013 y posteriores disponibles  <br/> |
   
**Transacciones sintéticas admitidas para servicios punto a punto**

||||
|:-----|:-----|:-----|
|6   <br/> |Mensajería instantánea punto a punto  <br/> |Disponible en Lync Server 2010 y posteriores  <br/> |
|7   <br/> |Vídeo de audio punto a punto  <br/> |Disponible en Lync Server 2010 y posteriores  <br/> |
|8   <br/> |Mensaje instantáneo punto a punto de MCX (móvil)  <br/> |Disponible en la versión de septiembre de 2011 de Lync Server 2010 a Skype Empresarial 2019  <br/> |
 
> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype Empresarial Server 2019. Todos los clientes Skype Empresarial móviles ya usan la API web de comunicaciones unificadas (UCWA) para admitir mensajería instantánea (MI), presencia y contactos. Los usuarios con clientes heredados que usen MCX tendrán que actualizar a un cliente actual.
  
**Transacciones sintéticas admitidas para conferencias y chat persistente**

||||
|:-----|:-----|:-----|
|9   <br/> |Conferencia de audio y videoconferencia  <br/> |Disponible en Lync Server 2010 y posteriores  <br/> |
|10   <br/> |Conferencia de datos  <br/> |Disponible en Lync Server 2013 y posteriores  <br/> |
|11  <br/> |Conferencia de mensajes instantáneos  <br/> |Disponible en Lync Server 2010 y posteriores  <br/> |
|12   <br/> | Chat persistente <br/> |Disponible en Lync Server 2013 y posteriores  <br/> |
|13  <br/> |Unirse Selector (reuniones programadas)  <br/> |Disponible en Lync Server 2013 y posteriores  <br/> |
|14   <br/> |Conferencia de acceso telefónico local  <br/> |Disponible en Skype Empresarial Server 2015 y posteriores <br/> |
|15  <br/> |Conferencia de uso compartido de aplicaciones  <br/> |Disponible en Skype Empresarial Server 2015 y posteriores <br/> |
|16   <br/> |Conferencia UCWA (unirse a una reunión web)  <br/> |Disponible en Skype Empresarial Server 2015 y posteriores <br/> |
   
**Transacciones sintéticas admitidas para dependencias de red y partners**

||||
|:-----|:-----|:-----|
|17   <br/> |Conectividad perimetral av  <br/> |Disponible en Lync Server 2013 y posteriores  <br/> |
|18   <br/> |Conectividad perimetral AV Exchange de mensajes unificados (correo de voz)  <br/> |Disponible en Lync Server 2013 y posteriores  <br/> |
|19  <br/> |Llamada de punto a punto RTC  <br/> |Disponible en Lync Server 2010 y posteriores  <br/> |
|20  <br/> |Mensajería instantánea XMPP (federación)  <br/> |Disponible en Lync Server 2013 y posteriores  <br/> |
| 21  <br/> |Servidor de interoperabilidad de vídeo  <br/> |Disponible en Skype Empresarial Server 2015 y posteriores  <br/> |
   
## <a name="how-health-rolls-up"></a>Cómo se revierte el estado

En la tabla siguiente se muestran los estados de mantenimiento de los objetos Skype Empresarial Server de supervisión.
  
|**Objeto Management Pack**|**Description**|
|:-----|:-----|
|Skype Empresarial Server Implementación  <br/> |Representa la implementación de Skype Empresarial Server 2019 en la organización.  <br/> |
|Skype Empresarial Server Sitio  <br/> |Representa diferentes ubicaciones geográficas donde se implementan los servicios.  <br/> |
|Skype Empresarial Server Grupo de servidores  <br/> |Un grupo de servidores (dentro de un sitio) que proporciona servicios de comunicaciones, como mensajería instantánea y conferencia, a los usuarios. Aplicable a grupos de servidores front-end, grupos de servidores perimetrales y grupos de directores, incluso si solo hay una sola máquina en un grupo determinado.  <br/> |
|Skype Empresarial Server Rol  <br/> |Un rol de servidor que hospeda Skype Empresarial Server servicio.  <br/> |
|Skype Empresarial Server Servicio  <br/> |Representa una funcionalidad implementada en un equipo específico (por ejemplo, servicio de usuario en fp01.contoso.com).  <br/> |
|Skype Empresarial Server Componente  <br/> |Un componente del servicio (por ejemplo, el componente de descarga de libreta de direcciones forma parte del servicio web).  <br/> |
|Skype Empresarial Server Pool Watcher  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo.  <br/> |
|Skype Empresarial Server Registrador  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo de registradores.  <br/> |
|Skype Empresarial Server User Services Pool Watcher  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo de servicios de usuario.  <br/> |
|Skype Empresarial Server Watcher de grupo de voz  <br/> |Una instancia de transacciones sintéticas que se ejecutan en un grupo de servidores de voz.  <br/> |
|Skype Empresarial Server Port Watcher  <br/> |Instancia de comprobaciones de puerto que se ejecutan en un grupo de servidores.  <br/> |
|Simple URL Watcher  <br/> |Realiza el sondeo HTTPS de las direcciones URL sencillas configuradas en una implementación.  <br/> |
   
![Paquete acumulativo de SCOM](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Un grupo Skype Empresarial Server puede contener varios sistemas de Skype Empresarial Server individuales (con más de un rol Skype Empresarial Server, Skype Empresarial Server servicio y Skype Empresarial Server componente). Por lo tanto, el error de un servidor o componente individual es menos crítico para el estado general del grupo de servidores de Skype Empresarial Server, ya que otros servidores del mismo grupo pueden proporcionar el servicio de aplicación al cliente. El estado se revertirá en un nivel porcentual al Skype Empresarial Server grupo de servidores. 
  
El Skype Empresarial Server grupo de servidores realiza transacciones sintéticas en un grupo Skype Empresarial Server grupo de servidores. El error consecutivo de una o más transacciones sintéticas (un proceso conocido como intervalo de sondeo consecutivo) subirá el estado de estado crítico al nivel de grupo (peor de cualquier transacción sintética), como se muestra en el siguiente diagrama. 
  
![Sondeo consecutivo de paquete acumulativo de SCOM](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Procedimiento recomendado: Crear un módulo de administración para personalizaciones

De forma predeterminada, Operations Manager guarda todas las personalizaciones, como las invalidaciones en el Módulo de administración predeterminado. Como práctica recomendada, debe crear un módulo de administración independiente para cada módulo de administración sellado que desee personalizar. 
  
Al crear un módulo de administración para almacenar configuraciones personalizadas para un módulo de administración sellado, se recomienda asignar un nombre adecuado al nuevo módulo de administración, como "Skype Empresarial Server 2019 Customizations".
  
La creación de un nuevo módulo de administración para almacenar personalizaciones de cada módulo de administración sellado facilita la exportación de las personalizaciones de un entorno de prueba a un entorno de producción. Esto también facilita la eliminación de un módulo de administración, ya que debe eliminar las dependencias antes de poder eliminar un módulo de administración. Si las personalizaciones de todos los módulos de administración se guardan en el Módulo de administración predeterminado y necesita eliminar un único módulo de administración, primero debe eliminar el Módulo de administración predeterminado, que también elimina las personalizaciones de otros módulos de administración. 
  
## <a name="links"></a>Vínculos

Los vínculos siguientes le conectan a información sobre tareas comunes asociadas con System Center de supervisión de 2012:
  
- [Ciclo de vida del módulo de administración](/previous-versions/system-center/system-center-2012-R2/hh212732(v=sc.12))
    
- [Cómo importar un módulo de administración en Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh212691(v=sc.12))
    
- [Cómo invalidar una regla o un monitor](/previous-versions/system-center/system-center-2012-R2/hh212869(v=sc.12))
    
- [Cómo crear una cuenta de ejecución en Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh321655(v=sc.12))
    
- [Administración de cuentas y perfiles de ejecución](/previous-versions/system-center/system-center-2012-R2/hh212714(v=sc.12))
    
- [Cómo exportar un módulo de administración de Operations Manager](/previous-versions/system-center/system-center-2012-R2/hh320149(v=sc.12))
    
- [Cómo quitar un módulo de administración de Operations Manager](/previous-versions/system-center/system-center-2012-R2/hh230746(v=sc.12))
    
Los vínculos siguientes le conectan a información sobre tareas comunes asociadas con System Center de supervisión de 2007:
  
- [Administrar el ciclo de vida del módulo de administración](/previous-versions/system-center/operations-manager-2007-r2/cc974486(v=technet.10))
    
- [Cómo importar un módulo de administración en Operations Manager 2007](/previous-versions/system-center/operations-manager-2007-r2/cc974494(v=technet.10))
    
- [Cómo supervisar el uso de invalidaciones](/previous-versions/system-center/operations-manager-2007-r2/bb309719(v=technet.10))
    
- [Cómo crear una cuenta de ejecución en Operations Manager 2007](/previous-versions/system-center/operations-manager-2007-r2/bb309445(v=technet.10))
    
- [Cómo modificar un perfil de ejecución existente](/previous-versions/system-center/operations-manager-2007-r2/dd891202(v=technet.10))
    
- [Cómo exportar personalizaciones del módulo de administración](/previous-versions/system-center/operations-manager-2007-r2/cc974487(v=technet.10))
    
- [Cómo quitar un módulo de administración](/previous-versions/system-center/operations-manager-2007-r2/cc974489(v=technet.10))
    
Para obtener preguntas sobre Operations Manager y los paquetes de supervisión, consulte el foro de System Center de la comunidad [de Operations Manager](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Un recurso útil es el [blog System Center Operations Manager Unleashed,](https://opsmgrunleashed.wordpress.com/) que contiene entradas "Por ejemplo" para paquetes de supervisión específicos.
  
Para obtener información adicional acerca de Operations Manager, consulte los blogs siguientes: 
  
- [Blog del equipo de Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog de OpsMgr de Kevin Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Ideas sobre OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog de Rafael Burri](https://rburri.wordpress.com/)
    
- [Espacio de administración de BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Toda la información y el contenido de los sitios que no sean propiedad de Microsoft han sido proporcionados por el propietario o los usuarios del sitio web. Microsoft no ofrece garantías, expresas, implícitas o estatutarias, en cuanto a la información de este sitio web. 
  
## <a name="see-also"></a>Consulte también

[Skype Empresarial Server de administración de 2019](../management-tools-2019.md)