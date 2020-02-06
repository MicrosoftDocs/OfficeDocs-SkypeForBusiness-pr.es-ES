---
title: Requisitos de puertos y protocolos para servidores
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c94063f1-e802-4a61-be90-022fc185335e
description: 'Resumen: Revise las consideraciones de uso de puertos antes de implementar Skype empresarial Server.'
ms.openlocfilehash: ca790f2ca4ff1504ab4851fedfbba086e251d91a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802020"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Requisitos de puertos y protocolos para servidores
 
**Resumen:** Revise las consideraciones de uso de puertos antes de implementar Skype empresarial Server.
  
Skype empresarial Server requiere que los puertos específicos de los firewalls externos e internos estén abiertos. Además, si se ha implementado el protocolo de seguridad de Internet (IPSec) en la organización, IPSec debe estar deshabilitado en el intervalo de puertos que se usa para la entrega de audio, vídeo y vídeo panorámico. 
  
A pesar de que esto puede parecer complicado, el trabajo pesado para planear esto puede hacerse con la [herramienta de planificación de Skype empresarial Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725). Una vez que haya finalizado las preguntas del asistente sobre las características que planea usar, para cada sitio que defina, puede ver el informe de Firewall dentro del informe de administración perimetral y usar la información que se muestra aquí para crear reglas de yourfirewall. También puede realizar ajustes en muchos de los nombres y direcciones IP usados, para obtener detalles, consulte [revisar el informe de Firewall](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Tenga en cuenta que puede exportar el informe de administración perimetral a una hoja de cálculo de Excel y el informe de Firewall será una de las hojas de cálculo del archivo. 
  
También puede encontrar la información de estas tablas en forma de diagrama revisando el póster de cargas de trabajo de protocolo vinculado de los [diagramas técnicos para el artículo de Skype empresarial Server 2015](../../technical-diagrams.md) .
> [!NOTE]
> - Si va a implementar Skype empresarial online (O365), consulte [Office 365 URL e intervalos de direcciones IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). Los entornos híbridos deberán hacer referencia a este tema y también [planear la conectividad híbrida](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
> - Puede tener servidores de seguridad de hardware o software, no requieran versiones o modelos específicos. Lo que importa es qué puertos están en la lista blanca para que el Firewall no perjudique el funcionamiento de Skype empresarial Server.
  
## <a name="port-and-protocol-details"></a>Detalles de protocolo y puerto

En esta sección se resumen los puertos y protocolos usados por servidores, equilibradores de carga y clientes en una implementación de Skype empresarial Server.
  
> [!NOTE]
> Cuando se inicia Skype empresarial Server, se abren los puertos necesarios en el Firewall de Windows. Firewall de Windows ya debe estar ejecutándose en la mayoría de las aplicaciones normales, pero si no se usa, Skype empresarial Server funcionará sin él. 
  
Para obtener más información sobre la configuración del firewall para los componentes de Edge, consulte [escenarios de servidores perimetrales en Skype empresarial server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
En la tabla siguiente se enumeran los puertos que debe abrir en cada rol del servidor interno. 
  
**Puertos de servidor obligatorios (por rol de servidor)**

|Rol de servidor|Nombre de servicio|Puerto|Protocolo|Notas|
|:-----|:-----|:-----|:-----|:-----|
|Todos los servidores  |Explorador SQL  |1434  |UDP  |Explorador SQL para la copia replicada local de la base de datos del almacén central de administración.  |
|Servidores front-end  |Servicio front-end de Skype empresarial Server  |5060  |TCP  |Opcionalmente lo usan los servidores Standard Edition y front-end para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.  |
|Servidores front-end  |Servicio front-end de Skype empresarial Server  |5061  | TCP (TLS) |Lo usan los servidores Standard Edition y los grupos de servidores front-end para todas las comunicaciones SIP internas entre los servidores (MTLS), para las comunicaciones SIP entre el cliente y el servidor (TLS) y para las comunicaciones SIP entre los servidores front-end y los servidores de mediación (MTLS). También se usa para las comunicaciones con un servidor de supervisión.  |
| Servidores front-end |Servicio front-end de Skype empresarial Server  |444  | HTTPS <br/> TCP  |Se usa para la comunicación HTTPS entre el foco (el componente de Skype empresarial Server que administra el estado de la Conferencia) y los servidores individuales.  <br/> Este puerto también se usa para la comunicación TCP entre los equipos de las sucursales y los servidores de aplicaciones para el usuario.  |
|Servidores front-end  |Servicio front-end de Skype empresarial Server  |135  |DCOM y llamada a procedimiento remoto (RPC)  |Se usa para operaciones basadas en DCOM, como la migración de los usuarios, la sincronización del replicador de usuarios y la sincronización de la libreta de direcciones.  |
|Servidores front-end  |Servicio de conferencia de mensajería instantánea de Skype empresarial Server  |5062  |TCP  |Se usa para las solicitudes SIP entrantes de las conferencias de mensajería instantánea.  |
|Servidores front-end  |Servicio de conferencias por Internet de Skype empresarial Server  |8057  |TCP (TLS)  |Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.  |
|Servidores front-end  |Servicio de compatibilidad con conferencias web de Skype empresarial Server  |8058  |TCP (TLS)  |Se usa para escuchar conexiones persistentes del modelo de objetos compartidos (PSOM) del cliente de Live Meeting y de las versiones anteriores de Skype empresarial Server.  |
|Servidores front-end  |Servicio de videoconferencias de audio y videollamadas de Skype empresarial Server  |5063  |TCP  |Se usa para las solicitudes SIP entrantes de las conferencias de audio y vídeo (A/V).  |
|Servidores front-end  |Servicio de videoconferencias de audio y videollamadas de Skype empresarial Server  |57501-65535  |TCP/UDP  |Intervalo de puertos de medios que se usa para conferencias de vídeo.  |
|Servidores front-end  |Servicio de compatibilidad Web de Skype empresarial Server  |80  |HTTP  |Se usa para la comunicación entre los servidores front-end y los FQDN (direcciones URL que usan los componentes web de IIS) cuando no se usa HTTPS.  |
|Servidores front-end  |Servicio de compatibilidad Web de Skype empresarial Server  |443  |HTTPS  |Se usa para la comunicación entre los servidores front-end y los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS).  |
|Servidores front-end  |Servicio de compatibilidad Web de Skype empresarial Server  |8080  |TCP y HTTP  |Lo usan los componentes web para acceso externo.  |
|Servidores front-end  |Componente de servidor web  |4443  |HTTPS  |Comunicaciones entre grupos de HTTPS (desde proxy inverso) y HTTPS front-end para el inicio de sesión con detección automática.  |
|Servidores front-end  |Componente de servidor web  |8060  |TCP (MTLS)  ||
|Servidores front-end  |Componente de servidor web  |8061  |TCP (MTLS)  ||
|Servidores front-end  |Componente de servicios de movilidad  |5086  |TCP (MTLS)  |Puerto SIP que usan los procesos internos de los servicios de movilidad  |
|Servidores front-end  |Componente de servicios de movilidad  |5087  |TCP (MTLS)  |Puerto SIP que usan los procesos internos de los servicios de movilidad  |
|Servidores front-end  |Componente de servicios de movilidad  |443  |HTTPS  ||
|Servidores front-end  |Servicio del operador de conferencias de Skype empresarial Server (Conferencia de acceso telefónico local)  |5064  |TCP  |Se usa para las solicitudes SIP entrantes de las conferencias de acceso telefónico local.  |
|Servidores front-end  |Servicio del operador de conferencias de Skype empresarial Server (Conferencia de acceso telefónico local)  |5072  |TCP  |Se usa para las solicitudes SIP entrantes para operadores (llamar en conferencia).  |
|Servidores front-end que también ejecutan un servidor de mediación combinado  |Servicio de mediación de Skype empresarial  |5070  |TCP  |Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end al servidor de mediación.  |
|Servidores front-end que también ejecutan un servidor de mediación combinado  |Servicio de mediación de Skype empresarial  |5067  |TCP (TLS)  |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.  |
|Servidores front-end que también ejecutan un servidor de mediación combinado  |Servicio de mediación de Skype empresarial  |5068  |TCP  |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.  |
|Servidores front-end que también ejecutan un servidor de mediación combinado  |Servicio de mediación de Skype empresarial  |5081  |TCP  |Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.  |
|Servidores front-end que también ejecutan un servidor de mediación combinado  |Servicio de mediación de Skype empresarial  |5082  |TCP (TLS)  |Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.  |
|Servidores front-end  |Servicio de uso compartido de aplicaciones de Skype empresarial Server  |5065  |TCP  |Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.  |
|Servidores front-end  |Servicio de uso compartido de aplicaciones de Skype empresarial Server  |49152-65535  |TCP  |Intervalo de puertos de medios que se usa para compartir aplicaciones.  |
|Servidores front-end  |Servicio de anuncios de conferencias de Skype empresarial Server  |5073  |TCP  |Se usa para solicitudes SIP entrantes para el servicio de anuncios de conferencias de Skype empresarial Server (es decir, para conferencias de acceso telefónico local).  |
|Servidores front-end  |Servicio de estacionamiento de llamadas de Skype empresarial Server  |5075  |TCP  |Se usa para las solicitudes SIP entrantes de la aplicación Estacionamiento de llamadas.  |
|Servidores front-end  |Servicio de prueba de audio de Skype empresarial Server  |5076  |TCP  |Se usa para las solicitudes SIP entrantes del servicio de prueba de audio.  |
|Servidores front-end  |No aplicable  |5066  |TCP  |Se usa para la puerta de enlace 9-1-1 mejorado (E9-1-1) saliente.  |
|Servidores front-end  |Servicio de grupo de respuesta de Skype empresarial Server  |5071  |TCP  |Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.  |
|Servidores front-end  |Servicio de grupo de respuesta de Skype empresarial Server  |8404  |TCP (MTLS)  |Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.  |
|Servidores front-end  |Servicio de directivas de ancho de banda de Skype empresarial Server  |5080  |TCP  |Lo usa el servicio de directiva de ancho de banda del tráfico TURN perimetral A/V para el servicio de control de admisión de llamadas.  |
|Servidores front-end  |Acceso a servidor compartido de archivos de Skype empresarial Server  |445   |SMB/TCP  | Se usa para recuperar la libreta de direcciones, el contenido de la reunión y otros elementos almacenados en el servidor de uso compartido de archivos.  |
|Servidores front-end  |Servicio de directivas de ancho de banda de Skype empresarial Server  |448  |TCP  |Usado por el servicio de directivas de ancho de banda de Skype empresarial Server.  |
|Servidores front-end en los que reside el almacén de administración central  | Servicio agente de replicación maestra de Skype empresarial Server |445  |TCP  |Se usa para insertar datos de configuración desde el almacén de administración central en servidores que ejecuten Skype empresarial Server.  |
|Todos los servidores  |Explorador SQL  |1434  |UDP  |Explorador SQL para la copia replicada local de los datos del almacén central de administración en la instancia local de SQL Server  |
|Todos los usuarios internos  |Varios  |49152-57500  |TCP/UDP  |El intervalo de puertos de medios se usa para audioconferencias en todos los servidores internos. Usado por todos los servidores que terminan audio: servidores front-end (para el servicio del operador de conferencias de Skype empresarial Server, servicio de anuncios de conferencias de Skype empresarial Server y el servidor de mediación de audio o videoconferencia de Skype empresarial Server).  |
|Servidores de Office Web Apps  ||443  ||Usado por Skype empresarial Server para conectarse a Office Web Apps Server.  |
|Directores  |Servicio front-end de Skype empresarial Server  |5060  |TCP  |Se usa opcionalmente para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.  |
|Directores  |Servicio front-end de Skype empresarial Server  |444  |HTTPS  <br/> TCP  |Comunicación entre servidores front-end y Director. Además, la publicación de certificados de cliente (a servidores de aplicaciones para el usuario) o la validación si el certificado de cliente ya se ha publicado.  |
|Directores  |Servicio de compatibilidad Web de Skype empresarial Server  |80  |TCP  |Se usa para la comunicación inicial desde los Directores a los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS). En condiciones normales, cambiará a tráfico HTTPS a través del puerto 443 y el tipo de protocolo TCP.  |
|Directores  |Servicio de compatibilidad Web de Skype empresarial Server  |443  |HTTPS  |Se usa para la comunicación desde los Directores a los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS).  |
|Directores  |Servicio front-end de Skype empresarial Server  |5061  |TCP  |Se usa para comunicaciones internas entre servidores y para conexiones de cliente.  |
|Servidores de mediación  |Servicio de mediación de Skype empresarial  |5070  |TCP  |Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end.  |
|Servidores de mediación  |Servicio de mediación de Skype empresarial  |5067  |TCP (TLS)  |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.  |
|Servidores de mediación  |Servicio de mediación de Skype empresarial  |5068  |TCP  |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.  |
|Servidores de mediación  |Servicio de mediación de Skype empresarial  |5070  |TCP (MTLS)  |Se usa para solicitudes SIP desde los servidores front-end.  |
|Servidor front-end de chat persistente  |SIP de chat persistente  |5041  |TCP (MTLS)  ||
|Servidor front-end de chat persistente  |Windows Communication Foundation (WCF) de chat persistente  |881  |TCP (TLS) y TCP (MTLS)  ||
|Servidor front-end de chat persistente  |Servicio de transferencia de archivos de chat persistente  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Algunos escenarios de control remoto de llamadas requieren una conexión entre el servidor front-end o el Director y la PBX. Aunque Skype empresarial Server ya no usa el puerto TCP 5060, durante la implementación de control remoto de llamadas, usted crea una configuración de servidor de confianza, que asocia el FQDN del servidor de línea RCC con el puerto TCP que usará el servidor o el director front-end para conectarse al Sistema PBX. Para obtener más información, consulte el cmdlet **CsTrustedApplicationComputer** en la documentación del shell de administración de Skype empresarial Server.
  
Para los grupos que solo usan equilibrio de carga de hardware (no equilibrio de carga de DNS), en la siguiente tabla se muestran los puertos que necesitan para abrir los equilibradores de carga de hardware.
  
**Puertos del equilibrador de carga de hardware si solo usa equilibrio de carga de hardware**

|Equilibrador de carga|Puerto|Protocolo|
|:-----|:-----|:-----|
|Equilibrador de carga del servidor front-end  |5061  |TCP (TLS)  |
|Equilibrador de carga del servidor front-end  |444  |HTTPS  |
|Equilibrador de carga del servidor front-end  |135  |DCOM y llamada a procedimiento remoto (RPC)  |
|Equilibrador de carga del servidor front-end  |80  |HTTP  |
|Equilibrador de carga del servidor front-end  |8080  |TCP: recuperación de dispositivos y clientes del certificado raíz desde el servidor front-end-clientes y dispositivos autenticados por NTLM  |
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
|Equilibrador de carga del servidor front-end  |8080  |TCP: recuperación de dispositivos y clientes del certificado raíz desde el servidor front-end-clientes y dispositivos autenticados por NTLM  |
|Equilibrador de carga del servidor front-end  |4443  |HTTPS (desde proxy inverso)  |
|Equilibrador de carga del Director  |443  |HTTPS  |
|Equilibrador de carga del Director  |4443  |HTTPS (desde proxy inverso)  |

**Puertos de cliente necesarios**

|Componente|Puerto|Protocolo|Notas|
|:-----|:-----|:-----|:-----|
|Clientes  |67/68  |DHCP  |Utilizado por Skype empresarial Server para buscar el FQDN de la entidad registradora (es decir, si no se puede establecer el SRV de DNS y la configuración manual no).  |
|Clientes  |443  |TCP (TLS)  |Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.  |
|Clientes  |443  |TCP (PSOM/TLS)  |Se usa para el acceso de usuarios externos a las sesiones de conferencia web.  |
|Clientes  |443  |TCP (STUN/MSTURN)  |Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP).  |
|Clientes  |3478  |UDP (STUN/MSTURN)  |Se usa para el acceso de usuarios externos a los medios y las sesiones de A/V (UDP)  |
|Clientes  |5061  |TCP (MTLS)  |Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.  |
|Clientes  |6891-6901  |TCP  |Se usa para la transferencia de archivos entre clientes de Skype empresarial y clientes anteriores.  |
|Clientes  |1024-65535\*  |TCP/UDP  |Intervalo de puertos de audio (se requieren 20 puertos como mínimo).  |
|Clientes  |1024-65535\*  |TCP/UDP  |Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo).  |
|Clientes  |1024-65535\*  |TCP  |Transferencias de archivos de punto a punto (para la transferencia de archivos de conferencia, los clientes usan PSOM).  |
|Clientes  |1024-65535\*  |TCP  |Uso compartido de aplicaciones.  |
|Teléfono de área común Aastra 6721ip  <br/> Teléfono de escritorio Aastra 6725ip  <br/> Teléfono IP HP 4110 (teléfono de área común)  <br/> Teléfono IP HP 4120 (teléfono de escritorio)  <br/> Teléfono de área común Polycom CX500 IP  <br/> Teléfono de escritorio Polycom CX600 IP  <br/> Teléfono de escritorio Polycom CX700 IP  <br/> Teléfono de conferencia Polycom CX3000 IP  |67/68  |DHCP  |Usado por los dispositivos de la lista para buscar el certificado de Skype empresarial Server, el FQDN de aprovisionamiento y el FQDN del registrador.  |
   
\*Para configurar puertos específicos para estos tipos de medios, use el cmdlet CsConferencingConfiguration (ClientMediaPortRangeEnabled, ClientMediaPort y ClientMediaPortRange parámetros).
  
> [!NOTE]
> Los programas de configuración de los clientes de Skype empresarial crean automáticamente las excepciones de firewall del sistema operativo necesarias en el equipo cliente. 

> [!NOTE]
> Los puertos que se usan para el acceso de usuarios externos son necesarios para cualquier escenario en el que el cliente deba atravesar el Firewall de la organización (por ejemplo, cualquier comunicación o reunión externa hospedada por otras organizaciones). 
  
## <a name="ipsec-exceptions"></a>Excepciones de IPsec

En aquellas redes empresariales donde el protocolo de seguridad de Internet (IPsec) (consulte IETF RFC 4301-4309) está implementado, IPsec se necesita deshabilitar en el intervalo de puertos usado para la entrega de audio, vídeo y vídeo panorámico. Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios por la negociación de IPsec.
  
En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas. 
  
**Excepciones de IPsec recomendadas**

|Nombre de regla|IP de origen|IP de destino|Protocolo|Puerto de origen|Puerto de destino|Requisito de autenticación|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|Servidor perimetral A/V interno entrante  |Cualquiera  |Servidor perimetral A/V interno  |UDP y TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Servidor perimetral A/V externo entrante  |Cualquiera  |Servidor perimetral A/V externo  |UDP y TCP  |Cualquiera   |Cualquiera  |No autenticar  |
|Servidor perimetral A/V interno saliente  |Servidor perimetral A/V interno  |Cualquiera  |TCP &amp; UDP  |Cualquiera   |Cualquiera  |No autenticar  |
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
