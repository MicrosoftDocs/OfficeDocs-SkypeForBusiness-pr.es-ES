---
title: Requisitos de protocolo y puerto para los servidores
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Resumen: Revise las consideraciones de uso del puerto antes de implementar Skype para Business Server 2015.'
ms.openlocfilehash: 4bf9b7f9f1d0d0b99a8add76c4f73d4adcebea16
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="port-and-protocol-requirements-for-servers"></a>Requisitos de protocolo y puerto para los servidores
 
**Resumen:** Revise las consideraciones de uso del puerto antes de implementar Skype para Business Server 2015.
  
Skype para Business Server requiere que estén abiertos determinados puertos en los firewalls internos y externos. Además, si se ha implementado el protocolo de seguridad de Internet (IPSec) en la organización, IPSec debe estar deshabilitado en el intervalo de puertos que se usa para la entrega de audio, vídeo y vídeo panorámico. 
  
Aunque esto puede parecer complicado bit en primer lugar, el trabajo para planear esto puede realizarse mediante el [Skype para la herramienta de planeación de Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=50357). Una vez que se ha desplazado a través de las preguntas del asistente acerca de qué características que se va a utilizar, para cada sitio que defina se puede ver el informe de Firewall en el informe de administración perimetral y usar la información que aparece no existe para crear reglas de yourfirewall. También puede realizar ajustes en muchos de los nombres y las direcciones IP utilizadas para obtener más información vea [revisión del informe de Firewall](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Tenga en cuenta que puede exportar el informe de administración perimetral a una hoja de cálculo de Excel y el informe de Firewall será una de las hojas de cálculo en el archivo. 
  
También puede encontrar la información en estas tablas en forma de diagrama revisando el póster de cargas de trabajo de protocolo vinculado fuera el artículo [Technical diagrams de Skype para Business Server 2015](../../technical-diagrams.md) .
  
## <a name="port-and-protocol-details"></a>Detalles de protocolo y puerto

En esta sección se resume los puertos y protocolos utilizados por los servidores, los equilibradores de carga y los clientes en un Skype para la implementación de Business Server.
  
> [!NOTE]
> Cuando se inicia Skype para Business Server, abre los puertos requeridos en el Firewall de Windows. Ya debe ejecutar Firewall de Windows en las aplicaciones más normales, pero si no va a usa Skype para Business Server funcionará sin él. 
  
Para obtener información detallada acerca de la configuración de firewall para componentes perimetrales, vea [escenarios de servidor perimetral de Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
En la tabla siguiente se enumeran los puertos que debe abrir en cada rol del servidor interno. 
  
**Puertos de servidor obligatorios (por rol de servidor)**

|**Función de servidor**|**Nombre de servicio**|**Puerto**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|Todos los servidores  <br/> |Explorador SQL  <br/> |1434  <br/> |UDP  <br/> |Explorador SQL para la copia replicada local de la base de datos del Almacén de administración central.  <br/> |
|Servidores front-end  <br/> |Skype para servicio Business Server front-end  <br/> |5060  <br/> |TCP  <br/> |Opcionalmente lo usan los servidores Standard Edition y front-end para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.  <br/> |
|Servidores front-end  <br/> |Skype para servicio Business Server front-end  <br/> |5061  <br/> | TCP (TLS) <br/> |Lo usan los servidores Standard Edition y los grupos de servidores front-end para todas las comunicaciones SIP internas entre los servidores (MTLS), para las comunicaciones SIP entre el cliente y el servidor (TLS) y para las comunicaciones SIP entre los servidores front-end y los servidores de mediación (MTLS). También se usa para las comunicaciones con un servidor de supervisión.  <br/> |
| Servidores front-end <br/> |Skype para servicio Business Server front-end  <br/> |444  <br/> | HTTPS <br/> TCP  <br/> |Se usa para las comunicaciones HTTPS entre el foco (Skype para el componente de Business Server que administra el estado de la conferencia) y los servidores individuales.  <br/> Este puerto también se utiliza para las comunicaciones TCP entre aplicaciones de sucursal con funciones de supervivencia y servidores Front-End.  <br/> |
|Servidores front-end  <br/> |Skype para servicio Business Server front-end  <br/> |135  <br/> |DCOM y llamada a procedimiento remoto (RPC)  <br/> |Se usa para operaciones basadas en DCOM, como la migración de los usuarios, la sincronización del replicador de usuarios y la sincronización de la libreta de direcciones.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de conferencia de mensajería instantánea de servidor empresarial  <br/> |5062  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de mensajería instantánea.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de conferencia Web de Business Server  <br/> |8057  <br/> |TCP (TLS)  <br/> |Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de compatibilidad de conferencia Web Business Server  <br/> |8058  <br/> |TCP (TLS)  <br/> |Se usa para escuchar las conexiones del modelo de objetos de compartidos persistente (PSOM) desde el cliente de Live Meeting y versiones anteriores de Skype para Business Server.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de conferencia de Audio y vídeo de servidor empresarial  <br/> |5063  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de audio y vídeo (A/V).  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de conferencia de Audio y vídeo de servidor empresarial  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |Intervalo de puertos de medios que se usa para conferencias de vídeo.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de compatibilidad de negocio servidor Web  <br/> |80  <br/> |HTTP  <br/> |Se usa para la comunicación entre los servidores front-end y los FQDN (direcciones URL que usan los componentes web de IIS) cuando no se usa HTTPS.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de compatibilidad de negocio servidor Web  <br/> |443  <br/> |HTTPS  <br/> |Se usa para la comunicación entre los servidores front-end y los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS).  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de compatibilidad de negocio servidor Web  <br/> |8080  <br/> |TCP y HTTP  <br/> |Lo usan los componentes web para acceso externo.  <br/> |
|Servidores front-end  <br/> |Componente de servidor web  <br/> |4443  <br/> |HTTPS  <br/> |Comunicaciones entre grupos de HTTPS (desde proxy inverso) y HTTPS front-end para el inicio de sesión con detección automática.  <br/> |
|Servidores front-end  <br/> |Componente de servidor web  <br/> |8060  <br/> |TCP (MTLS)  <br/> ||
|Servidores front-end  <br/> |Componente de servidor web  <br/> |8061  <br/> |TCP (MTLS)  <br/> ||
|Servidores front-end  <br/> |Componente de servicios de movilidad  <br/> |5086  <br/> |TCP (MTLS)  <br/> |Puerto SIP que usan los procesos internos de los servicios de movilidad  <br/> |
|Servidores front-end  <br/> |Componente de servicios de movilidad  <br/> |5087  <br/> |TCP (MTLS)  <br/> |Puerto SIP que usan los procesos internos de los servicios de movilidad  <br/> |
|Servidores front-end  <br/> |Componente de servicios de movilidad  <br/> |443  <br/> |HTTPS  <br/> ||
|Servidores front-end  <br/> |Skype para el servicio de operador de conferencia del servidor empresarial (telefónico)  <br/> |5064  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de las conferencias de acceso telefónico local.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de operador de conferencia del servidor empresarial (telefónico)  <br/> |5072  <br/> |TCP  <br/> |Se utiliza para las solicitudes SIP entrantes operador (conferencia de acceso telefónico).  <br/> |
|Servidores front-end que también ejecutan un servidor de mediación combinado  <br/> |Skype para servicio de mediación de servidor empresarial  <br/> |5070  <br/> |TCP  <br/> |Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end al servidor de mediación.  <br/> |
|Servidores front-end que también ejecutan un servidor de mediación combinado  <br/> |Skype para servicio de mediación de servidor empresarial  <br/> |5067  <br/> |TCP (TLS)  <br/> |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.  <br/> |
|Servidores front-end que también ejecutan un servidor de mediación combinado  <br/> |Skype para servicio de mediación de servidor empresarial  <br/> |5068  <br/> |TCP  <br/> |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.  <br/> |
|Servidores front-end que también ejecutan un servidor de mediación combinado  <br/> |Skype para servicio de mediación de servidor empresarial  <br/> |5081  <br/> |TCP  <br/> |Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.  <br/> |
|Servidores front-end que también ejecutan un servidor de mediación combinado  <br/> |Skype para servicio de mediación de servidor empresarial  <br/> |5082  <br/> |TCP (TLS)  <br/> |Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.  <br/> |
|Servidores front-end  <br/> |Skype para uso compartido de Business Server aplicaciones de servicio  <br/> |5065  <br/> |TCP  <br/> |Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.  <br/> |
|Servidores front-end  <br/> |Skype para uso compartido de Business Server aplicaciones de servicio  <br/> |49152-65535  <br/> |TCP  <br/> |Intervalo de puertos de medios que se usa para compartir aplicaciones.  <br/> |
|Servidores front-end  <br/> |Skype para servicio de anuncio de conferencia del servidor empresarial  <br/> |5073  <br/> |TCP  <br/> |Se utiliza para las solicitudes SIP entrantes de la Skype para servicio de anuncio de conferencia del servidor empresarial (es decir, para conferencias de acceso telefónico).  <br/> |
|Servidores front-end  <br/> |Skype para servicio de estacionamiento de llamadas de servidor empresarial  <br/> |5075  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de la aplicación Estacionamiento de llamadas.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de prueba de Audio de servidor empresarial  <br/> |5076  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes del servicio de prueba de audio.  <br/> |
|Servidores front-end  <br/> |No aplicable  <br/> |5066  <br/> |TCP  <br/> |Se usa para la puerta de enlace 9-1-1 mejorado (E9-1-1) saliente.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de grupo de respuesta de servidor empresarial  <br/> |5071  <br/> |TCP  <br/> |Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.  <br/> |
|Servidores front-end  <br/> |Skype para el servicio de grupo de respuesta de servidor empresarial  <br/> |8404  <br/> |TCP (MTLS)  <br/> |Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.  <br/> |
|Servidores front-end  <br/> |Skype para servicio de directiva de ancho de banda de servidor empresarial  <br/> |5080  <br/> |TCP  <br/> |Lo usa el servicio de directiva de ancho de banda del tráfico TURN perimetral A/V para el servicio de control de admisión de llamadas.  <br/> |
|Servidores front-end  <br/> |Skype para servicio de directiva de ancho de banda de servidor empresarial  <br/> |448  <br/> |TCP  <br/> |Se utiliza para el control de admisión de llamadas por el Skype servicio de directiva de ancho de banda de servidor empresarial.  <br/> |
|Front-End los servidores en el que reside el almacén de Administración Central  <br/> | Skype para el servicio de agente de Replicador maestro de servidor empresarial <br/> |445  <br/> |TCP  <br/> |Se usa para enviar datos de configuración desde el almacén de Administración Central para los servidores que ejecutan Skype para Business Server.  <br/> |
|Todos los servidores  <br/> |Explorador SQL  <br/> |1434  <br/> |UDP  <br/> |Explorador SQL para la copia replicada local de la Administración Central de almacenar datos en la instancia local de SQL Server  <br/> |
|Todos los usuarios internos  <br/> |Varios  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |El intervalo de puertos de medios se usa para audioconferencias en todos los servidores internos. Utilizado por todos los servidores que terminar audio: servidores Front-End (para Skype para el servicio de operador de conferencia del servidor empresarial, Skype para servicio de anuncio de conferencia del servidor empresarial y Skype para el servicio de conferencia de Audio y vídeo de servidor empresarial), y Servidor de mediación.  <br/> |
|Servidores de Office Web Apps  <br/> ||443  <br/> ||Usa Skype para Business Server 2015 para conectarse a Office Web Apps Server.  <br/> |
|Directores  <br/> |Skype para servicio Business Server front-end  <br/> |5060  <br/> |TCP  <br/> |Se usa opcionalmente para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.  <br/> |
|Directores  <br/> |Skype para servicio Business Server front-end  <br/> |444  <br/> |HTTPS  <br/> TCP  <br/> |Comunicación entre servidores front-end y Director. Además, el certificado de cliente publicar (en servidores Front-End) o validar si ya se ha publicado el certificado de cliente.  <br/> |
|Directores  <br/> |Skype para el servicio de compatibilidad de negocio servidor Web  <br/> |80  <br/> |TCP  <br/> |Se usa para la comunicación inicial desde los Directores a los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS). En condiciones normales, cambiará a tráfico HTTPS a través del puerto 443 y el tipo de protocolo TCP.  <br/> |
|Directores  <br/> |Skype para el servicio de compatibilidad de negocio servidor Web  <br/> |443  <br/> |HTTPS  <br/> |Se usa para la comunicación desde los Directores a los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS).  <br/> |
|Directores  <br/> |Skype para servicio Business Server front-end  <br/> |5061  <br/> |TCP  <br/> |Se usa para comunicaciones internas entre servidores y para conexiones de cliente.  <br/> |
|Servidores de mediación  <br/> |Skype para servicio de mediación de servidor empresarial  <br/> |5070  <br/> |TCP  <br/> |Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end.  <br/> |
|Servidores de mediación  <br/> |Skype para servicio de mediación de servidor empresarial  <br/> |5067  <br/> |TCP (TLS)  <br/> |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.  <br/> |
|Servidores de mediación  <br/> |Skype para servicio de mediación de servidor empresarial  <br/> |5068  <br/> |TCP  <br/> |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.  <br/> |
|Servidores de mediación  <br/> |Skype para servicio de mediación de servidor empresarial  <br/> |5070  <br/> |TCP (MTLS)  <br/> |Se usa para solicitudes SIP desde los servidores front-end.  <br/> |
|Servidor front-end de chat persistente  <br/> |SIP de chat persistente  <br/> |5041  <br/> |TCP (MTLS)  <br/> ||
|Servidor front-end de chat persistente  <br/> |Windows Communication Foundation (WCF) de chat persistente  <br/> |881  <br/> |TCP (TLS) y TCP (MTLS)  <br/> ||
|Servidor front-end de chat persistente  <br/> |Servicio de transferencia de archivos de chat persistente  <br/> |443  <br/> |TCP (TLS)  <br/> ||
   
> [!NOTE]
> Algunos escenarios de control remoto de llamadas requieren una conexión entre el servidor front-end o el Director y la PBX. Aunque Skype para Business Server ya no usa el puerto TCP 5060, durante la implementación de control remoto de llamadas se crea una configuración de servidor de confianza, que se asocia el FQDN del servidor de línea de control remoto de llamadas con el puerto TCP que el servidor Front-End o un Director que va a usar para conectarse a la Sistema PBX. Para obtener información detallada, vea el cmdlet **CsTrustedApplicationComputer** en el Skype para la documentación del Shell de administración de servidor empresarial.
  
Para los grupos que solo usan equilibrio de carga de hardware (no equilibrio de carga de DNS), en la siguiente tabla se muestran los puertos que necesitan para abrir los equilibradores de carga de hardware.
  
**Puertos del equilibrador de carga de hardware si usa sólo Hardware de equilibrio de carga**

|**Equilibrador de carga**|**Puerto**|**Protocolo**|
|:-----|:-----|:-----|
|Equilibrador de carga del servidor front-end  <br/> |5061  <br/> |TCP (TLS)  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |444  <br/> |HTTPS  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |135  <br/> |DCOM y llamada a procedimiento remoto (RPC)  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |80  <br/> |HTTP  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |8080  <br/> |TCP - recuperación cliente y dispositivo del certificado raíz de servidor Front-End - clientes y dispositivos autenticados por NTLM  <br/> |
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
  
**Puertos del equilibrador de carga de hardware si usa equilibrio de carga de DNS**

|**Equilibrador de carga**|**Puerto**|**Protocolo**|
|:-----|:-----|:-----|
|Equilibrador de carga del servidor front-end  <br/> |80  <br/> |HTTP  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |443  <br/> |HTTPS  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |8080  <br/> |TCP - recuperación cliente y dispositivo del certificado raíz de servidor Front-End - clientes y dispositivos autenticados por NTLM  <br/> |
|Equilibrador de carga del servidor front-end  <br/> |4443  <br/> |HTTPS (desde proxy inverso)  <br/> |
|Equilibrador de carga del Director  <br/> |443  <br/> |HTTPS  <br/> |
|Equilibrador de carga del Director  <br/> |4443  <br/> |HTTPS (desde proxy inverso)  <br/> |
   
**Puertos de cliente requeridos**

|**Componente**|**Puerto**|**Protocolo**|**Notas**|
|:-----|:-----|:-----|:-----|
|Clientes  <br/> |67/68  <br/> |DHCP  <br/> |Skype para Business Server lo usa para encontrar el FQDN del registrador (es decir, si se produce un error de SRV de DNS y las opciones manuales no están configuradas).  <br/> |
|Clientes  <br/> |443  <br/> |TCP (TLS)  <br/> |Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.  <br/> |
|Clientes  <br/> |443  <br/> |TCP (PSOM/TLS)  <br/> |Se usa para el acceso de usuarios externos a las sesiones de conferencia web.  <br/> |
|Clientes  <br/> |443  <br/> |TCP (STUN/MSTURN)  <br/> |Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP).  <br/> |
|Clientes  <br/> |3478  <br/> |UDP (STUN/MSTURN)  <br/> |Se usa para el acceso de usuarios externos a los medios y las sesiones de A/V (UDP)  <br/> |
|Clientes  <br/> |5061  <br/> |TCP (MTLS)  <br/> |Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.  <br/> |
|Clientes  <br/> |6891-6901  <br/> |TCP  <br/> |Se usa para la transferencia de archivos entre Skype para clientes empresariales y clientes anteriores.  <br/> |
|Clientes  <br/> |1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de puertos de audio (se requieren 20 puertos como mínimo).  <br/> |
|Clientes  <br/> |1024-65535\*  <br/> |TCP/UDP  <br/> |Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo).  <br/> |
|Clientes  <br/> |1024-65535\*  <br/> |TCP  <br/> |Transferencias de archivos de punto a punto (para la transferencia de archivos de conferencia, los clientes usan PSOM).  <br/> |
|Clientes  <br/> |1024-65535\*  <br/> |TCP  <br/> |Uso compartido de aplicaciones.  <br/> |
|Teléfono de área común Aastra 6721ip  <br/> Teléfono de escritorio Aastra 6725ip  <br/> Teléfono IP HP 4110 (teléfono de área común)  <br/> Teléfono IP HP 4120 (teléfono de escritorio)  <br/> Teléfono de área común Polycom CX500 IP  <br/> Teléfono de escritorio Polycom CX600 IP  <br/> Teléfono de escritorio Polycom CX700 IP  <br/> Teléfono de conferencia Polycom CX3000 IP  <br/> |67/68  <br/> |DHCP  <br/> |Los dispositivos enumerados lo usan para encontrar el Skype para el certificado de servidor empresarial, FQDN aprovisionamiento y FQDN del registrador.  <br/> |
   
\*Para configurar puertos específicos para estos tipos de medios, use el cmdlet CsConferencingConfiguration (los parámetros ClientMediaPortRangeEnabled, ClientMediaPort y ClientMediaPortRange).
  
> [!NOTE]
> Los programas de instalación de Skype para clientes empresariales crean automáticamente las excepciones de firewall del sistema operativo en el equipo cliente. 
  
> [!NOTE]
> Los puertos que se usan para el acceso de usuarios externos son necesarios para cualquier escenario en el que el cliente debe atravesar firewall de la organización (por ejemplo, las comunicaciones externas o reuniones hospedadas por otras organizaciones). 
  
## <a name="ipsec-exceptions"></a>Excepciones de IPsec

En aquellas redes empresariales donde el protocolo de seguridad de Internet (IPsec) (consulte IETF RFC 4301-4309) está implementado, IPsec se necesita deshabilitar en el intervalo de puertos usado para la entrega de audio, vídeo y vídeo panorámico. Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios por la negociación de IPsec.
  
En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas. 
  
**Excepciones de IPsec recomendadas**

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
   

