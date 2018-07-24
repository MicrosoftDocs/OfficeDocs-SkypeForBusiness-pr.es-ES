---
title: Administrar Skype Empresarial Server 2015 con el módulo de administración SCOM
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: 'Resumen: Obtenga información sobre cómo configurar su Skype para infraestructura de Business Server 2015 para trabajar con System Center Operations Manager.'
ms.openlocfilehash: b94490c60234f76b0e07f0b7732d76cc2354eaad
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20994965"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Administrar Skype Empresarial Server 2015 con el módulo de administración SCOM
 
**Resumen:** Obtenga información sobre cómo configurar su Skype para infraestructura de Business Server 2015 para trabajar con System Center Operations Manager.
  
En un mundo ideal, nunca encontraría problemas con Skype para Business Server 2015. Sin embargo, Skype para Business Server puede verse afectado por factores externos — por ejemplo, bloqueos y errores de hardware de red. Mediante el uso de Skype para paquetes de administración de Business Server 2015, puede identificar y solucionar posibles problemas de forma proactiva. De este modo, el Skype para paquetes de administración de Business Server 2015 extender las capacidades de System Center Operations Manager.
  
Esta información se escribió basándose en la versión 9319.0 del paquete de supervisión de Skype para el software de comunicaciones empresariales Server 2015.
  
## <a name="configuration-overview"></a>Descripción de la configuración

 Para configurar su Skype para infraestructura de Business Server 2015 para trabajar con System Center Operations Manager, debe seguir estos tres pasos:
  
Identificar y [Configurar el servidor de administración principal](configure-the-primary.md). Para ello, debe instalar System Center Operations Manager 2012 SP1 o R2. 
  
 Identificar y [Configure el Skype para los equipos de servidor empresarial que se van a supervisar](configure-computers-to-monitor.md). Para supervisar un Skype para el equipo servidor empresarial mediante el uso de System Center Operations Manager, debe instalar los archivos del agente System Center Operations Manager y configurar cada servidor para que actúe como un servidor proxy. 
  
 Identificar y [instalar y configurar los nodos de monitor](watcher-nodes.md). Nodos de monitor son equipos que ejecutan periódicamente Skype para las transacciones sintéticas Business Server — cmdlets de Windows PowerShell que comprobar esa clave Skype para los componentes de servidor empresarial, como la capacidad para iniciar sesión en el sistema o la capacidad de instantánea de exchange mensajes, funcionan según lo previsto. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Servidor de administración de System Center Operations Manager raíz y compatibilidad con el agente

Los paquetes de administración se pueden usar con System Center Operations Manager 2007 R2 (64 bits) (versión compatible solo con fines de migración) o System Center Operations Manager 2012 SP1 &amp; R2 (64 bits). La siguiente tabla muestran las configuraciones compatibles para los paquetes de administración de Skype para Business Server 2015: 
  
|**Configuración**|**¿Se admite?**|
|:-----|:-----|
|Sistema operativo Windows Server 2008 R2  <br/> Sistema operativo Windows Server 2012 R2  <br/> |Sí. Ambos en Skype para server Business Server 2015 y nodos de Monitor de transacciones sintéticas.  <br/> |
|Servidores agrupados en clúster  <br/> |No admitido.  <br/> |
|Supervisión sin agente  <br/> |No admitido.  <br/> |
|Entorno virtual  <br/> |Sí.  <br/> |
|Roles de servidor unidos al dominio  <br/> |Todos los Skype interno para funciones de servidor de Business Server 2015 debe estar unido a un dominio.  <br/> |
|Roles de servidor independientes  <br/> |Skype para los servidores perimetrales de Business Server 2015 no tienen que estar unido a un dominio.  <br/> |
|Limitaciones de la topología  <br/> |Todos los roles de servidor de una implementación se deben controlar desde el mismo grupo de administración de Operations Manager.  <br/> |
|Nodo de monitor de transacciones sintéticas  <br/> |Se admite disponibilidad de escenario de supervisión con un nodo de monitor de transacciones sintéticas (configuración adicional necesaria). No es necesario que los nodos de monitor estén unidos al dominio.  <br/> |
   
La siguiente tabla muestra la capacidad y los requisitos del sistema operativo para un nodo de monitor de transacción sintética:
  
|**Componente de hardware**|**Requisito mínimo**|
|:-----|:-----|
|CPU  <br/> |Uno de los siguientes:  <br/> Procesador de 64 bits, cuatro núcleos, 2,33 GHz o superior  <br/> Procesador de 64 bits, dos canales, doble núcleo, 2,33 GHz o superior  <br/> |
|Memoria  <br/> |8 GB  <br/> |
|Sistema operativo  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Red  <br/> |1 adaptador de red de 1 Gbps  <br/> |
   
## <a name="prerequisites"></a>Requisitos previos

Para ejecutar un nodo de monitor de transacción sintética, en primer lugar debe instalar lo siguiente:
  
- Agente de System Center Operations Manager 
    
-  Microsoft .NET Framework 4.5
    
- Skype para archivos de instalación de Business Server core (OcsCore.msi) y la API administrada de comunicaciones unificadas (UCMA) (versiones deben coincidir con el Skype para Business Server WatcherNode.msi versión)
    
## <a name="files-in-this-monitoring-pack"></a>Archivos de este módulo de monitor

El paquete de supervisión de Skype para Business Server 2015 incluye los siguientes archivos:
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Novedades

Las siguientes características son nuevas en Skype para paquetes de administración de Business Server 2015.
  
- **Detección automática para inicio de sesión de los clientes** Las aplicaciones de cliente que inicio de sesión en Skype para Business Server 2015 a menudo automáticamente detección el servidor para iniciar sesión. Las transacciones sintéticas ahora son compatibles con la función para comprobar si la detección automática se ha configurado correctamente.
    
- **Ejecute intervalos de transacciones sintéticas personalizada** Para simplificar el proceso de nodos de Monitor de configuración, las transacciones sintéticas pueden compartir las cuentas de usuario. Esto reduce la frecuencia con la que se ejecutan las pruebas en serie para evitar conflictos. De forma predeterminada, las transacciones sintéticas se ejecutan cada 15 minutos para garantizar que todas las pruebas dispongan de tiempo para ejecutarse. Los administradores que elijan usar más usuarios o menos pruebas también pueden reducir el intervalo de ejecución.
    
- **Transacciones sintéticas de los servicios de interoperabilidad de vídeo** Los clientes que se va a migrar a Skype para Business Server 2015 desde soluciones de otros fabricantes a menudo desean continuar usando los dispositivos de videoconferencias (VTCs) de estos otros proveedores. Servidor de interoperabilidad de vídeo es un nuevo Skype para Business Server 2015 rol de servidor que permite a los clientes seguir usando Cisco VTCs en las salas de conferencias conectándose a Cisco CUCM a través de un tronco SIP vídeo. Esta característica también agrega una transacción sintética para ayudar a comprobar que el Servidor de interoperabilidad de vídeo está activo y puede administrar las conexiones entrantes a través de un tronco SIP de vídeo.
    
- **Transacción sintética de conferencia de uso compartido de aplicaciones** Ya se admite validación de un escenario de un extremo a otro para las conferencias de uso compartido de aplicaciones.
    
## <a name="monitoring-scenarios"></a>Escenarios de supervisión

El Skype para Business Server 2015 Management Pack aprovecha una gran variedad de características que le ayudarán a detectar y diagnosticar problemas. Estas características de proporcionar visibilidad en tiempo real en el estado de un Skype para entorno empresarial Server 2015.
  
|**Supervisión escenario**|**Descripción**|
|:-----|:-----|
|Transacciones sintéticas  <br/> | Cmdlets de Windows PowerShell para probar y ayudar a asegurar una alta disponibilidad de escenarios, como inicio de sesión de presencia, mensajería instantánea y conferencias para los usuarios. <br/> Las transacciones sintéticas se pueden ejecutar desde cualquier ubicación geográfica, incluso desde la empresa, desde fuera de ésta y desde las sucursales.  <br/> Cuando se producen errores en una transacción sintética, se crean registros HTML para ayudar a determinar la naturaleza exacta del error. Esto incluye comprender qué acción ha dado lugar al error, la latencia de cada acción, la línea de comandos usada para ejecutar la prueba y el error específico que se han producido.  <br/> |
|Alertas de confiabilidad de llamadas  <br/> |Registros de detalles de llamadas (CDR) escritas por Skype para servidores de Business Server 2015 reflejar si los usuarios son capaces de conectarse a una llamada o por qué se ha finalizado una llamada. Las alertas de confiabilidad de las llamadas consultan la base de datos de CDR para generar alertas que indican si hay un número elevado de usuarios con problemas de conectividad con las llamadas punto a punto o con la funcionalidad de conferencia básica.  <br/> El escenario abarca llamadas de audio, mensajería instantánea (MI) de punto a punto y otras características de conferencia.  <br/> |
|Alertas de calidad de medios  <br/> |Consultas de base de datos que consultar informes de calidad de la experiencia (QoE) publicados por Skype para clientes empresariales Server 2015 al final de cada llamada. Estas consultas producen alertas que indicar escenarios donde están más probable que la experiencia de calidad de los medios en peligro durante las llamadas y las conferencias a los usuarios. Los datos se basa en métricas claves, como la latencia de paquetes y pérdida de paquetes, que contribuyen directamente a la calidad de la experiencia del usuario.  <br/> |
|Alertas de estado de componente  <br/> |Los componentes de servidor generan alertas a través de registros de eventos y contadores de para indicar condiciones de error que pueden afectar significativamente escenarios de usuario. Estas alertas indican distintas condiciones, como servicios que no se ejecutan, porcentaje elevado de errores, latencia de mensajes elevada o problemas de conectividad.  <br/> |
|Seguimiento de estado de dependencia  <br/> |Skype para Business Server puede producir un error en una variedad de motivos externos. El módulo de administración supervisa y recopila datos para dependencias externas críticas que pueden indicar problemas graves. Estas dependencias incluyen disponibilidad de Internet Information Services (IIS) y CPU de servidores que se utiliza para Skype de Business Server.  <br/> |
   
### <a name="alert-prioritization"></a>Prioridad de las alertas

Las alertas se clasifican en las siguientes categorías: 
  
 **Avisos de alta prioridad:** Estas alertas indican las condiciones que provocar interrupciones de servicio para grandes grupos de usuarios y requieren una acción inmediata. Las interrupciones detectadas por las transacciones sintéticas y los servicios sin conexión (como Skype para conferencias de Audio y vídeo de servidor empresarial) calificar como alertas de prioridad alta. Por el contrario, un error de componente en una única máquina no es una alerta de alta prioridad. Skype para Business Server 2015 tiene características integradas de alta disponibilidad para estas situaciones, por ejemplo, varios servidores Front-End detrás de los equilibradores de carga.
  
 **Las alertas de prioridad Media:** Estas alertas indican las condiciones que afectan a un subconjunto de usuarios o indican problemas de calidad de la llamada, por ejemplo, errores de componentes, latencia de establecimiento de llamada o inferior calidad de audio en las llamadas. Las alertas de esta categoría son con seguimiento de estado (es decir, la naturaleza de la alerta cambia según el estado de la conexión de red.) Por ejemplo, si tiempos de establecimiento de llamada indican latencia pero, a continuación, volver a un umbral normal, esta alerta prioridad Media sería resuelto automático en System Center Operations Manager y los administradores no tendría que tomar medidas. Los administradores suelen tratarse las alertas que no se pueden resolver automático en el mismo día laborable.
  
 **Otras alertas:** estas alertas se generan desde componentes que podrían afectar a un usuario o a un subconjunto de usuarios determinado. Por ejemplo, una alerta típica sería que el servicio de libreta de direcciones no analiza la entrada de Servicios de dominio de Active Directory® (AD DS) para el usuario: testuser@contoso.com. Los administradores pueden corregir estas alertas siempre que tengan tiempo disponible.
  
### <a name="synthetic-transactions"></a>Transacciones sintéticas

Skype para paquetes de administración de Business Server 2015 proporcionar aumento de la cobertura de alertas a través de las transacciones sintéticas. Las transacciones sintéticas están integrados en el módulo de administración de Operations Manager para probar los escenarios de extremo a otro usuario de cmdlets de Windows PowerShell. Al designar un servidor para ejecutar transacciones sintéticas, estos cmdlets se desencadenan periódicamente por el módulo de administración. Errores de resultante de una transacción sintética generan una alerta de estado. Aquí están las transacciones sintéticas compatibles para Skype para Business Server 2015:
  
**Transacciones sintéticas compatibles para registro, presencia y contactos**

||||
|:-----|:-----|:-----|
|1  <br/> |Registro (inicio de sesión del usuario)  <br/> |Lync Server 2010 disponibles y posteriores  <br/> |
|2  <br/> |Servicio de libreta de direcciones (descarga de archivos)  <br/> |Lync Server 2010 disponibles y posteriores  <br/> |
|3  <br/> |Consulta web de la libreta de direcciones  <br/> |Lync Server 2010 disponibles y posteriores  <br/> |
|4  <br/> |Presence  <br/> |Lync Server 2010 disponibles y posteriores  <br/> |
|5  <br/> |Almacenamiento de contactos unificado  <br/> |Lync Server 2013 disponibles y posteriores  <br/> |
   
**Transacciones sintéticas compatibles para servicios punto a punto**

||||
|:-----|:-----|:-----|
|6  <br/> |Mensajes instantáneos de punto a punto  <br/> |Disponible en Lync Server 2010 y más allá  <br/> |
|7  <br/> |Audio y vídeo punto a punto  <br/> |Disponible en Lync Server 2010 y más allá  <br/> |
|8  <br/> |Mensajería instantánea punto a punto MCX (móvil)  <br/> |Disponible en la versión de septiembre de 2011 de Lync Server 2010 para Skype para profesionales de 2015  <br/> |
 
> [!NOTE]
> Compatibilidad con MCX para los clientes móviles heredados ya no está disponible en Skype para Business Server 2019. Los usuarios deben actualizar a un cliente actual.
  
**Transacciones sintéticas compatibles para conferencias y chat persistente**

||||
|:-----|:-----|:-----|
|9  <br/> |Conferencias de audio y vídeo  <br/> |Disponible en Lync Server 2010 y más allá  <br/> |
|10  <br/> |Conferencias de datos  <br/> |Disponible en Lync Server 2013 y más allá  <br/> |
|11  <br/> |Conferencia de mensajes instantáneos  <br/> |Disponible en Lync Server 2010 y más allá  <br/> |
|12  <br/> | Chat persistente <br/> |Disponible en Lync Server 2013 y más allá  <br/> |
|13  <br/> |Iniciador de participación en reuniones (reuniones programadas)  <br/> |Disponible en Lync Server 2013 y más allá  <br/> |
|14  <br/> |Conferencia de acceso telefónico  <br/> |Es una novedad de Skype para Business Server 2015  <br/> |
|15  <br/> |Conferencia de uso compartido de aplicaciones  <br/> |Es una novedad de Skype para Business Server 2015  <br/> |
|16  <br/> |Conferencia USWA (participación en reunión web)  <br/> |Es una novedad de Skype para Business Server 2015  <br/> |
   
**Transacciones sintéticas compatibles para dependencias de asociado y red**

||||
|:-----|:-----|:-----|
|17  <br/> |Conectividad del servidor perimetral de A/V  <br/> |Disponible en Lync Server 2013 y más allá  <br/> |
|18  <br/> |Conectividad de mensajería unificada de Exchange de conectividad de servidor perimetral AV (correo de voz)  <br/> |Disponible en Lync Server 2013 y más allá  <br/> |
|19  <br/> |Llamada punto a punto de RTC  <br/> |Disponible en Lync Server 2010 y más allá  <br/> |
|20  <br/> |Mensajería instantánea XMPP (federación)  <br/> |Disponible en Lync Server 2013 y Skype para profesionales de 2015  <br/> |
|21  <br/> |Servidor de interoperabilidad de vídeo  <br/> |Es una novedad de Skype para Business Server 2015  <br/> |
   
## <a name="how-health-rolls-up"></a>Resumen del estado

En la siguiente tabla se muestra los Estados de mantenimiento de objetos el Skype para Business Server paquete de supervisión.
  
|**Objeto de módulo de administración**|**Descripción**|
|:-----|:-----|
|Skype para la implementación de servidor de la empresa  <br/> |Representa la implementación de Skype para Business Server 2015 en la organización.  <br/> |
|Skype para sitio Business Server  <br/> |Representa distintas ubicaciones geográficas donde se han implementado los servicios.  <br/> |
|Skype para grupo de servidores de negocio  <br/> |Grupo de servidores (dentro de un sitio) que proporciona servicios de comunicaciones, como la mensajería instantánea y las conferencias, a los usuarios. Es aplicable a grupos de servidores front-end, grupos de servidores perimetrales y grupos de directores, incluso si solo hay una sola máquina de un determinado grupo.  <br/> |
|Skype para la función de servidor de negocio  <br/> |Función de servidor que hospeda Skype para el servicio del servidor de negocio.  <br/> |
|Skype para servicio Business Server  <br/> |Representa una función implementada en un equipo específico (por ejemplo, servicio de usuario en fp0.contoso.com).  <br/> |
|Skype para el componente de servidor empresarial  <br/> |Componente del servicio (por ejemplo, el componente de descarga de la libreta de direcciones es una parte del servicio web).  <br/> |
|Skype para monitor de grupo de servidores de servidor empresarial  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo.  <br/> |
|Skype para Business Server registrador Monitor  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo de registradores.  <br/> |
|Skype para monitor de grupo de servidores de servicios de Business Server usuario  <br/> |Instancia de transacciones sintéticas que se ejecutan en un grupo de servicios de usuario.  <br/> |
|Skype para monitor de grupo de servidores de voz de servidor empresarial  <br/> |Instancia de transacciones sintéticas que se ejecutan en un solo grupo de voz.  <br/> |
|Skype para monitor de puerto del servidor empresarial  <br/> |Instancia de comprobaciones de puerto que se ejecuta en un grupo.  <br/> |
|Monitor de URL simple  <br/> |Realiza el sondeo HTTPS de las direcciones URL simples configuradas en una implementación.  <br/> |
   
![Resumen SCOM](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Un Skype para grupo de servidores de negocio puede contener varios Skype individual para los sistemas de Business Server (con más de un Skype para Business Server role, Skype para servicio Business Server y Skype para el componente de servidor empresarial). Por lo tanto, el error de un servidor individual o componente es menos crítico en el estado general de la Skype para el grupo de servidores empresariales, debido a que otros servidores en el mismo grupo pueden proporcionar el servicio de aplicación para el cliente. El mantenimiento se resumir en un nivel de porcentaje para el Skype para grupo de servidores empresariales. 
  
El Skype para Business Server grupo Monitor realiza las transacciones sintéticas contra un Skype para grupo de servidores empresariales. Los errores consecutivos en una o más transacciones sintéticas (proceso conocido como intervalo de sondeo consecutivos) resumirán el mantenimiento en el nivel del grupo (el peor de cualquier transacción sintética), tal y como se muestra en el siguiente diagrama. 
  
![Sondeo consecutivo de resumen SCOM](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Práctica recomendada: Crear un módulo de administración para personalizaciones

De forma predeterminada, Operations Manager guarda todas las personalizaciones, como las invalidaciones del módulo de administración predeterminado. Como práctica recomendada, debe crear un módulo de administración independiente para cada módulo de administración sellado que desee personalizar. 
  
Cuando se crea un módulo de administración de para almacenar configuraciones personalizadas para un módulo de administración sellado, se recomienda asignar un nombre adecuado para el nuevo módulo de administración, como "Personalizaciones de Skype Empresarial Server 2015". 
  
La creación de un nuevo módulo de administración para almacenar las personalizaciones de cada módulo de administración sellado facilita la exportación de las personalizaciones de un entorno de prueba a un entorno de producción. Esto también hace que sea más fácil eliminar un módulo de administración, porque antes de eliminarlo deben eliminarse todas sus dependencias. Si las personalizaciones para todos los paquetes de administración se guardan en el módulo de administración predeterminado y es necesario eliminar un único módulo de administración, en primer lugar se debe eliminar el módulo de administración predeterminado, que elimina también las personalizaciones realizadas en otros módulos de administración. 
  
## <a name="links"></a>Vínculos

Los siguientes vínculos permiten obtener acceso a información sobre tareas comunes asociadas con los módulos de supervisión de System Center 2012:
  
- [Ciclo de vida del paquete de administración](https://technet.microsoft.com/en-us/library/hh212732.aspx)
    
- [Procedimiento para importar un paquete de administración de Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212691.aspx)
    
- [Procedimiento para reemplazar una regla o un Monitor](https://technet.microsoft.com/en-us/library/hh212869.aspx)
    
- [Procedimiento para crear una ejecución como cuenta en Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh321655.aspx)
    
- [Administración de ejecutar como cuentas y perfiles](https://technet.microsoft.com/en-us/library/hh212714.aspx)
    
- [Procedimiento para exportar un paquete de administración de Operations Manager](https://technet.microsoft.com/en-us/library/hh320149.aspx)
    
- [Cómo quitar un módulo de administración de Operations Manager](https://technet.microsoft.com/en-us/library/hh230746.aspx)
    
Los siguientes vínculos permiten obtener acceso a información sobre tareas comunes asociadas con los módulos de supervisión de System Center 2007:
  
- [Administración del ciclo de vida del paquete de administración](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Procedimiento para importar un paquete de administración de Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Cómo supervisar el uso de invalida](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Procedimiento para crear una ejecución como cuenta en Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Procedimiento para modificar una ejecución existente como perfil](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Cómo exportar las personalizaciones del paquete de administración](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Cómo quitar un paquete de administración](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Para preguntas acerca de Operations Manager y supervisión de paquetes, vea el [foro de la Comunidad de System Center Operations Manager](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Un recurso útil es el blog [Del sistema Center Operations Manager lanza](https://opsmgrunleashed.wordpress.com/) , que contiene entradas de "Por ejemplo" para los paquetes específicos de supervisión.
  
Para obtener información adicional acerca de Operations Manager, consulte los blogs siguientes: 
  
- [Blog del equipo de Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [OpsMgr Blog de Kevin Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Pensamientos en OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog de Raphael Burri](https://rburri.wordpress.com/)
    
- [Espacio de administración de BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [OpsMgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Toda la información y contenido de sitios que no sean de Microsoft la proporciona el propietario o los usuarios del sitio web correspondiente. Microsoft no ofrece ninguna garantía, explícita, implícita o legal, con respecto a la información de dichos sitios web. 
  
## <a name="see-also"></a>Vea también

[Skype para herramientas de administración de Business Server 2015](../../management-tools/management-tools.md)