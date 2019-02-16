---
title: Requisitos de protocolo y puerto para los servidores
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Resumen: Revise las consideraciones de uso del puerto antes de implementar Skype para Business Server.'
ms.openlocfilehash: a014df31ad27e5ed89b97fd7ca09979d4cfb5661
ms.sourcegitcommit: 4967c9b1010a444475dcfbdb6dd3c058494449d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2019
ms.locfileid: "30069515"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Requisitos de protocolo y puerto para los servidores
 
**Resumen:** Revise las consideraciones de uso del puerto antes de implementar Skype para Business Server.
  
Skype para Business Server requiere que estén abiertos determinados puertos en los firewalls internos y externos. Además, si se ha implementado el protocolo de seguridad de Internet (IPSec) en la organización, IPSec debe estar deshabilitado en el intervalo de puertos que se usa para la entrega de audio, vídeo y vídeo panorámico. 
  
Aunque esto puede parecer complicado bit en primer lugar, el trabajo para planear esto puede realizarse mediante el [Skype para la herramienta de planeación de Business Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725). Una vez que se ha desplazado a través de las preguntas del asistente acerca de qué características que se va a utilizar, para cada sitio que defina se puede ver el informe de Firewall en el informe de administración perimetral y usar la información que aparece no existe para crear reglas de yourfirewall. También puede realizar ajustes en muchos de los nombres y las direcciones IP utilizadas para obtener más información vea [revisión del informe de Firewall](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Tenga en cuenta que puede exportar el informe de administración perimetral a una hoja de cálculo de Excel y el informe de Firewall será una de las hojas de cálculo en el archivo. 
  
También puede encontrar la información en estas tablas en forma de diagrama revisando el póster de cargas de trabajo de protocolo vinculado fuera el artículo [Technical diagrams de Skype para Business Server 2015](../../technical-diagrams.md) .
> [!NOTE]
> - Si se está implementando Skype para profesionales en línea (O365) hacen referencia a [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). Entornos híbridos deberá hacer referencia a este tema y también [Planear la conectividad híbrida](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
> - Se puede tener los servidores de seguridad de hardware o software, no requieren modelos específicos o versiones. Lo que importa es qué puertos están en la lista blanca, por lo que el servidor de seguridad no poner en peligro el funcionamiento de Skype para Business Server.
  
## <a name="port-and-protocol-details"></a>Detalles de protocolo y puerto

En esta sección se resume los puertos y protocolos utilizados por los servidores, los equilibradores de carga y los clientes en un Skype para la implementación de Business Server.
  
> [!NOTE]
> Cuando se inicia Skype para Business Server, abre los puertos requeridos en el Firewall de Windows. Ya debe ejecutar Firewall de Windows en las aplicaciones más normales, pero si no va a usa Skype para Business Server funcionará sin él. 
  
Para obtener información detallada acerca de la configuración de firewall para componentes perimetrales, vea [escenarios de servidor perimetral de Skype para Business Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
En la tabla siguiente se enumeran los puertos que debe abrir en cada rol del servidor interno. 
  
**Puertos de servidor obligatorios (por rol de servidor)**

|Rol de servidor|Nombre de servicio|Puerto|Protocolo|Notas|
|:-----|:-----|:-----|:-----|:-----|
|Todos los servidores  |Explorador SQL  |1434  |UDP  |Explorador SQL para la copia replicada local de la base de datos de almacén de Administración Central.  |
|Servidores front-end  |Skype para servicio Business Server front-end  |5060  |TCP  |Opcionalmente lo usan los servidores Standard Edition y front-end para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.  |
|Servidores front-end  |Skype para servicio Business Server front-end  |5061  | TCP (TLS) |Lo usan los servidores Standard Edition y los grupos de servidores front-end para todas las comunicaciones SIP internas entre los servidores (MTLS), para las comunicaciones SIP entre el cliente y el servidor (TLS) y para las comunicaciones SIP entre los servidores front-end y los servidores de mediación (MTLS). También se usa para las comunicaciones con un servidor de supervisión.  |
| Servidores front-end |Skype para servicio Business Server front-end  |444  | HTTPS <br/> TCP  |Se usa para las comunicaciones HTTPS entre el foco (Skype para el componente de Business Server que administra el estado de la conferencia) y los servidores individuales.  <br/> Este puerto también se utiliza para las comunicaciones TCP entre aplicaciones de sucursal con funciones de supervivencia y servidores Front-End.  |
|Servidores front-end  |Skype para servicio Business Server front-end  |135  |DCOM y llamada a procedimiento remoto (RPC)  |Se usa para operaciones basadas en DCOM, como la migración de los usuarios, la sincronización del replicador de usuarios y la sincronización de la libreta de direcciones.  |
|Servidores front-end  |Skype para el servicio de conferencia de mensajería instantánea de servidor empresarial  |5062  |TCP  |Se usa para las solicitudes SIP entrantes de las conferencias de mensajería instantánea.  |
|Servidores front-end  |Skype para el servicio de conferencia Web de Business Server  |8057  |TCP (TLS)  |Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.  |
|Servidores front-end  |Skype para el servicio de compatibilidad de conferencia Web Business Server  |8058  |TCP (TLS)  |Se usa para escuchar las conexiones del modelo de objetos de compartidos persistente (PSOM) desde el cliente de Live Meeting y versiones anteriores de Skype para Business Server.  |
|Servidores front-end  |Skype para el servicio de conferencia de Audio y vídeo de servidor empresarial  |5063  |TCP  |Se usa para las solicitudes SIP entrantes de las conferencias de audio y vídeo (A/V).  |
|Servidores front-end  |Skype para el servicio de conferencia de Audio y vídeo de servidor empresarial  |57501-65535  |TCP/UDP  |Intervalo de puertos de medios que se usa para conferencias de vídeo.  |
|Servidores front-end  |Skype para el servicio de compatibilidad de negocio servidor Web  |80  |HTTP  |Se usa para la comunicación entre los servidores front-end y los FQDN (direcciones URL que usan los componentes web de IIS) cuando no se usa HTTPS.  |
|Servidores front-end  |Skype para el servicio de compatibilidad de negocio servidor Web  |443  |HTTPS  |Se usa para la comunicación entre los servidores front-end y los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS).  |
|Servidores front-end  |Skype para el servicio de compatibilidad de negocio servidor Web  |8080  |TCP y HTTP  |Lo usan los componentes web para acceso externo.  |
|Servidores front-end  |Componente de servidor web  |4443  |HTTPS  |Comunicaciones entre grupos de HTTPS (desde proxy inverso) y HTTPS front-end para el inicio de sesión con detección automática.  |
|Servidores front-end  |Componente de servidor web  |8060  |TCP (MTLS)  ||
|Servidores front-end  |Componente de servidor web  |8061  |TCP (MTLS)  ||
|Servidores front-end  |Componente de servicios de movilidad  |5086  |TCP (MTLS)  |Puerto SIP que usan los procesos internos de los servicios de movilidad  |
|Servidores front-end  |Componente de servicios de movilidad  |5087  |TCP (MTLS)  |Puerto SIP que usan los procesos internos de los servicios de movilidad  |
|Servidores front-end  |Componente de servicios de movilidad  |443  |HTTPS  ||
|Servidores front-end  |Skype para el servicio de operador de conferencia del servidor empresarial (telefónico)  |5064  |TCP  |Se usa para las solicitudes SIP entrantes de las conferencias de acceso telefónico local.  |
|Servidores front-end  |Skype para el servicio de operador de conferencia del servidor empresarial (telefónico)  |5072  |TCP  |Se utiliza para las solicitudes SIP entrantes operador (conferencia de acceso telefónico).  |
|Servidores front-end que también ejecutan un servidor de mediación combinado  |Skype para servicio de mediación de servidor empresarial  |5070  |TCP  |Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end al servidor de mediación.  |
|Servidores front-end que también ejecutan un servidor de mediación combinado  |Skype para servicio de mediación de servidor empresarial  |5067  |TCP (TLS)  |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.  |
|Servidores front-end que también ejecutan un servidor de mediación combinado  |Skype para servicio de mediación de servidor empresarial  |5068  |TCP  |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.  |
|Servidores front-end que también ejecutan un servidor de mediación combinado  |Skype para servicio de mediación de servidor empresarial  |5081  |TCP  |Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.  |
|Servidores front-end que también ejecutan un servidor de mediación combinado  |Skype para servicio de mediación de servidor empresarial  |5082  |TCP (TLS)  |Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.  |
|Servidores front-end  |Skype para uso compartido de Business Server aplicaciones de servicio  |5065  |TCP  |Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.  |
|Servidores front-end  |Skype para uso compartido de Business Server aplicaciones de servicio  |49152-65535  |TCP  |Intervalo de puertos de medios que se usa para compartir aplicaciones.  |
|Servidores front-end  |Skype para servicio de anuncio de conferencia del servidor empresarial  |5073  |TCP  |Se utiliza para las solicitudes SIP entrantes de la Skype para servicio de anuncio de conferencia del servidor empresarial (es decir, para conferencias de acceso telefónico).  |
|Servidores front-end  |Skype para servicio de estacionamiento de llamadas de servidor empresarial  |5075  |TCP  |Se usa para las solicitudes SIP entrantes de la aplicación Estacionamiento de llamadas.  |
|Servidores front-end  |Skype para el servicio de prueba de Audio de servidor empresarial  |5076  |TCP  |Se usa para las solicitudes SIP entrantes del servicio de prueba de audio.  |
|Servidores front-end  |No aplicable  |5066  |TCP  |Se usa para la puerta de enlace 9-1-1 mejorado (E9-1-1) saliente.  |
|Servidores front-end  |Skype para el servicio de grupo de respuesta de servidor empresarial  |5071  |TCP  |Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.  |
|Servidores front-end  |Skype para el servicio de grupo de respuesta de servidor empresarial  |8404  |TCP (MTLS)  |Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.  |
|Servidores front-end  |Skype para servicio de directiva de ancho de banda de servidor empresarial  |5080  |TCP  |Lo usa el servicio de directiva de ancho de banda del tráfico TURN perimetral A/V para el servicio de control de admisión de llamadas.  |
|Servidores front-end  |Skype para el acceso de recurso compartido de archivos de servidor de Business server  |445   |SMB/TCP  | Se usa para recuperar la libreta de direcciones, contenido de reuniones y otros elementos almacenados en el servidor del recurso compartido de archivos.  |
|Servidores front-end  |Skype para servicio de directiva de ancho de banda de servidor empresarial  |448  |TCP  |Se utiliza para el control de admisión de llamadas por el Skype servicio de directiva de ancho de banda de servidor empresarial.  |
|Front-End los servidores en el que reside el almacén de Administración Central  | Skype para el servicio de agente de Replicador maestro de servidor empresarial |445  |TCP  |Se usa para enviar datos de configuración desde el almacén de Administración Central para los servidores que ejecutan Skype para Business Server.  |
|Todos los servidores  |Explorador SQL  |1434  |UDP  |Explorador SQL para la copia replicada local de la Administración Central de almacenar datos en la instancia local de SQL Server  |
|Todos los usuarios internos  |Varios  |49152-57500  |TCP/UDP  |El intervalo de puertos de medios se usa para audioconferencias en todos los servidores internos. Utilizado por todos los servidores que terminar audio: servidores Front-End (para Skype para el servicio de operador de conferencia del servidor empresarial, Skype para servicio de anuncio de conferencia del servidor empresarial y Skype para el servicio de conferencia de Audio y vídeo de servidor empresarial), y Servidor de mediación.  |
|Servidores de Office Web Apps  ||443  ||Usa Skype para Business Server para conectarse a Office Web Apps Server.  |
|Directores  |Skype para servicio Business Server front-end  |5060  |TCP  |Se usa opcionalmente para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.  |
|Directores  |Skype para servicio Business Server front-end  |444  |HTTPS  <br/> TCP  |Comunicación entre servidores front-end y Director. Además, el certificado de cliente publicar (en servidores Front-End) o validar si ya se ha publicado el certificado de cliente.  |
|Directores  |Skype para el servicio de compatibilidad de negocio servidor Web  |80  |TCP  |Se usa para la comunicación inicial desde los Directores a los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS). En condiciones normales, cambiará a tráfico HTTPS a través del puerto 443 y el tipo de protocolo TCP.  |
|Directores  |Skype para el servicio de compatibilidad de negocio servidor Web  |443  |HTTPS  |Se usa para la comunicación desde los Directores a los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS).  |
|Directores  |Skype para servicio Business Server front-end  |5061  |TCP  |Se usa para comunicaciones internas entre servidores y para conexiones de cliente.  |
|Servidores de mediación  |Skype para servicio de mediación de servidor empresarial  |5070  |TCP  |Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end.  |
|Servidores de mediación  |Skype para servicio de mediación de servidor empresarial  |5067  |TCP (TLS)  |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.  |
|Servidores de mediación  |Skype para servicio de mediación de servidor empresarial  |5068  |TCP  |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.  |
|Servidores de mediación  |Skype para servicio de mediación de servidor empresarial  |5070  |TCP (MTLS)  |Se usa para solicitudes SIP desde los servidores front-end.  |
|Servidor front-end de chat persistente  |SIP de chat persistente  |5041  |TCP (MTLS)  ||
|Servidor front-end de chat persistente  |Windows Communication Foundation (WCF) de chat persistente  |881  |TCP (TLS) y TCP (MTLS)  ||
|Servidor front-end de chat persistente  |Servicio de transferencia de archivos de chat persistente  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Algunos escenarios de control remoto de llamadas requieren una conexión entre el servidor front-end o el Director y la PBX. Aunque Skype para Business Server ya no usa el puerto TCP 5060, durante la implementación de control remoto de llamadas se crea una configuración de servidor de confianza, que se asocia el FQDN del servidor de línea de control remoto de llamadas con el puerto TCP que el servidor Front-End o un Director que va a usar para conectarse a la Sistema PBX. Para obtener información detallada, vea el cmdlet **CsTrustedApplicationComputer** en el Skype para la documentación del Shell de administración de servidor empresarial.
  
Para los grupos que solo usan equilibrio de carga de hardware (no equilibrio de carga de DNS), en la siguiente tabla se muestran los puertos que necesitan para abrir los equilibradores de carga de hardware.
  
**Puertos del equilibrador de carga de hardware si solo usa equilibrio de carga de hardware**

|Equilibrador de carga|Puerto|Protocolo|
|:-----|:-----|:-----|
|Equilibrador de carga del servidor front-end  |5061  |TCP (TLS)  |
|Equilibrador de carga del servidor front-end  |444  |HTTPS  |
|Equilibrador de carga del servidor front-end  |135  |DCOM y llamada a procedimiento remoto (RPC)  |
|Equilibrador de carga del servidor front-end  |80  |HTTP  |
|Equilibrador de carga del servidor front-end  |8080  |TCP - recuperación cliente y dispositivo del certificado raíz de servidor Front-End - clientes y dispositivos autenticados por NTLM  |
|Equilibrador de carga del servidor front-end  |443  |HTTPS  |
|Equilibrador de carga del servidor front-end  |4443  |HTTPS (desde proxy inverso)  |
|Equilibrador de carga del servidor front-end  |5072  |TCP  |
|Equilibrador de carga del servidor front-end  |5073  |TCP  |
|Equilibrador de carga del servidor front-end  |5075  |TCP  |
|Equilibrador de carga del servidor front-end  |5076  |TCP  |
|Equilibrador de carga del servidor front-end  |5071  |TCP  |
|Equilibrador de carga del servidor front-end  |5080  |TCP  |
|Equilibrador de carga del servidor front-end  |448  |TCP  |
|Equilibrador de carga del servidor de mediación  |5070  |TCP  |
|Equilibrador de carga del servidor front-end (si el grupo también ejecuta el servidor de mediación)  |5070  |TCP  |
|Equilibrador de carga del Director  |443  |HTTPS  |
|Equilibrador de carga del Director  |444  |HTTPS  |
|Equilibrador de carga del Director  |5061  |TCP  |
|Equilibrador de carga del Director  |4443  |HTTPS (desde proxy inverso)  |
   
Los grupos de servidores front-end y de Directores que usan equilibrio de carga de DNS también deben tener implementado un equilibrador de carga de hardware. En la siguiente tabla se muestran los puertos que se deben abrir en estos equilibradores de carga de hardware.
  
**Puertos del equilibrador de carga de hardware si usa equilibrio de carga de DNS**

|Equilibrador de carga|Puerto|Protocolo|
|:-----|:-----|:-----|
|Equilibrador de carga del servidor front-end  |80  |HTTP  |
|Equilibrador de carga del servidor front-end  |443  |HTTPS  |
|Equilibrador de carga del servidor front-end  |8080  |TCP - recuperación cliente y dispositivo del certificado raíz de servidor Front-End - clientes y dispositivos autenticados por NTLM  |
|Equilibrador de carga del servidor front-end  |4443  |HTTPS (desde proxy inverso)  |
|Equilibrador de carga del Director  |443  |HTTPS  |
|Equilibrador de carga del Director  |4443  |HTTPS (desde proxy inverso)  |

**Puertos de cliente necesarios**

|Componente|Puerto|Protocolo|Notas|
|:-----|:-----|:-----|:-----|
|Clientes  |67/68  |DHCP  |Skype para Business Server lo usa para encontrar el FQDN del registrador (es decir, si se produce un error de SRV de DNS y las opciones manuales no están configuradas).  |
|Clientes  |443  |TCP (TLS)  |Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.  |
|Clientes  |443  |TCP (PSOM/TLS)  |Se usa para el acceso de usuarios externos a las sesiones de conferencia web.  |
|Clientes  |443  |TCP (STUN/MSTURN)  |Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP).  |
|Clientes  |3478  |UDP (STUN/MSTURN)  |Se usa para el acceso de usuarios externos a los medios y las sesiones de A/V (UDP)  |
|Clientes  |5061  |TCP (MTLS)  |Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.  |
|Clientes  |6891-6901  |TCP  |Se usa para la transferencia de archivos entre Skype para clientes empresariales y clientes anteriores.  |
|Clientes  |1024-65535\*  |TCP/UDP  |Intervalo de puertos de audio (se requieren 20 puertos como mínimo).  |
|Clientes  |1024-65535\*  |TCP/UDP  |Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo).  |
|Clientes  |1024-65535\*  |TCP  |Transferencias de archivos de punto a punto (para la transferencia de archivos de conferencia, los clientes usan PSOM).  |
|Clientes  |1024-65535\*  |TCP  |Uso compartido de aplicaciones.  |
|Teléfono de área común Aastra 6721ip  <br/> Teléfono de escritorio Aastra 6725ip  <br/> Teléfono IP HP 4110 (teléfono de área común)  <br/> Teléfono IP HP 4120 (teléfono de escritorio)  <br/> Teléfono de área común Polycom CX500 IP  <br/> Teléfono de escritorio Polycom CX600 IP  <br/> Teléfono de escritorio Polycom CX700 IP  <br/> Teléfono de conferencia Polycom CX3000 IP  |67/68  |DHCP  |Los dispositivos enumerados lo usan para encontrar el Skype para el certificado de servidor empresarial, FQDN aprovisionamiento y FQDN del registrador.  |
   
\*Para configurar puertos específicos para estos tipos de medios, use el cmdlet CsConferencingConfiguration (los parámetros ClientMediaPortRangeEnabled, ClientMediaPort y ClientMediaPortRange).
  
> [!NOTE]
> Los programas de instalación de Skype para clientes empresariales crean automáticamente las excepciones de firewall del sistema operativo en el equipo cliente. 

> [!NOTE]
> Los puertos que se usan para el acceso de usuarios externos son necesarios para cualquier escenario en el que el cliente debe atravesar firewall de la organización (por ejemplo, las comunicaciones externas o reuniones hospedadas por otras organizaciones). 
  
## <a name="ipsec-exceptions"></a>Excepciones de IPsec

En aquellas redes empresariales donde el protocolo de seguridad de Internet (IPsec) (consulte IETF RFC 4301-4309) está implementado, IPsec se necesita deshabilitar en el intervalo de puertos usado para la entrega de audio, vídeo y vídeo panorámico. Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios por la negociación de IPsec.
  
En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas. 
  
**Excepciones de IPsec recomendadas**

|Nombre de regla|IP de origen|IP de destino|Protocolo|Puerto de origen|Puerto de destino|Requisito de autenticación|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|Servidor perimetral A/V interno entrante  |Cualquiera  |Servidor perimetral A/V interno  |UDP y TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Servidor perimetral A/V externo entrante  |Cualquiera  |Servidor perimetral A/V externo  |UDP y TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Servidor perimetral A/V interno saliente  |Servidor perimetral A/V interno  |Cualquiera  |UDP &amp; TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Servidor perimetral A/V externo saliente  |Servidor perimetral A/V externo  |Cualquiera  |UDP y TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Servidor de mediación entrante  |Cualquiera  |Servidores  <br/> de mediación  |UDP y TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Servidor de mediación saliente  |Servidores  <br/> de mediación  |Cualquiera  |UDP y TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Operador de conferencia entrante  |Cualquiera  |Servidor front-end que ejecuta operador de conferencia  |UDP y TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Operador de conferencia saliente  |Servidor front-end que ejecuta operador de conferencia  |Cualquiera  |UDP y TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Servidor de conferencia A/V entrante  |Cualquiera  |Servidores front-end  |UDP y TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Salida de conferencia A/V  |Servidores front-end  |Cualquiera  |UDP y TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Exchange entrante  |Cualquiera  |Mensajería unificada de Exchange  |UDP y TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Servidores de aplicaciones compartidas entrantes  |Cualquiera  |Servidores de aplicaciones compartidas  |TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Servidor de aplicaciones compartidas saliente  |Servidores de aplicaciones compartidas  |Cualquiera  |TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Exchange saliente  |Mensajería unificada de Exchange  |Cualquiera  |UDP y TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Clientes  |Cualquiera   |Cualquiera  |UDP  |Intervalo de puertos de medios especificado  |Cualquiera  |No autenticar  |