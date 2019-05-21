---
title: Administrar Skype Empresarial Server 2015 con el módulo de administración SCOM
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: 'Resumen: Aprenda a configurar la infraestructura de Skype empresarial Server 2015 para que funcione con System Center Operations Manager.'
ms.openlocfilehash: 3f8f8d188beee3a67a2b4d7cc6308c60410cbf9a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277653"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Administrar Skype Empresarial Server 2015 con el módulo de administración SCOM
 
**Resumen:** Aprenda a configurar la infraestructura de Skype empresarial Server 2015 para que funcione con System Center Operations Manager.
  
En un mundo ideal, nunca encontrará problemas con Skype empresarial Server 2015. Sin embargo, Skype empresarial Server puede verse afectado por factores externos, por ejemplo, bloqueos de red y errores de hardware. Con los paquetes de administración de Skype empresarial Server 2015, puede identificar y resolver los problemas potenciales de forma proactiva. De esta manera, los paquetes de administración de Skype empresarial Server 2015 extienden las capacidades de System Center Operations Manager.
  
Esta información se escribió según la versión 9319,0 del paquete de supervisión del software de comunicaciones de Skype empresarial Server 2015.
  
## <a name="configuration-overview"></a>Descripción de la configuración

 Para configurar la infraestructura de Skype empresarial Server 2015 para que funcione con System Center Operations Manager, debe realizar tres acciones:
  
Identifique y [Configure el servidor de administración principal](configure-the-primary.md). Para ello, debe instalar System Center Operations Manager 2012 SP1 o R2. 
  
 Identifique y [Configure los equipos servidor de Skype empresarial que se van a supervisar](configure-computers-to-monitor.md). Para supervisar un equipo servidor de Skype empresarial mediante System Center Operations Manager, debe instalar los archivos del agente System Center Operations Manager y configurar cada servidor para que actúe como proxy. 
  
 Identifique e [Instale y configure nodos de monitor](watcher-nodes.md). Los nodos de monitor son equipos que ejecutan periódicamente transacciones sintéticas de Skype empresarial Server: cmdlets de Windows PowerShell que comprueban los componentes clave de Skype empresarial Server, como la posibilidad de iniciar sesión en el sistema o de intercambiar instantáneamente. los mensajes funcionan de la forma esperada. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Compatibilidad con el servidor de administración raíz de System Center Operations Manager y el agente

Los paquetes de administración se pueden usar con System Center Operations Manager 2007 R2 (64 bits) (se admite solo para migración) o System Center Operations Manager &amp; 2012 SP1 R2 (64-bit) o System Center operations Manager 2016 (64 bits). En la tabla siguiente se muestran las configuraciones admitidas para los módulos de administración de Skype empresarial Server 2015: 
  
|**Configuración**|**Posible?**|
|:-----|:-----|
|Sistema operativo Windows Server 2008 R2  <br/> Sistema operativo Windows Server 2012 R2  <br/> |Sí. Tanto en el servidor de Skype empresarial Server 2015 como en los nodos de monitor de transacciones sintéticos.  <br/> |
|Servidores agrupados en clúster  <br/> |No admitido.  <br/> |
|Supervisión sin agente  <br/> |No admitido.  <br/> |
|Entorno virtual  <br/> |Sí.  <br/> |
|Roles de servidor unidos al dominio  <br/> |Todos los roles de servidor de Skype empresarial Server 2015 internos deben unirse al dominio.  <br/> |
|Roles de servidor independientes  <br/> |No es necesario que los servidores perimetrales de Skype empresarial Server 2015 estén Unidos al dominio.  <br/> |
|Limitaciones de la topología  <br/> |Todos los roles de servidor de una implementación se deben controlar desde el mismo grupo de administración de Operations Manager.  <br/> |
|Nodo de monitor de transacciones sintéticas  <br/> |Se admite disponibilidad de escenario de supervisión con un nodo de monitor de transacciones sintéticas (configuración adicional necesaria). No es necesario que los nodos de monitor estén unidos al dominio.  <br/> |
   
La siguiente tabla muestra la capacidad y los requisitos del sistema operativo para un nodo de monitor de transacción sintética:
  
|**Componente de hardware**|**Requisito mínimo**|
|:-----|:-----|
|CPU  <br/> |Uno de los siguientes:  <br/> Procesador de 64 bits, cuatro núcleos, 2,33 GHz o superior  <br/> Procesador de 64 bits, dos canales, doble núcleo, 2,33 GHz o superior  <br/> |
|Memoria  <br/> |8 GB  <br/> |
|Sistema operativo  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Red  <br/> |1 adaptador de red de 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>Requisitos previos

Para ejecutar un nodo de monitor de transacción sintética, en primer lugar debe instalar lo siguiente:
  
- Agente de System Center Operations Manager 
    
-  Microsoft .NET Framework 4.5
    
- Archivos de instalación principales de Skype empresarial Server (OcsCore. msi) y la API administrada de comunicaciones unificadas (UCMA) (las versiones deben coincidir con la versión de Skype empresarial Server WatcherNode. msi)
    
## <a name="files-in-this-monitoring-pack"></a>Archivos de este módulo de monitor

El paquete de supervisión para Skype empresarial Server 2015 incluye los siguientes archivos:
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Novedades

Las siguientes características son nuevas en los paquetes de administración de Skype empresarial Server 2015.
  
- **Detección automática para el inicio de sesión en el cliente** Las aplicaciones cliente que inician sesión en Skype empresarial Server 2015 a menudo detectan automáticamente el servidor para iniciar sesión en. Las transacciones sintéticas ahora son compatibles con la función para comprobar si la detección automática se ha configurado correctamente.
    
- **Intervalos de ejecución de la transacción sintética personalizada** Para simplificar el proceso de configuración de los nodos de monitor, las transacciones sintéticas pueden compartir cuentas de usuario. Esto reduce la frecuencia con la que se ejecutan las pruebas en serie para evitar conflictos. De forma predeterminada, las transacciones sintéticas se ejecutan cada 15 minutos para garantizar que todas las pruebas dispongan de tiempo para ejecutarse. Los administradores que elijan usar más usuarios o menos pruebas también pueden reducir el intervalo de ejecución.
    
- **Transacción sintética de servicios** de interoperabilidad de vídeo Los clientes que migren a Skype empresarial Server 2015 de otras soluciones de proveedores, a menudo desean continuar usando los dispositivos de teleconferencia de vídeo (VTCs) de estos otros proveedores. El servidor de interoperabilidad de vídeo es un nuevo rol de servidor de Skype empresarial Server 2015 que permite a los clientes seguir usando Cisco VTCs en sus salas de conferencia conectándose a Cisco CUCM a través de un tronco de video SIP. Esta característica también agrega una transacción sintética para ayudar a comprobar que el Servidor de interoperabilidad de vídeo está activo y puede administrar las conexiones entrantes a través de un tronco SIP de vídeo.
    
- **Transacción sintética de conferencia de uso compartido de aplicaciones** Ya se admite validación de un escenario de un extremo a otro para las conferencias de uso compartido de aplicaciones.
    
## <a name="monitoring-scenarios"></a>Escenarios de supervisión

El paquete de administración de Skype empresarial Server 2015 aprovecha una variedad de características para ayudarle a detectar y diagnosticar problemas. Estas características proporcionan una visibilidad en tiempo real del estado de un entorno de Skype empresarial Server 2015.
  
|**Supervisión escenario**|**Descripción**|
|:-----|:-----|
|Transacciones sintéticas  <br/> | Cmdlets de Windows PowerShell para probar y ayudar a garantizar una alta disponibilidad de escenarios como el inicio de sesión, la presencia, la mensajería instantánea y las conferencias para los usuarios. <br/> Las transacciones sintéticas se pueden ejecutar desde cualquier ubicación geográfica, incluso desde la empresa, desde fuera de ésta y desde las sucursales.  <br/> Cuando se producen errores en una transacción sintética, se crean registros HTML para ayudar a determinar la naturaleza exacta del error. Esto incluye comprender qué acción ha dado lugar al error, la latencia de cada acción, la línea de comandos usada para ejecutar la prueba y el error específico que se han producido.  <br/> |
|Alertas de confiabilidad de llamadas  <br/> |Los registros de detalles de llamadas (CDRs) escritos por los servidores de Skype empresarial Server 2015 reflejan si los usuarios pueden conectarse a una llamada o por qué se termina una llamada. Las alertas de confiabilidad de las llamadas consultan la base de datos de CDR para generar alertas que indican si hay un número elevado de usuarios con problemas de conectividad con las llamadas punto a punto o con la funcionalidad de conferencia básica.  <br/> El escenario abarca llamadas de audio, mensajería instantánea (MI) de punto a punto y otras características de conferencia.  <br/> |
|Alertas de calidad de medios  <br/> |Consultas de base de datos que tienen los informes de calidad de la experiencia (QoE) publicados por los clientes de Skype empresarial Server 2015 al final de cada llamada. Estas consultas generan alertas que indican escenarios en los que es más probable que los usuarios experimenten la calidad de los medios comprometidos durante las llamadas y las conferencias. Los datos se basan en métricas clave, como la latencia y la pérdida de paquetes, que contribuyen directamente a la calidad de la experiencia del usuario.  <br/> |
|Alertas de estado de componente  <br/> |Los componentes de servidor generan alertas a través de registros de eventos y contadores de para indicar condiciones de error que pueden afectar significativamente escenarios de usuario. Estas alertas indican distintas condiciones, como servicios que no se ejecutan, porcentaje elevado de errores, latencia de mensajes elevada o problemas de conectividad.  <br/> |
|Seguimiento de estado de dependencia  <br/> |Skype empresarial Server puede fallar por una gran variedad de motivos. El módulo de administración supervisa y recopila datos para dependencias externas críticas que pueden indicar problemas graves. Estas dependencias incluyen la disponibilidad de Internet Information Services (IIS) y la CPU de los servidores usados para Skype empresarial Server.  <br/> |
   
### <a name="alert-prioritization"></a>Prioridad de las alertas

Las alertas se clasifican en las siguientes categorías: 
  
 **Alertas de prioridad alta:** Estas alertas indican condiciones que provocan interrupciones de servicio para grupos grandes de usuarios y requieren una acción inmediata. Las interrupciones detectadas por transacciones sintéticas y servicios sin conexión (como las videoconferencias de audio/vídeo de Skype empresarial Server) se califican como alertas de alta prioridad. Por el contrario, un error de componente en un solo equipo no es una alerta de alta prioridad. Skype empresarial Server 2015 tiene características integradas de alta disponibilidad para estas situaciones, por ejemplo, varios servidores front-end detrás de equilibradores de carga.
  
 **Alertas de prioridad media:** Estas alertas indican las condiciones que afectan a un subconjunto de usuarios o indican problemas en la calidad de las llamadas, por ejemplo, errores de componentes, latencia en el establecimiento de la llamada o menor calidad de audio en las llamadas. Las alertas de esta categoría tienen estado (es decir, la naturaleza de la alerta cambia según el estado de la conexión de red). Por ejemplo, si las horas de establecimiento de la llamada indican latencia pero después vuelven a un umbral normal, esta alerta de prioridad media se resolverá automáticamente en System Center Operations Manager y los administradores no necesitarán tomar medidas. Las alertas que no se pueden resolver automáticamente generalmente los administradores las resuelven el mismo día laborable.
  
 **Otras alertas:** estas alertas se generan desde componentes que podrían afectar a un usuario o a un subconjunto de usuarios determinado. Por ejemplo, una alerta típica sería que el servicio de libreta de direcciones no analiza la entrada de Servicios de dominio de Active Directory® (AD DS) para el usuario: testuser@contoso.com. Los administradores pueden corregir estas alertas siempre que tengan tiempo disponible.
  
### <a name="synthetic-transactions"></a>Transacciones sintéticas

Los paquetes de administración de Skype empresarial Server 2015 proporcionan una mayor cobertura para las alertas a través de transacciones sintéticas. Las transacciones sintéticas son cmdlets de Windows PowerShell integrados en el módulo de administración de Operations Manager para probar escenarios de usuario de principio a fin. Al designar un servidor para que ejecute transacciones sintéticas, estos cmdlets se desencadenan periódicamente por el módulo de administración. Los errores resultantes de una transacción sintética generan una alerta de estado. Estas son las transacciones sintéticas compatibles con Skype empresarial Server 2015:
  
**Transacciones sintéticas compatibles para registro, presencia y contactos**

||||
|:-----|:-----|:-----|
|1  <br/> |Registro (inicio de sesión del usuario)  <br/> |Lync Server 2010 y posterior disponible  <br/> |
|2  <br/> |Servicio de libreta de direcciones (descarga de archivos)  <br/> |Lync Server 2010 y posterior disponible  <br/> |
|3  <br/> |Consulta web de la libreta de direcciones  <br/> |Lync Server 2010 y posterior disponible  <br/> |
|4  <br/> |Presence  <br/> |Lync Server 2010 y posterior disponible  <br/> |
|5  <br/> |Almacenamiento de contactos unificado  <br/> |Lync Server 2013 y posterior disponible  <br/> |
   
**Transacciones sintéticas compatibles para servicios punto a punto**

||||
|:-----|:-----|:-----|
|6  <br/> |Mensajes instantáneos de punto a punto  <br/> |Disponible en Lync Server 2010 y versiones posteriores  <br/> |
|7  <br/> |Audio y vídeo punto a punto  <br/> |Disponible en Lync Server 2010 y versiones posteriores  <br/> |
|4,8  <br/> |Mensajería instantánea punto a punto MCX (móvil)  <br/> |Disponible en la versión de septiembre de 2011 de Lync Server 2010 a Skype empresarial 2015  <br/> |
 
> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea, la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.
  
**Transacciones sintéticas compatibles para conferencias y chat persistente**

||||
|:-----|:-----|:-----|
|99,999  <br/> |Conferencias de audio y vídeo  <br/> |Disponible en Lync Server 2010 y versiones posteriores  <br/> |
|base10  <br/> |Conferencias de datos  <br/> |Disponible en Lync Server 2013 y versiones posteriores  <br/> |
|once  <br/> |Conferencia de mensajes instantáneos  <br/> |Disponible en Lync Server 2010 y versiones posteriores  <br/> |
|2007  <br/> | Chat persistente <br/> |Disponible en Lync Server 2013 y versiones posteriores  <br/> |
|13  <br/> |Iniciador de participación en reuniones (reuniones programadas)  <br/> |Disponible en Lync Server 2013 y versiones posteriores  <br/> |
|14  <br/> |Conferencia de acceso telefónico  <br/> |Novedades de Skype empresarial Server 2015  <br/> |
|4,5  <br/> |Conferencia de uso compartido de aplicaciones  <br/> |Novedades de Skype empresarial Server 2015  <br/> |
|apartado  <br/> |Conferencia USWA (participación en reunión web)  <br/> |Novedades de Skype empresarial Server 2015  <br/> |
   
**Transacciones sintéticas compatibles para dependencias de asociado y red**

||||
|:-----|:-----|:-----|
|apartado  <br/> |Conectividad del servidor perimetral de A/V  <br/> |Disponible en Lync Server 2013 y versiones posteriores  <br/> |
|18  <br/> |Conectividad de mensajería unificada de Exchange de conectividad de servidor perimetral AV (correo de voz)  <br/> |Disponible en Lync Server 2013 y versiones posteriores  <br/> |
|19  <br/> |Llamada punto a punto de RTC  <br/> |Disponible en Lync Server 2010 y versiones posteriores  <br/> |
|veinte  <br/> |Mensajería instantánea XMPP (federación)  <br/> |Disponible en Lync Server 2013 y Skype empresarial 2015  <br/> |
|21Vianet  <br/> |Servidor de interoperabilidad de vídeo  <br/> |Novedades de Skype empresarial Server 2015  <br/> |
   
## <a name="how-health-rolls-up"></a>Resumen del estado

En la siguiente tabla se muestran los Estados de mantenimiento de los objetos del paquete de supervisión de Skype empresarial Server.
  
|**Objeto de módulo de administración**|**Descripción**|
|:-----|:-----|
|Implementación de Skype empresarial Server  <br/> |Representa la implementación de Skype empresarial Server 2015 en la organización.  <br/> |
|Sitio de Skype empresarial Server  <br/> |Representa distintas ubicaciones geográficas donde se han implementado los servicios.  <br/> |
|Grupo de servidores de Skype empresarial  <br/> |Grupo de servidores (dentro de un sitio) que proporciona servicios de comunicaciones, como la mensajería instantánea y las conferencias, a los usuarios. Es aplicable a grupos de servidores front-end, grupos de servidores perimetrales y grupos de directores, incluso si solo hay una sola máquina de un determinado grupo.  <br/> |
|Rol de servidor de Skype empresarial  <br/> |Un rol de servidor que hospede el servicio de Skype empresarial Server.  <br/> |
|Servicio de Skype empresarial Server  <br/> |Representa una función implementada en un equipo específico (por ejemplo, servicio de usuario en fp0.contoso.com).  <br/> |
|Componente de Skype empresarial Server  <br/> |Componente del servicio (por ejemplo, el componente de descarga de la libreta de direcciones es una parte del servicio web).  <br/> |
|Monitor de grupo de Skype empresarial Server  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo.  <br/> |
|Monitor de registrador de Skype empresarial Server  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo de registradores.  <br/> |
|Monitor de grupo de servicios de usuario de Skype empresarial Server  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo de servicios de usuario.  <br/> |
|Monitor de grupo de voz de Skype empresarial Server  <br/> |Instancia de transacciones sintéticas que se ejecutan en un solo grupo de voz.  <br/> |
|Monitor de puerto de Skype empresarial Server  <br/> |Instancia de comprobaciones de puerto que se ejecuta en un grupo.  <br/> |
|Monitor de URL simple  <br/> |Realiza el sondeo HTTPS de las direcciones URL simples configuradas en una implementación.  <br/> |
   
![Resumen SCOM](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Un grupo de servidores de Skype empresarial puede contener varios sistemas individuales de Skype empresarial Server (con más de un rol de servidor de Skype empresarial, un servicio de Skype empresarial Server y un componente de Skype empresarial Server). Por lo tanto, el error de un servidor o componente individual es menos crítico para el estado general del grupo de servidores de Skype empresarial, porque otros servidores del mismo grupo pueden proporcionar el servicio de aplicación al cliente. El estado se acumulará en un nivel porcentual para el grupo de servidores de Skype empresarial. 
  
El monitor de grupo de Skype empresarial Server realiza transacciones sintéticas en un grupo de servidores de Skype empresarial. Los errores consecutivos en una o más transacciones sintéticas (proceso conocido como intervalo de sondeo consecutivos) resumirán el mantenimiento en el nivel del grupo (el peor de cualquier transacción sintética), tal y como se muestra en el siguiente diagrama. 
  
![Sondeo consecutivo de resumen SCOM](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Práctica recomendada: Crear un módulo de administración para personalizaciones

De forma predeterminada, Operations Manager guarda todas las personalizaciones, como las invalidaciones del módulo de administración predeterminado. Como práctica recomendada, debe crear un módulo de administración independiente para cada módulo de administración sellado que desee personalizar. 
  
Cuando se crea un módulo de administración de para almacenar configuraciones personalizadas para un módulo de administración sellado, se recomienda asignar un nombre adecuado para el nuevo módulo de administración, como "Personalizaciones de Skype Empresarial Server 2015". 
  
La creación de un nuevo módulo de administración para almacenar las personalizaciones de cada módulo de administración sellado facilita la exportación de las personalizaciones de un entorno de prueba a un entorno de producción. Esto también hace que sea más fácil eliminar un módulo de administración, porque antes de eliminarlo deben eliminarse todas sus dependencias. Si las personalizaciones para todos los paquetes de administración se guardan en el módulo de administración predeterminado y es necesario eliminar un único módulo de administración, en primer lugar se debe eliminar el módulo de administración predeterminado, que elimina también las personalizaciones realizadas en otros módulos de administración. 
  
## <a name="links"></a>Vínculos

Los siguientes vínculos permiten obtener acceso a información sobre tareas comunes asociadas con los módulos de supervisión de System Center 2012:
  
- [Ciclo de vida del paquete de administración](https://technet.microsoft.com/en-us/library/hh212732.aspx)
    
- [Cómo importar un paquete de administración en Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212691.aspx)
    
- [Cómo invalidar una regla o un monitor](https://technet.microsoft.com/en-us/library/hh212869.aspx)
    
- [Cómo crear una cuenta de ejecución en Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh321655.aspx)
    
- [Administrar cuentas y perfiles de ejecución](https://technet.microsoft.com/en-us/library/hh212714.aspx)
    
- [Cómo exportar un módulo de administración de Operations Manager](https://technet.microsoft.com/en-us/library/hh320149.aspx)
    
- [Cómo quitar un módulo de administración de Operations Manager](https://technet.microsoft.com/en-us/library/hh230746.aspx)
    
Los siguientes vínculos permiten obtener acceso a información sobre tareas comunes asociadas con los módulos de supervisión de System Center 2007:
  
- [Administrar el ciclo de vida de un paquete de administración](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Cómo importar un paquete de administración en Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Cómo supervisar el uso de reemplazos](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Cómo crear una cuenta de ejecución en Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Cómo modificar un perfil de ejecución existente](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Cómo exportar las personalizaciones de los paquetes de administración](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Cómo quitar un módulo de administración](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Para obtener más información sobre Operations Manager y los paquetes de supervisión, consulte el foro de la [comunidad de System Center Operations Manager](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Un recurso útil es el blog de [System Center Operations Manager](https://opsmgrunleashed.wordpress.com/) , que contiene las entradas "por ejemplo" para paquetes de supervisión específicos.
  
Para obtener información adicional acerca de Operations Manager, consulte los blogs siguientes: 
  
- [Blog del equipo de Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog de OpsMgr de Kevin Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Ideas en OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog de Raphael zumbidos](https://rburri.wordpress.com/)
    
- [Espacio de administración de BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [OPS Mgr + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Toda la información y contenido de sitios que no sean de Microsoft la proporciona el propietario o los usuarios del sitio web correspondiente. Microsoft no ofrece ninguna garantía, explícita, implícita o legal, con respecto a la información de dichos sitios web. 
  
## <a name="see-also"></a>Vea también

[Herramientas de administración de Skype empresarial Server 2015](../../management-tools/management-tools.md)
