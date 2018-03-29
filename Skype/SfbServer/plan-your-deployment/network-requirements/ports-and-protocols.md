---
title: Requisitos de protocolo y puerto para servidores
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Resumen: Revisar las consideraciones de uso de puerto antes de implementar Skype para Business Server 2015.'
ms.openlocfilehash: 1e66437b5422e8de571f5db3ca0892377a10b9d9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="port-and-protocol-requirements-for-servers"></a>Requisitos de protocolo y puerto para servidores
 
**Resumen:** Revisar las consideraciones de uso de puerto antes de implementar Skype para Business Server 2015.
  
Skype para Business Server requiere que estén abiertos determinados puertos en los servidores de seguridad internos y externos. Además, si se ha implementado el protocolo de seguridad de Internet (IPSec) en la organización, IPSec debe estar deshabilitado en el intervalo de puertos que se usa para la entrega de audio, vídeo y vídeo panorámico. 
  
Aunque pueda parecer complicado bit en primer lugar, el trabajo pesado para planear esto puede hacerse usando el [Skype para la herramienta de planeación de Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357). Una vez que se ha desplazado a través de las preguntas del asistente acerca de qué características piensa utilizar, para cada sitio que define puede ver el informe de Firewall en el informe de administración de borde y utilizar la información de la lista para crear reglas de yourfirewall. También puede realizar ajustes a muchos de los nombres y las direcciones IP utilizadas para obtener información detallada Consulte [Revisar el informe del servidor de seguridad](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Tenga en cuenta que puede exportar el informe de administración de borde a una hoja de cálculo de Excel y el informe del servidor de seguridad será una de las hojas de cálculo en el archivo. 
  
También puede encontrar la información de estas tablas en forma de diagrama revisando el póster de cargas de trabajo de protocolo vinculado fuera el artículo [diagramas técnicos de Skype para Business Server 2015](../../technical-diagrams.md) .
  
## <a name="port-and-protocol-details"></a>Detalles de protocolo y puerto

Esta sección resume los puertos y protocolos utilizados por los clientes en un Skype, equilibradores de carga y servidores para la implementación de Business Server.
  
> [!NOTE]
> Cuando se inicia Skype para Business Server, abre los puertos necesarios en Firewall de Windows. Firewall de Windows ya debe estar en ejecución en las aplicaciones más normales, pero si no está siendo utilizado Skype para Business Server funcionará sin él. 
  
Para obtener más información acerca de la configuración de firewall para los componentes de borde, vea [escenarios de servidor perimetral en Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
En la tabla siguiente se enumeran los puertos que debe abrir en cada rol del servidor interno. 
  
**Puertos de servidor necesarios (mediante la función de servidor)**

|**Función de servidor**|**Nombre de servicio**|**Puerto**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|Todos los servidores  <br/> |Explorador SQL  <br/> |1434  <br/> |UDP  <br/> |Explorador SQL para la copia replicada local de la base de datos del Almacén de administración central.  <br/> |
|Servidores front-end  <br/> |Skype para servicio Business Server front-end  <br/> |5060  <br/> |TCP  <br/> |Opcionalmente lo usan los servidores Standard Edition y front-end para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.  <br/> |
|Servidores front-end  <br/> |Skype para servicio Business Server front-end  <br/> |5061  <br/> | TCP (TLS) <br/> |Lo usan los servidores Standard Edition y los grupos de servidores front-end para todas las comunicaciones SIP internas entre los servidores (MTLS), para las comunicaciones SIP entre el cliente y el servidor (TLS) y para las comunicaciones SIP entre los servidores front-end y los servidores de mediación (MTLS). También se usa para las comunicaciones con un servidor de supervisión.  <br/> |
| Servidores front-end <br/> |Skype para servicio Business Server front-end  <br/> |444  <br/> | HTTPS <br/> TCP  <br/> |Se utiliza para la comunicación HTTPS entre el foco (Skype para el componente de servidor empresarial que administra el estado de la conferencia) y los servidores individuales.  <br/> Este puerto también se utiliza para la comunicación TCP entre equipos de sucursales que sobreviven y servidores frontales.  <br/> |
|Servidores front-end  <br/> |Skype para servicio Business Server front-end  <br/> |135  <br/> |DCOM y llamada a procedimiento remoto (RPC)  <br/> |Se usa para operaciones basadas en DCOM, como la migración de los usuarios, la sincronización del replicador de usuarios y la sincronización de la libreta de direcciones.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de conferencia de negocios servidor IM  <br/> |5062  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de mensajería instantánea.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de conferencias Web de Business Server  <br/> |8057  <br/> |TCP (TLS)  <br/> |Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de compatibilidad con conferencias Web Business Server  <br/> |8058  <br/> |TCP (TLS)  <br/> |Se utiliza para escuchar las conexiones del modelo de objeto de compartidos persistente (PSOM) desde el cliente de Live Meeting y versiones anteriores de Skype para Business Server.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de conferencia de Audio y vídeo servidor Business  <br/> |5063  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de audio y vídeo (A/V).  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de conferencia de Audio y vídeo servidor Business  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Intervalo de puertos de medios que se usa para conferencias de vídeo.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de compatibilidad de Business Server Web  <br/> |80  <br/> |HTTP  <br/> |Se usa para la comunicación entre los servidores front-end y los FQDN (direcciones URL que usan los componentes web de IIS) cuando no se usa HTTPS.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de compatibilidad de Business Server Web  <br/> |443  <br/> |HTTPS  <br/> |Se usa para la comunicación entre los servidores front-end y los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS).  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de compatibilidad de Business Server Web  <br/> |8080  <br/> |TCP y HTTP  <br/> |Lo usan los componentes web para acceso externo.  <br/> |
|Servidores front-end  <br/> |Componente de servidor web  <br/> |4443  <br/> |HTTPS  <br/> |Comunicaciones entre grupos de HTTPS (desde proxy inverso) y HTTPS front-end para el inicio de sesión con detección automática.  <br/> |
|Servidores front-end  <br/> |Componente de servidor web  <br/> |8060  <br/> |TCP (MTLS)  <br/> ||
|Servidores front-end  <br/> |Componente de servidor web  <br/> |8061  <br/> |TCP (MTLS)  <br/> ||
|Servidores front-end  <br/> |Componente de servicios de movilidad  <br/> |5086  <br/> |TCP (MTLS)  <br/> |Puerto SIP que usan los procesos internos de los servicios de movilidad  <br/> |
|Servidores front-end  <br/> |Componente de servicios de movilidad  <br/> |5087  <br/> |TCP (MTLS)  <br/> |Puerto SIP que usan los procesos internos de los servicios de movilidad  <br/> |
|Servidores front-end  <br/> |Componente de servicios de movilidad  <br/> |443  <br/> |HTTPS  <br/> ||
|Servidores front-end  <br/> |Skype para el servicio de operador de Conferencing Server Business (conferencia de marcado)  <br/> |5064  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de acceso telefónico local.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de operador de Conferencing Server Business (conferencia de marcado)  <br/> |5072  <br/> |TCP  <br/> |Se utiliza para las solicitudes SIP entrantes para operador (marcado en conferencias).  <br/> |
|Servidores front-end que también ejecutan un servidor de mediación combinado  <br/> |Skype para el servicio de mediación de servidor empresarial  <br/> |5070  <br/> |TCP  <br/> |Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end al servidor de mediación.  <br/> |
|Servidores front-end que también ejecutan un servidor de mediación combinado  <br/> |Skype para el servicio de mediación de servidor empresarial  <br/> |5067  <br/> |TCP (TLS)  <br/> |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.  <br/> |
|Servidores front-end que también ejecutan un servidor de mediación combinado  <br/> |Skype para el servicio de mediación de servidor empresarial  <br/> |5068  <br/> |TCP  <br/> |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.  <br/> |
|Servidores front-end que también ejecutan un servidor de mediación combinado  <br/> |Skype para el servicio de mediación de servidor empresarial  <br/> |5081  <br/> |TCP  <br/> |Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.  <br/> |
|Servidores front-end que también ejecutan un servidor de mediación combinado  <br/> |Skype para el servicio de mediación de servidor empresarial  <br/> |5082  <br/> |TCP (TLS)  <br/> |Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de uso compartido de Business Server  <br/> |5065  <br/> |TCP  <br/> |Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de uso compartido de Business Server  <br/> |49152-65535  <br/> |TCP  <br/> |Intervalo de puertos de medios que se usa para compartir aplicaciones.  <br/> |
|Servidores front-end  <br/> |Skype para servicio de anuncio de Conferencing Server Business  <br/> |5073  <br/> |TCP  <br/> |Utilizado para las solicitudes SIP entrantes para el Skype para servicio de anuncio de Conferencing Server Business (es decir, para las conferencias de acceso telefónico).  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de llamada de Server Business Park  <br/> |5075  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de la aplicación Estacionamiento de llamadas.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de prueba de Audio de servidor empresarial  <br/> |5076  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes del servicio de prueba de audio.  <br/> |
|Servidores front-end  <br/> |No aplicable  <br/> |5066  <br/> |TCP  <br/> |Se usa para la puerta de enlace 9-1-1 mejorado (E9-1-1) saliente.  <br/> |
|Servidores front-end  <br/> |Skype para servicio de grupo de respuesta de servidor empresarial  <br/> |5071  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.  <br/> |
|Servidores front-end  <br/> |Skype para servicio de grupo de respuesta de servidor empresarial  <br/> |8404  <br/> |TCP (MTLS)  <br/> |Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de directivas de ancho de banda de servidor empresarial  <br/> |5080  <br/> |TCP  <br/> |Lo usa el servicio de directiva de ancho de banda del tráfico TURN perimetral A/V para el servicio de control de admisión de llamadas.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de directivas de ancho de banda de servidor empresarial  <br/> |448  <br/> |TCP  <br/> |Se utiliza para el control de admisión de llamada por el Skype para el servicio de directivas de ancho de banda de servidor Business.  <br/> |
|Frontal servidores de fondo donde se encuentra el almacén de Administración Central  <br/> | Skype para el servicio de agente de Replicator Business Server Master <br/> |445  <br/> |TCP  <br/> |Se utiliza para ingresar datos de configuración desde el almacén de Administración Central para servidores que ejecutan Skype para Business Server.  <br/> |
|Todos los servidores  <br/> |Explorador SQL  <br/> |1434  <br/> |UDP  <br/> |Explorador de SQL para la copia replicada local de la Administración Central de almacenar datos en la instancia local de SQL Server  <br/> |
|Todos los usuarios internos  <br/> |Varios  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |El intervalo de puertos de medios se usa para audioconferencias en todos los servidores internos. Utilizado por todos los servidores que terminar audio: servidores frontales (por Skype para el servicio de operador de Conferencing Server Business, Skype para servicio de anuncio de Conferencing Server Business y Skype para servicio Business Server Audio y videoconferencia), y Servidor de mediación.  <br/> |
|Servidores de Office Web Apps  <br/> ||443  <br/> ||Utiliza Skype para Business Server 2015 para conectarse al servidor de Office Web Apps.  <br/> |
|Directores  <br/> |Skype para servicio Business Server front-end  <br/> |5060  <br/> |TCP  <br/> |Se usa opcionalmente para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.  <br/> |
|Directores  <br/> |Skype para servicio Business Server front-end  <br/> |444  <br/> |HTTPS  <br/> TCP  <br/> |Comunicación entre servidores front-end y Director. Además, el certificado de cliente publicar (en servidores frontales) o validar si ya se ha publicado el certificado de cliente.  <br/> |
|Directores  <br/> |Skype para el servicio de compatibilidad de Business Server Web  <br/> |80  <br/> |TCP  <br/> |Se usa para la comunicación inicial desde los Directores a los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS). En condiciones normales, cambiará a tráfico HTTPS a través del puerto 443 y el tipo de protocolo TCP.  <br/> |
|Directores  <br/> |Skype para el servicio de compatibilidad de Business Server Web  <br/> |443  <br/> |HTTPS  <br/> |Se usa para la comunicación desde los Directores a los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS).  <br/> |
|Directores  <br/> |Skype para servicio Business Server front-end  <br/> |5061  <br/> |TCP  <br/> |Se usa para comunicaciones internas entre servidores y para conexiones de cliente.  <br/> |
|Servidores de mediación  <br/> |Skype para el servicio de mediación de servidor empresarial  <br/> |5070  <br/> |TCP  <br/> |Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end.  <br/> |
|Servidores de mediación  <br/> |Skype para el servicio de mediación de servidor empresarial  <br/> |5067  <br/> |TCP (TLS)  <br/> |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.  <br/> |
|Servidores de mediación  <br/> |Skype para el servicio de mediación de servidor empresarial  <br/> |5068  <br/> |TCP  <br/> |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.  <br/> |
|Servidores de mediación  <br/> |Skype para el servicio de mediación de servidor empresarial  <br/> |5070  <br/> |TCP (MTLS)  <br/> |Se usa para solicitudes SIP desde los servidores front-end.  <br/> |
|Servidor front-end de chat persistente  <br/> |SIP de chat persistente  <br/> |5041  <br/> |TCP (MTLS)  <br/> ||
|Servidor front-end de chat persistente  <br/> |Windows Communication Foundation (WCF) de chat persistente  <br/> |881  <br/> |TCP (TLS) y TCP (MTLS)  <br/> ||
|Servidor front-end de chat persistente  <br/> |Servicio de transferencia de archivos de chat persistente  <br/> |443  <br/> |TCP (TLS)  <br/> ||
   
> [!NOTE]
> Algunos escenarios de control remoto de llamadas requieren una conexión entre el servidor front-end o el Director y la PBX. Aunque Skype para Business Server ya no utiliza el puerto TCP 5060, durante la implementación de control de llamada remota se crea una configuración de servidores de confianza, que asocia el FQDN de servidor de línea de RCC con el puerto TCP que utilizará el servidor Front-End o Director para conectarse a la Sistema PBX. Para obtener información detallada, vea el cmdlet **CsTrustedApplicationComputer** en el Skype para la documentación del Shell de administración de servidor empresarial.
  
Para los grupos que solo usan equilibrio de carga de hardware (no equilibrio de carga de DNS), en la siguiente tabla se muestran los puertos que necesitan para abrir los equilibradores de carga de hardware.
  
**Puertos de equilibrador de carga de hardware si utiliza sólo Hardware de equilibrio de carga**

|**Equilibrador de carga**|**Puerto**|**Protocolo**|
|:-----|:-----|:-----|
|Equilibrador de carga del servidor front-end  <br/> |5061  <br/> |TCP (TLS)  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |444  <br/> |HTTPS  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |135  <br/> |DCOM y llamada a procedimiento remoto (RPC)  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |80  <br/> |HTTP  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |8080  <br/> |Clientes TCP - cliente y dispositivo de recuperación de certificado raíz de servidor Front-End - y dispositivos autenticados por NTLM  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |443  <br/> |HTTPS  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |4443  <br/> |HTTPS (desde proxy inverso)  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |5072  <br/> |TCP  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |5073  <br/> |TCP  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |5075  <br/> |TCP  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |5076  <br/> |TCP  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |5071  <br/> |TCP  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |5080  <br/> |TCP  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |448  <br/> |TCP  <br/> |
|Equilibrador de carga del servidor de mediación  <br/> |5070  <br/> |TCP  <br/> |
|Equilibrador de carga del servidor front-end (si el grupo también ejecuta el servidor de mediación)  <br/> |5070  <br/> |TCP  <br/> |
|Equilibrador de carga del Director  <br/> |443  <br/> |HTTPS  <br/> |
|Equilibrador de carga del Director  <br/> |444  <br/> |HTTPS  <br/> |
|Equilibrador de carga del Director  <br/> |5061  <br/> |TCP  <br/> |
|Equilibrador de carga del Director  <br/> |4443  <br/> |HTTPS (desde proxy inverso)  <br/> |
   
Los grupos de servidores front-end y de Directores que usan equilibrio de carga de DNS también deben tener implementado un equilibrador de carga de hardware. En la siguiente tabla se muestran los puertos que se deben abrir en estos equilibradores de carga de hardware.
  
**Puertos de equilibrador de carga de hardware si utiliza Equilibrio de carga DNS**

|**Equilibrador de carga**|**Puerto**|**Protocolo**|
|:-----|:-----|:-----|
|Equilibrador de carga del servidor front-end  <br/> |80  <br/> |HTTP  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |443  <br/> |HTTPS  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |8080  <br/> |Clientes TCP - cliente y dispositivo de recuperación de certificado raíz de servidor Front-End - y dispositivos autenticados por NTLM  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |4443  <br/> |HTTPS (desde proxy inverso)  <br/> |
|Equilibrador de carga del Director  <br/> |443  <br/> |HTTPS  <br/> |
|Equilibrador de carga del Director  <br/> |4443  <br/> |HTTPS (desde proxy inverso)  <br/> |
   
**Puertos de cliente requeridos**

|**Componente**|**Puerto**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|
|Clientes  <br/> |67/68  <br/> |DHCP  <br/> |Utiliza Skype para Business Server para buscar el FQDN del registrador (es decir, si se produce un error de DNS SRV y configuración manual no es).  <br/> |
|Clientes  <br/> |443  <br/> |TCP (TLS)  <br/> |Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.  <br/> |
|Clientes  <br/> |443  <br/> |TCP (PSOM/TLS)  <br/> |Se usa para el acceso de usuarios externos a las sesiones de conferencia web.  <br/> |
|Clientes  <br/> |443  <br/> |TCP (STUN/MSTURN)  <br/> |Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP).  <br/> |
|Clientes  <br/> |3478  <br/> |UDP (STUN/MSTURN)  <br/> |Se usa para el acceso de usuarios externos a los medios y las sesiones de A/V (UDP)  <br/> |
|Clientes  <br/> |5061  <br/> |TCP (MTLS)  <br/> |Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.  <br/> |
|Clientes  <br/> |6891-6901  <br/> |TCP  <br/> |Se utiliza para transferir archivos entre Skype para clientes de negocios y clientes anteriores.  <br/> |
|Clientes  <br/> |1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de puertos de audio (se requieren 20 puertos como mínimo).  <br/> |
|Clientes  <br/> |1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo).  <br/> |
|Clientes  <br/> |1024-65535\*  <br/> |TCP  <br/> |Transferencias de archivos de punto a punto (para la transferencia de archivos de conferencia, los clientes usan PSOM).  <br/> |
|Clientes  <br/> |1024-65535\*  <br/> |TCP  <br/> |Uso compartido de aplicaciones.  <br/> |
|Teléfono de área común Aastra 6721ip  <br/> Teléfono de escritorio Aastra 6725ip  <br/> Teléfono IP HP 4110 (teléfono de área común)  <br/> Teléfono IP HP 4120 (teléfono de escritorio)  <br/> Teléfono de área común Polycom CX500 IP  <br/> Teléfono de escritorio Polycom CX600 IP  <br/> Teléfono de escritorio Polycom CX700 IP  <br/> Teléfono de conferencia Polycom CX3000 IP  <br/> |67/68  <br/> |DHCP  <br/> |Utilizado por los dispositivos enumerados para encontrar el Skype para Business Server certificado, aprovisionamiento FQDN y FQDN del registrador.  <br/> |
   
\*Para configurar puertos específicos para estos tipos de medios, utilice el cmdlet CsConferencingConfiguration (parámetros ClientMediaPortRangeEnabled, ClientMediaPort y ClientMediaPortRange).
  
> [!NOTE]
> Los programas de instalación de Skype para clientes empresariales crean automáticamente las excepciones de firewall necesarias de sistema operativo en el equipo cliente. 
  
> [!NOTE]
> Los puertos que se utilizan para el acceso de usuarios externos son necesarios para cualquier escenario en el que el cliente debe atravesar el servidor de seguridad de la organización (por ejemplo, las comunicaciones externas o reuniones alojadas por otras organizaciones). 
  
## <a name="ipsec-exceptions"></a>Excepciones de IPsec

En aquellas redes empresariales donde el protocolo de seguridad de Internet (IPsec) (consulte IETF RFC 4301-4309) está implementado, IPsec se necesita deshabilitar en el intervalo de puertos usado para la entrega de audio, vídeo y vídeo panorámico. Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios por la negociación de IPsec.
  
En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas. 
  
**Recomienda las excepciones de IPsec**

|**Nombre de la regla**|**IP de origen**|**Destino IP**|**Protocolo**|**Puerto de origen**|**Puerto de destino**|**Requisito de autenticación**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Servidor perimetral A/V interno entrante  <br/> |Cualquiera  <br/> |Servidor perimetral A/V interno  <br/> |UDP y TCP  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
|Servidor perimetral A/V externo entrante  <br/> |Cualquiera  <br/> |Servidor perimetral A/V externo  <br/> |UDP y TCP  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
|Servidor perimetral A/V interno saliente  <br/> |Servidor perimetral A/V interno  <br/> |Cualquiera  <br/> |UDP &amp; TCP  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
|Servidor perimetral A/V externo saliente  <br/> |Servidor perimetral A/V externo  <br/> |Cualquiera  <br/> |UDP y TCP  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
|Servidor de mediación entrante  <br/> |Cualquiera  <br/> |Servidores  <br/> de mediación  <br/> |UDP y TCP  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
|Servidor de mediación saliente  <br/> |Servidores  <br/> de mediación  <br/> |Cualquiera  <br/> |UDP y TCP  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
|Operador de conferencia entrante  <br/> |Cualquiera  <br/> |Servidor front-end que ejecuta operador de conferencia  <br/> |UDP y TCP  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
|Operador de conferencia saliente  <br/> |Servidor front-end que ejecuta operador de conferencia  <br/> |Cualquiera  <br/> |UDP y TCP  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
|Servidor de conferencia A/V entrante  <br/> |Cualquiera  <br/> |Servidores front-end  <br/> |UDP y TCP  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
|Salida de conferencia A/V  <br/> |Servidores front-end  <br/> |Cualquiera  <br/> |UDP y TCP  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
|Exchange entrante  <br/> |Cualquiera  <br/> |Mensajería unificada de Exchange  <br/> |UDP y TCP  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
|Servidores de aplicaciones compartidas entrantes  <br/> |Cualquiera  <br/> |Servidores de aplicaciones compartidas  <br/> |TCP  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
|Servidor de aplicaciones compartidas saliente  <br/> |Servidores de aplicaciones compartidas  <br/> |Cualquiera  <br/> |TCP  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
|Exchange saliente  <br/> |Mensajería unificada de Exchange  <br/> |Cualquiera  <br/> |UDP y TCP  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
|Clientes  <br/> |Cualquiera  <br/> |Cualquiera  <br/> |UDP  <br/> |Intervalo de puertos de medios especificado  <br/> |Cualquiera  <br/> |No autenticar  <br/> |
   

