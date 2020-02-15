---
title: Administrar Skype empresarial Server 2015 con el módulo de administración de SCOM
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
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: 'Resumen: Obtenga información sobre cómo configurar la infraestructura de Skype empresarial Server 2015 para que funcione con System Center Operations Manager.'
ms.openlocfilehash: 06297ba7e0ab70e7046fc2f3db189275cc90f9d4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005945"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Administrar Skype empresarial Server 2015 con el módulo de administración de SCOM
 
**Resumen:** Obtenga información sobre cómo configurar la infraestructura de Skype empresarial Server 2015 para que funcione con System Center Operations Manager.
  
En un mundo ideal, nunca se encuentran problemas con Skype empresarial Server 2015. Sin embargo, Skype empresarial Server puede verse afectado por factores externos, por ejemplo, bloqueos de red y errores de hardware. Mediante el uso de los paquetes de administración de Skype empresarial Server 2015, puede identificar y solucionar posibles problemas de forma proactiva. De esta forma, los paquetes de administración de Skype empresarial Server 2015 amplían las capacidades de System Center Operations Manager.
  
Esta información se escribió en función de la versión 9319,0 del paquete de supervisión para el software de comunicaciones de Skype empresarial Server 2015.
  
## <a name="configuration-overview"></a>Descripción general de la configuración

 Para configurar la infraestructura de Skype empresarial Server 2015 para que funcione con System Center Operations Manager, debe hacer tres cosas:
  
Identifique y [Configure el servidor de administración principal](configure-the-primary.md). Para ello, debe instalar System Center Operations Manager 2012 SP1 o R2. 
  
 Identificar y [configurar los equipos de Skype empresarial Server que se supervisarán](configure-computers-to-monitor.md). Para supervisar un equipo de Skype empresarial Server mediante System Center Operations Manager, debe instalar los archivos del agente de System Center Operations Manager y configurar cada servidor para que actúe como proxy. 
  
 Identificar e [instalar y configurar nodos de monitor](watcher-nodes.md). Los nodos de monitor son equipos que ejecutan periódicamente transacciones sintéticas de Skype empresarial Server: cmdlets de Windows PowerShell que comprueban que los componentes clave de Skype empresarial Server, como la capacidad de iniciar sesión en el sistema o la capacidad de intercambiar instantáneamente los mensajes, funcionan según lo esperado. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Soporte de agente y servidor de administración raíz de System Center Operations Manager

Los paquetes de administración se pueden usar con System Center Operations Manager 2007 R2 (64 bits) (compatible solo con fines de migración) o System Center Operations &amp; Manager 2012 SP1 R2 (64-bit) o System Center operations Manager 2016 (64 bits). En la siguiente tabla se muestran las configuraciones admitidas para los módulos de administración de Skype empresarial Server 2015: 
  
|Configuración|¿Se admite?|
|:-----|:-----|
|Sistema operativo Windows Server 2008 R2  <br/> Sistema operativo Windows Server 2012 R2  <br/> |Sí. Tanto en el servidor de Skype empresarial Server 2015 como en los nodos de monitor de transacciones sintéticas.  <br/> |
|Servidores agrupados  <br/> |No admitida.  <br/> |
|Supervisión sin agente  <br/> |No admitida.  <br/> |
|Entorno virtual  <br/> |Sí.  <br/> |
|Roles de servidor Unidos a un dominio  <br/> |Todos los roles de servidor de Skype empresarial Server 2015 internos deben estar Unidos al dominio.  <br/> |
|Roles de servidor independientes  <br/> |No es necesario que los servidores perimetrales de Skype empresarial Server 2015 estén Unidos a un dominio.  <br/> |
|Limitaciones de la topología  <br/> |Todos los roles de servidor de una implementación deben supervisarse desde el mismo grupo de administración de Operations Manager.  <br/> |
|Nodo de monitor de transacciones sintéticas  <br/> |Se admite la disponibilidad de escenario de supervisión con un nodo de monitor de transacciones sintéticas (configuración adicional necesaria). No es necesario que los nodos de monitor estén Unidos a un dominio.  <br/> |
   
En la siguiente tabla se muestran la capacidad y los requisitos del sistema operativo para un nodo de monitor de transacciones sintéticas:
  
|Componente de hardware|Requisito mínimo|
|:-----|:-----|
|CPU  <br/> |Uno de los siguientes:  <br/> procesador de 64 bits, Quad-Core, 2,33 GHz o superior  <br/> procesador de 2 vías de 64 bits, doble núcleo, 2,33 GHz o superior  <br/> |
|Memoria  <br/> |8 GB  <br/> |
|Sistema operativo  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Red  <br/> |1 adaptador de red de 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>Requisitos previos

Para ejecutar un nodo de monitor de transacciones sintéticas, primero debe instalar lo siguiente:
  
- Agente de System Center Operations Manager 
    
-  Microsoft .NET Framework 4.5
    
- Los archivos de instalación básicos de Skype empresarial Server (OcsCore. msi) y la API administrada de comunicaciones unificadas (UCMA) (las versiones deben coincidir con la versión de Skype empresarial Server WatcherNode. msi)
    
## <a name="files-in-this-monitoring-pack"></a>Archivos de este módulo de supervisión

El paquete de supervisión de Skype empresarial Server 2015 incluye los siguientes archivos:
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode. msi
    
## <a name="whats-new"></a>Novedades

Las siguientes características son nuevas en los paquetes de administración de Skype empresarial Server 2015.

- **Cambios en la [actualización de septiembre de 2019](https://www.microsoft.com/en-in/download/details.aspx?id=47364) ** Algunas alertas han quitado caracteres especiales. En algunos casos, los caracteres especiales interfieren con la función de notificación de canal de comando SCOM.

- **Detección automática para el inicio de sesión de cliente** Las aplicaciones cliente que inician sesión en Skype empresarial Server 2015 a menudo detectan automáticamente el servidor en el que iniciar sesión. Las transacciones sintéticas ahora admiten la comprobación de que la detección automática está correctamente configurada.
    
- **Intervalos personalizados de ejecución de transacciones sintéticas** Para simplificar el proceso de configuración de los nodos de monitor, las transacciones sintéticas pueden compartir cuentas de usuario. Esto ralentiza la frecuencia con la que se ejecutan las pruebas, ya que las pruebas se serializan para evitar conflictos. De forma predeterminada, las transacciones sintéticas se ejecutan cada 15 minutos para asegurarse de que todas las pruebas tienen tiempo para ejecutarse. Los administradores que optan por usar más usuarios o menos pruebas por usuario pueden ahora reducir también el intervalo de ejecución.
    
- **Transacción sintética de servicios de interoperabilidad de vídeo** Los clientes que migren a Skype empresarial Server 2015 a partir de otras soluciones de proveedor, a menudo, desean seguir usando los dispositivos de teleconferencia de vídeo (VTC) de estos otros proveedores. El servidor de interoperabilidad de vídeo es un nuevo rol de servidor de Skype empresarial Server 2015 que permite a los clientes seguir usando Cisco VTC en sus salas de conferencias conectándose a Cisco CUCM a través de un tronco SIP de vídeo. Esta característica también agrega una transacción sintética para ayudar a comprobar que el servidor de interoperabilidad de vídeo está activo y puede administrar las conexiones entrantes a través de un tronco SIP de vídeo.
    
- **Transacción sintética de conferencia de uso compartido de aplicaciones** Ahora se admite la validación de escenario de un extremo a otro para las conferencias de uso compartido de aplicaciones.
    
## <a name="monitoring-scenarios"></a>Escenarios de supervisión

El módulo de administración de Skype empresarial Server 2015 aprovecha una variedad de características para ayudarle a detectar y diagnosticar los problemas. Estas características proporcionan una visibilidad en tiempo real del estado de un entorno de Skype empresarial Server 2015.
  
|Escenario de supervisión|Descripción|
|:-----|:-----|
|Transacciones sintéticas  <br/> | Cmdlets de Windows PowerShell para probar y ayudar a garantizar la alta disponibilidad de escenarios como el inicio de sesión, la presencia, la mensajería instantánea y las conferencias para los usuarios. <br/> Las transacciones sintéticas se pueden ejecutar desde cualquier ubicación geográfica, incluso dentro de la empresa, fuera de la empresa y en las sucursales.  <br/> Cuando se produce un error en una transacción sintética, se crean registros HTML para ayudar a determinar la naturaleza exacta del error. Esto incluye comprender qué acción ha fallado, la latencia de cada acción, la línea de comandos usada para ejecutar la prueba y el error específico que se ha producido.  <br/> |
|Alertas de confiabilidad de llamadas  <br/> |Los registros de detalles de llamadas (CDR) escritos por los servidores de Skype empresarial Server 2015 reflejan si los usuarios pueden conectarse a una llamada o por qué una llamada finaliza. Las alertas de confiabilidad de llamadas consultan la base de datos de CDR para generar alertas que indiquen si un gran número de usuarios experimentan problemas de conectividad para las llamadas punto a punto o las funciones de conferencia básicas.  <br/> La cobertura de escenario incluye llamadas de audio, mensajería instantánea de punto a punto (mi) y otras características de conferencia.  <br/> |
|Alertas de calidad de medios  <br/> |Consultas de base de datos que examinan los informes de calidad de la experiencia (QoE) publicados por los clientes de Skype empresarial Server 2015 al final de cada llamada. Estas consultas generan alertas que indican los escenarios en los que es más probable que los usuarios experimenten la calidad de los medios comprometidos durante las llamadas y las conferencias. Los datos se basan en métricas clave, como la latencia y la pérdida de paquetes, que contribuyen directamente a la calidad de la experiencia del usuario.  <br/> |
|Alertas de estado de componente  <br/> |Los componentes de servidor individuales generan alertas a través de registros de eventos y contadores de rendimiento para indicar condiciones de error que pueden afectar significativamente a los escenarios de usuario. Estas alertas indican una variedad de condiciones, como servicios que no se ejecutan, altas tasas de errores, alta latencia de mensajes o problemas de conectividad.  <br/> |
|Supervisión del estado de dependencia  <br/> |Skype empresarial Server puede fallar por varios motivos externos. El módulo de administración supervisa y recopila datos de dependencias externas críticas que pueden indicar problemas graves. Estas dependencias incluyen la disponibilidad de Internet Information Services (IIS) y la CPU de los servidores usados para Skype empresarial Server.  <br/> |
|||
   
### <a name="alert-prioritization"></a>Priorización de alertas

Las alertas se clasifican en las siguientes categorías: 
  
 **Alertas de prioridad alta:** Estas alertas indican condiciones que causan interrupciones en el servicio para grandes grupos de usuarios y requieren una acción inmediata. Las interrupciones detectadas por las transacciones sintéticas y los servicios sin conexión (como las conferencias de audio y vídeo de Skype empresarial Server) se califican como alertas de alta prioridad. Por el contrario, un error de componente en un solo equipo no es una alerta de prioridad alta. Skype empresarial Server 2015 tiene características integradas de alta disponibilidad para estas situaciones; por ejemplo, varios servidores front-end detrás de equilibradores de carga.
  
 **Alertas de prioridad media:** Estas alertas indican las condiciones que afectan a un subconjunto de usuarios o indican problemas en la calidad de las llamadas (por ejemplo, errores de componentes, latencia en el establecimiento de la llamada o menor calidad de audio en las llamadas). Las alertas de esta categoría tienen estado (es decir, la naturaleza de la alerta cambia en función del estado de la conexión de red). Por ejemplo, si las horas de establecimiento de llamadas indican latencia, pero después vuelven a un umbral normal, esta alerta de prioridad media se resolverá automáticamente en System Center Operations Manager y los administradores no necesitarán realizar ninguna acción. Los administradores suelen solucionar los avisos que no se pueden resolver automáticamente en el mismo día hábil.
  
 **Otras alertas:** Estas alertas se generan a partir de componentes que pueden afectar a un usuario específico o a un subconjunto de usuarios. Por ejemplo, una alerta típica sería que el servicio de libreta de direcciones no pudiera analizar la entrada de servicios de dominio® (AD DS) de Active Directory para el usuario: testuser@contoso.com. Los administradores pueden dirigir estas alertas siempre que tengan tiempo disponible.
  
### <a name="synthetic-transactions"></a>Transacciones sintéticas

Los paquetes de administración de Skype empresarial Server 2015 proporcionan una mayor cobertura para las alertas a través de transacciones sintéticas. Las transacciones sintéticas son cmdlets de Windows PowerShell integrados en el módulo de administración de Operations Manager para probar escenarios de usuario de un extremo a otro. Al designar un servidor para ejecutar transacciones sintéticas, el módulo de administración desencadena periódicamente estos cmdlets. Los errores resultantes de una transacción sintética generan una alerta con estado. Estas son las transacciones sintéticas admitidas para Skype empresarial Server 2015:
  


|Transacciones sintéticas admitidas para registro, presencia y contactos|||
|:-----|:-----|:-----|
|1   <br/> |Registro (inicio de sesión de usuario)  <br/> |Lync Server 2010 y posterior disponible  <br/> |
|2   <br/> |Servicio de libreta de direcciones (descarga de archivos)  <br/> |Lync Server 2010 y posterior disponible  <br/> |
|3   <br/> |Consulta web de la libreta de direcciones  <br/> |Lync Server 2010 y posterior disponible  <br/> |
|4   <br/> |Presencia  <br/> |Lync Server 2010 y posterior disponible  <br/> |
|5   <br/> |Almacén de contactos unificado  <br/> |Lync Server 2013 y posterior disponible  <br/> |
||||   

|Transacciones sintéticas compatibles para servicios punto a punto|||
|:-----|:-----|:-----|
|6   <br/> |Mensajería instantánea punto a punto  <br/> |Disponible en Lync Server 2010 y versiones posteriores  <br/> |
|7   <br/> |Vídeo de audio punto a punto  <br/> |Disponible en Lync Server 2010 y versiones posteriores  <br/> |
|8   <br/> |Mensaje instantáneo de punto a punto de MCX (móvil)  <br/> |Disponible en la versión de septiembre de 2011 de Lync Server 2010 a Skype empresarial 2015  <br/> |
 
> [!NOTE]
> La compatibilidad con MCX (Mobility Service) para clientes móviles heredados ya no está disponible en Skype empresarial Server 2019. Todos los clientes móviles actuales de Skype empresarial ya usan la API Web de comunicaciones unificadas (UCWA) para admitir la mensajería instantánea (mi), la presencia y los contactos. Los usuarios con clientes heredados que usen MCX deberán actualizar a un cliente actual.


|Transacciones sintéticas compatibles para conferencias y chat persistente|||
|:-----|:-----|:-----|
|9   <br/> |Conferencias de audio y vídeo  <br/> |Disponible en Lync Server 2010 y versiones posteriores  <br/> |
|10   <br/> |Conferencia de datos  <br/> |Disponible en Lync Server 2013 y versiones posteriores  <br/> |
|12  <br/> |Conferencia de mensajes instantáneos  <br/> |Disponible en Lync Server 2010 y versiones posteriores  <br/> |
|12  <br/> | Chat persistente <br/> |Disponible en Lync Server 2013 y versiones posteriores  <br/> |
|apartado  <br/> |Unirse al iniciador (reuniones programadas)  <br/> |Disponible en Lync Server 2013 y versiones posteriores  <br/> |
|14   <br/> |Conferencia de acceso telefónico local  <br/> |Nuevo en Skype empresarial Server 2015  <br/> |
|15   <br/> |Conferencia de uso compartido de aplicaciones  <br/> |Nuevo en Skype empresarial Server 2015  <br/> |
|16   <br/> |Conferencia de UCWA (Unión a reuniones Web)  <br/> |Nuevo en Skype empresarial Server 2015  <br/> |
||||

|Transacciones sintéticas compatibles para dependencias de red y asociado|||
|:-----|:-----|:-----|
|17   <br/> |Conectividad de servidores perimetrales AUDIOVISUALes  <br/> |Disponible en Lync Server 2013 y versiones posteriores  <br/> |
|18   <br/> |Conectividad perimetral AV conectividad de mensajería unificada de Exchange (correo de voz)  <br/> |Disponible en Lync Server 2013 y versiones posteriores  <br/> |
|18  <br/> |Llamada de punto a punto de RTC  <br/> |Disponible en Lync Server 2010 y versiones posteriores  <br/> |
|20  <br/> |Mensajería instantánea XMPP (Federación)  <br/> |Disponible en Lync Server 2013 y Skype empresarial 2015  <br/> |
|21  <br/> |Servidor de interoperabilidad de vídeo  <br/> |Nuevo en Skype empresarial Server 2015  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>Cómo se acumula el estado

En la siguiente tabla se muestran los Estados de mantenimiento de los objetos del módulo de supervisión de Skype empresarial Server.
  
|Objeto de módulo de administración|Descripción|
|:-----|:-----|
|Implementación de Skype empresarial Server  <br/> |Representa la implementación de Skype empresarial Server 2015 en la organización.  <br/> |
|Sitio de Skype empresarial Server  <br/> |Representa distintas ubicaciones geográficas donde se implementan los servicios.  <br/> |
|Grupo de servidores de Skype empresarial Server  <br/> |Un grupo de servidores (dentro de un sitio) que proporciona servicios de comunicaciones, como la mensajería instantánea y las conferencias, a los usuarios. Aplicable a los grupos de servidores front-end, los grupos de servidores perimetrales y los grupos de directores, incluso si hay un solo equipo en un grupo determinado.  <br/> |
|Rol de servidor de Skype empresarial  <br/> |Un rol de servidor que hospede el servicio de Skype empresarial Server.  <br/> |
|Servicio de Skype empresarial Server  <br/> |Representa una funcionalidad implementada en un equipo específico (por ejemplo, servicio de usuario en fp01.contoso.com).  <br/> |
|Componente de Skype empresarial Server  <br/> |Un componente del servicio (por ejemplo, el componente de descarga de la libreta de direcciones forma parte del servicio Web).  <br/> |
|Monitor de grupo de Skype empresarial Server  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo de servidores.  <br/> |
|Monitor de registro de registrador de Skype empresarial Server  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo de registradores.  <br/> |
|Monitor de grupo de servicios de usuario de Skype empresarial Server  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo de servicios de usuario.  <br/> |
|Monitor de grupo de voz de Skype empresarial Server  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo de voz.  <br/> |
|Monitor de puerto del servidor de Skype empresarial  <br/> |Una instancia de comprobaciones de puerto que se ejecuta en un grupo de servidores.  <br/> |
|Monitor de direcciones URL sencillas  <br/> |Realiza un sondeo HTTPS de las direcciones URL sencillas configuradas en una implementación.  <br/> |
   
![Paquete acumulativo de SCOM](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Un grupo de servidores de Skype empresarial Server puede contener varios sistemas de Skype empresarial Server individuales (con más de una función de servidor de Skype empresarial, servicio de Skype empresarial Server y componente de Skype empresarial Server). Por lo tanto, el error de un servidor o componente individual es menos crítico para el estado general del grupo de Skype empresarial Server, ya que otros servidores del mismo grupo pueden proporcionar el servicio de aplicación al cliente. El estado se resumirá en un nivel porcentual para el grupo de servidores de Skype empresarial. 
  
El monitor de grupo de Skype empresarial Server realiza transacciones sintéticas en un grupo de servidores de Skype empresarial. Un error consecutivo de una o varias transacciones sintéticas (un proceso conocido como el intervalo de sondeo consecutivo) resumirá el estado de mantenimiento crítico en el nivel del grupo (en el peor de las transacciones sintéticas), como se muestra en el siguiente diagrama. 
  
![Sondeo consecutivo de Resumen de SCOM](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Procedimiento recomendado: crear un módulo de administración para las personalizaciones

De forma predeterminada, Operations Manager guarda todas las personalizaciones, como invalidaciones en el módulo de administración predeterminado. Como práctica recomendada, debe crear un módulo de administración independiente para cada módulo de administración sellado que desee personalizar. 
  
Cuando se crea un módulo de administración para almacenar configuraciones personalizadas para un módulo de administración sellado, se recomienda asignar un nombre adecuado al nuevo módulo de administración, como "personalizaciones de Skype empresarial Server 2015". 
  
La creación de un nuevo módulo de administración para almacenar las personalizaciones de cada módulo de administración sellado facilita la exportación de las personalizaciones de un entorno de prueba a un entorno de producción. Esto también hace que sea más fácil eliminar un módulo de administración, ya que debe eliminar todas las dependencias para poder eliminar un módulo de administración. Si se guardan las personalizaciones de todos los módulos de administración en el módulo de administración predeterminado y necesita eliminar un solo módulo de administración, primero debe eliminar el módulo de administración predeterminado, que también elimina las personalizaciones de otros módulos de administración. 
  
## <a name="links"></a>Vínculos

Los siguientes vínculos le conectan a información sobre tareas comunes asociadas con los paquetes de supervisión de System Center 2012:
  
- [Ciclo de vida del paquete de administración](https://technet.microsoft.com/library/hh212732.aspx)
    
- [Cómo importar un paquete de administración en Operations Manager 2012](https://technet.microsoft.com/library/hh212691.aspx)
    
- [Cómo invalidar una regla o un monitor](https://technet.microsoft.com/library/hh212869.aspx)
    
- [Cómo crear una cuenta "ejecutar como" en Operations Manager 2012](https://technet.microsoft.com/library/hh321655.aspx)
    
- [Administración de cuentas y perfiles de ejecución](https://technet.microsoft.com/library/hh212714.aspx)
    
- [Cómo exportar un módulo de administración de Operations Manager](https://technet.microsoft.com/library/hh320149.aspx)
    
- [Cómo quitar un módulo de administración de Operations Manager](https://technet.microsoft.com/library/hh230746.aspx)
    
Los siguientes vínculos le conectan a información sobre tareas comunes asociadas con los paquetes de supervisión de System Center 2007:
  
- [Administración del ciclo de vida de los paquetes de administración](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Cómo importar un paquete de administración en Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Cómo supervisar el uso de reemplazos](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Cómo crear una cuenta "ejecutar como" en Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Cómo modificar un perfil de ejecución existente](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Cómo exportar personalizaciones del paquete de administración](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Cómo quitar un módulo de administración](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Para obtener preguntas sobre Operations Manager y los paquetes de supervisión, consulte el foro de la [comunidad de System Center Operations Manager](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Un recurso útil es el blog de [System Center Operations Manager](https://opsmgrunleashed.wordpress.com/) , que contiene las publicaciones "por ejemplo" para los paquetes de supervisión específicos.
  
Para obtener información adicional acerca de Operations Manager, consulte los siguientes blogs: 
  
- [Blog del equipo de Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog de OpsMgr de Kevin Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Ideas sobre OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog de blog Raphael zumbidos](https://rburri.wordpress.com/)
    
- [Espacio de administración de BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [OPS Mgr + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Toda la información y el contenido de los sitios que no sean propiedad de Microsoft han sido proporcionados por el propietario o los usuarios del sitio web. Microsoft no ofrece ninguna garantía, expresa, implícita o legal, con respecto a la información de este sitio Web. 
  
## <a name="see-also"></a>Vea también

[Herramientas de administración de Skype empresarial Server 2015](../../management-tools/management-tools.md)
