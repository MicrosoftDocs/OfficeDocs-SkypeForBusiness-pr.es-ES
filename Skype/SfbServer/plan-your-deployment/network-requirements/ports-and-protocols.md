---
title: Requisitos de puerto y protocolo para servidores
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: revise las consideraciones de uso del puerto antes de implementar Skype Empresarial Server.'
ms.openlocfilehash: d2e3cf07dbdf7471cd1e2f535d619e8bece74ecc0a9f9e16d416b7cba46548c1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352628"
---
# <a name="port-and-protocol-requirements-for-servers"></a>Requisitos de puerto y protocolo para servidores
 
**Resumen:** Revise las consideraciones de uso del puerto antes de implementar Skype Empresarial Server.
  
Skype Empresarial Server requiere que los puertos específicos de los firewalls externos e internos estén abiertos. Además, si se ha implementado el protocolo de seguridad de Internet (IPSec) en la organización, IPSec debe estar deshabilitado en el intervalo de puertos usado para la entrega de audio, vídeo y vídeo panorámico. 
  
Aunque esto puede parecer un poco desalentador, el trabajo pesado para planear esto se puede realizar con la herramienta de planeación [Skype Empresarial Server 2015](https://go.microsoft.com/fwlink/p/?LinkID=282725). Una vez que haya pasado por las preguntas del asistente acerca de las características que tiene previsto usar, para cada sitio que defina puede ver el informe de firewall en el informe de administración perimetral y usar la información que aparece allí para crear las reglas de firewall. También puede realizar ajustes en muchos de los nombres y direcciones IP usados, para obtener más información, vea [Review the Firewall Report](../../management-tools/planning-tool/review-the-administrator-reports.md#Firewall_report). Tenga en cuenta que puede exportar el informe de administración perimetral a una hoja de cálculo Excel y el informe de firewall será una de las hojas de cálculo del archivo. 
  
Encontrará la información en estas tablas en forma de diagrama revisando el póster Cargas de trabajo de protocolo vinculado fuera del artículo Diagramas técnicos [para Skype Empresarial Server 2015.](../../technical-diagrams.md)

> [!NOTE]
> - Si va a implementar Skype Empresarial Online (Microsoft 365 o Office 365) consulte Microsoft 365 y Office 365 direcciones URL e [intervalos de direcciones IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US). Los entornos híbridos tendrán que hacer referencia a este tema y también [planear la conectividad híbrida.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2floc.json&toc=%2fSkypeForBusiness%2ftoc.json)
> - Puede tener firewall de hardware o software. No necesitamos modelos o versiones específicos. Lo importante es qué puertos se agregan a una lista de permitidos para que el firewall no perda el funcionamiento de Skype Empresarial Server.
  
## <a name="port-and-protocol-details"></a>Detalles de puerto y protocolo

En esta sección se resumen los puertos y protocolos usados por servidores, equilibradores de carga y clientes en una Skype Empresarial Server implementación.
  
> [!NOTE]
> Cuando Skype Empresarial Server, se abren los puertos necesarios en el firewall Windows. Windows El firewall ya debería estar ejecutándose en la mayoría de las aplicaciones normales, pero si no se usa, Skype Empresarial Server funcionará sin él. 
  
Para obtener información detallada acerca de la configuración del firewall para componentes perimetrales, vea Escenarios del servidor perimetral [en Skype Empresarial Server 2015](../../plan-your-deployment/edge-server-deployments/scenarios.md). 
  
En la tabla siguiente se enumeran los puertos que debe abrir en cada rol del servidor interno. 
  
**Puertos de servidor obligatorios (por rol del servidor)**

|Rol de servidor|Nombre del servicio|Puerto|Protocolo|Notas|
|:-----|:-----|:-----|:-----|:-----|
|Todos los servidores  |Explorador SQL  |1434  |UDP  |SQL Explorador de la copia replicada local de la base de datos del Almacén de administración central.  |
|Front-End servidores  |Skype Empresarial Server Front-End servicio de Skype Empresarial Server Front-End web  |5060  |TCP  |Opcionalmente lo usan los servidores Standard Edition y front-end para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.  |
|Servidores front-end  |Skype Empresarial Server Front-End servicio de Skype Empresarial Server Front-End web  |5061  | TCP (TLS) |Lo usan los servidores Standard Edition y los grupos de servidores front-end para todas la comunicaciones SIP internas entre los servidores (MTLS), para las comunicaciones SIP entre el cliente y del servidor (TLS) y para las comunicaciones entre los servidores front-end y los servidores de mediación (MTLS). También se usa para comunicaciones con un servidor de supervisión.  |
| Servidores front-end |Skype Empresarial Server Front-End servicio de Skype Empresarial Server Front-End web  |444  | HTTPS <br/> TCP  |Se usa para la comunicación HTTPS entre el foco (el Skype Empresarial Server que administra el estado de conferencia) y los servidores individuales.  <br/> Este puerto también se usa para la comunicación TCP entre los dispositivos de sucursal con funciones de supervivencia y los servidores front-end.  |
|Servidores front-end  |Skype Empresarial Server Front-End servicio de Skype Empresarial Server Front-End web  |135  |DCOM y llamada a procedimiento remoto (RPC)  |Se usa para operaciones basadas en DCOM como la migración de los usuarios, la sincronización del replicador de usuarios y la sincronización de la libreta de direcciones.  |
|Servidores front-end  |Skype Empresarial Server Servicio de conferencia de mensajería instantánea  |5062  |TCP  |Se usa para las solicitudes SIP entrantes de las conferencias de mensajería instantánea.  |
|Servidores front-end  |Skype Empresarial Server Servicio de conferencia web  |8057  |TCP (TLS)  |Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.  |
|Servidores front-end  |Skype Empresarial Server Servicio de compatibilidad de conferencia web  |8058  |TCP (TLS)  |Se usa para escuchar las conexiones del modelo de objetos compartidos persistentes (PSOM) desde el cliente de Live Meeting y las versiones anteriores de Skype Empresarial Server.  |
|Servidores front-end  |Skype Empresarial Server Servicio de conferencia de audio y vídeo  |5063  |TCP  |Se usa para las solicitudes SIP entrantes de las conferencias de audio y vídeo (A/V).  |
|Servidores front-end  |Skype Empresarial Server Servicio de conferencia de audio y vídeo  |57501-65535  |TCP/UDP  |Intervalo de puerto de medios usado para conferencias de vídeo.  |
|Servidores front-end  |Skype Empresarial Server Servicio de compatibilidad web  |80  |HTTP  |Se usa para la comunicación entre los servidores front-end y los FQDN (direcciones URL usadas por los componentes web IIS) cuando no se usa HTTPS.  |
|Servidores front-end  |Skype Empresarial Server Servicio de compatibilidad web  |443  |HTTPS  |Se usa para la comunicación entre los servidores front-end y los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS).  |
|Servidores front-end  |Skype Empresarial Server Servicio de compatibilidad web  |8080  |TCP y HTTP  |Usado por los componentes web para el acceso externo.  |
|Servidores front-end  |Componente de servidor web  |4443  |HTTPS  |HTTPS (desde proxy inverso) y comunicaciones entre servidores front-end HTTPS para el inicio de sesión de detección automática.  |
|Servidores front-end  |Componente de servidor web  |8060  |TCP (MTLS)  ||
|Servidores front-end  |Componente de servidor web  |8061  |TCP (MTLS)  ||
|Servidores front-end  |Componente de Mobility Services  |5086  |TCP (MTLS)  |Puerto SIP usado por procesos internos de Mobility Services  |
|Servidores front-end  |Componente de Mobility Services  |5087  |TCP (MTLS)  |Puerto SIP usado por procesos internos de Mobility Services  |
|Servidores front-end  |Componente de Mobility Services  |443  |HTTPS  ||
|Servidores front-end  |Skype Empresarial Server Operador de conferencia (conferencia de acceso telefónico local)  |5064  |TCP  |Se usa para las solicitudes SIP entrantes de las conferencias telefónicas.  |
|Servidores front-end  |Skype Empresarial Server Operador de conferencia (conferencia de acceso telefónico local)  |5072  |TCP  |Se usa para las solicitudes SIP entrantes para Attendant (dial in conferencing).  |
|Servidores front-end que también ejecutan un servidor de mediación instalado  |Skype Empresarial Server Servicio de mediación  |5070  |TCP  |Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end al servidor de mediación.  |
|Servidores front-end que también ejecutan un servidor de mediación instalado  |Skype Empresarial Server Servicio de mediación  |5067  |TCP (TLS)  |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.  |
|Servidores front-end que también ejecutan un servidor de mediación instalado  |Skype Empresarial Server Servicio de mediación  |5068  |TCP  |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.  |
|Servidores front-end que también ejecutan un servidor de mediación instalado  |Skype Empresarial Server Servicio de mediación  |5081  |TCP  |Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.  |
|Servidores front-end que también ejecutan un servidor de mediación instalado  |Skype Empresarial Server Servicio de mediación  |5082  |TCP (TLS)  |Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.  |
|Servidores front-end  |Skype Empresarial Server Servicio de uso compartido de aplicaciones  |5065  |TCP  |Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.  |
|Servidores front-end  |Skype Empresarial Server Servicio de uso compartido de aplicaciones  |49152-65535  |TCP  |Intervalo de puerto de medios usado para compartir aplicaciones.  |
|Servidores front-end  |Skype Empresarial Server Anuncio de conferencia servicio  |5073  |TCP  |Se usa para las solicitudes SIP entrantes para el Skype Empresarial Server Anuncio de conferencia (es decir, para conferencias de acceso telefónico local).  |
|Servidores front-end  |Skype Empresarial Server Servicio de estacionamiento de llamadas  |5075  |TCP  |Se usa para las solicitudes SIP entrantes de la aplicación Estacionamiento de llamadas.  |
|Servidores front-end  |Skype Empresarial Server Servicio de prueba de audio  |5076  |TCP  |Se usa para las solicitudes SIP entrantes del servicio de prueba de audio.  |
|Servidores front-end  |No aplicable  |5066  |TCP  |Se usa para la puerta de enlace 9-1-1 mejorado (E9-1-1) saliente  |
|Servidores front-end  |Skype Empresarial Server Servicio de grupo de respuesta  |5071  |TCP  |Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.  |
|Servidores front-end  |Skype Empresarial Server Servicio de grupo de respuesta  |8404  |TCP (MTLS)  |Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.  |
|Servidores front-end  |Skype Empresarial Server Servicio de directivas de ancho de banda  |5080  |TCP  |Lo usa el servicio de directiva de ancho de banda del tráfico TURN perimetral A/V para el control de admisión de llamadas.  |
|Servidores front-end  |Skype Empresarial Server Acceso al servidor de recurso compartido de archivos  |445   |SMB/TCP  | Se usa para recuperar la libreta de direcciones, el contenido de la reunión y otros elementos almacenados en el servidor de recurso compartido de archivos.  |
|Servidores front-end  |Skype Empresarial Server Servicio de directivas de ancho de banda  |448  |TCP  |Se usa para el control de admisión de llamadas por el Skype Empresarial Server de directivas de ancho de banda.  |
|Servidores front-end donde reside el almacén de administración central  | Skype Empresarial Server Servicio de agente replicador maestro |445  |TCP  |Se usa para insertar datos de configuración del almacén de administración central en servidores que ejecutan Skype Empresarial Server.  |
|Todos los servidores  |Explorador SQL  |1434  |UDP  |SQL Explorador para copia replicada local de datos del almacén de administración central en la instancia SQL Server local  |
|Todos los usuarios internos  |Varios  |49152-57500  |TCP/UDP  |El intervalo de puerto de medios se usa para audioconferencias en todos los servidores internos. Se usa en todos los servidores que terminan el audio: servidores front-end (para el servicio Skype Empresarial Server Operador de conferencia, el servicio Skype Empresarial Server Anuncio de conferencia y el servicio de audio y vídeoconferencia Skype Empresarial Server) y el servidor de mediación.  |
|Office Servidores de aplicaciones web  ||443  ||Se usa Skype Empresarial Server para conectarse a Office Web Apps Server.  |
|Directores  |Skype Empresarial Server Front-End servicio de Skype Empresarial Server Front-End web  |5060  |TCP  |Se usa opcionalmente para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.  |
|Directores  |Skype Empresarial Server Front-End servicio de Skype Empresarial Server Front-End web  |444  |HTTPS  <br/> TCP  |Comunicación entre servidores front-end y director. Además, el certificado de cliente se publica (en servidores front-end) o se valida si el certificado de cliente ya se ha publicado.  |
|Directores  |Skype Empresarial Server Servicio de compatibilidad web  |80  |TCP  |Se usa para la comunicación inicial desde los directores a los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS). En condiciones normales, cambiará a tráfico HTTPS usando el puerto 443 y el tipo de protocolo TCP.  |
|Directores  |Skype Empresarial Server Servicio de compatibilidad web  |443  |HTTPS  |Se usa para la comunicación desde los directores a los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS).  |
|Directores  |Skype Empresarial Server Front-End servicio de Skype Empresarial Server Front-End web  |5061  |TCP  |Se usa para comunicaciones internas entre servidores y para conexiones de cliente.  |
|Servidores de mediación  |Skype Empresarial Server Servicio de mediación  |5070  |TCP  |Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end.  |
|Servidores de mediación  |Skype Empresarial Server Servicio de mediación  |5067  |TCP (TLS)  |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.  |
|Servidores de mediación  |Skype Empresarial Server Servicio de mediación  |5068  |TCP  |Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.  |
|Servidores de mediación  |Skype Empresarial Server Servicio de mediación  |5070  |TCP (MTLS)  |Se usa para solicitudes SIP desde los servidores front-end.  |
|Servidor front-end de chat persistente  |SIP de chat persistente  |5041  |TCP (MTLS)  ||
|Servidor front-end de chat persistente  |Chat persistente Windows Communication Foundation (WCF)  |881  |TCP (TLS) y TCP (MTLS)  ||
|Servidor front-end de chat persistente  |Servicio de transferencia de archivos de chat persistente  |443  |TCP (TLS)  ||
   
> [!NOTE]
> Algunos escenarios de control remoto de llamadas requieren una conexión entre el servidor front-end o el director y la PBX. Aunque Skype Empresarial Server ya no usa el puerto TCP 5060, durante la implementación del control remoto de llamadas se crea una configuración de servidor de confianza, que asocia el FQDN del servidor de línea RCC con el puerto TCP que el servidor front-end o director usará para conectarse al sistema PBX. Para obtener más información, consulte el cmdlet **CsTrustedApplicationComputer** en la Skype Empresarial Server del Shell de administración.
  
Para los grupos de servidores que solo usan equilibrio de carga de hardware (no equilibrio de carga de DNS), en la siguiente tabla se muestran los puertos que necesitan para abrir los equilibradores de carga de hardware.
  
**Puertos del equilibrador de carga de hardware si solo usa equilibrio de carga de hardware**

|Equilibrador de carga|Puerto|Protocolo|
|:-----|:-----|:-----|
|Equilibrador de carga del servidor front-end  |5061  |TCP (TLS)  |
|Equilibrador de carga del servidor front-end  |444  |HTTPS  |
|Equilibrador de carga del servidor front-end  |135  |DCOM y llamada a procedimiento remoto (RPC)  |
|Equilibrador de carga del servidor front-end  |80  |HTTP  |
|Equilibrador de carga del servidor front-end  |8080  |TCP: recuperación de cliente y dispositivo del certificado raíz desde el servidor front-end: clientes y dispositivos autenticados por NTLM  |
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
|Equilibrador de carga del director  |443  |HTTPS  |
|Equilibrador de carga del director  |444  |HTTPS  |
|Equilibrador de carga del director  |5061  |TCP  |
|Equilibrador de carga del director  |4443  |HTTPS (desde proxy inverso)  |
   
Los grupos de servidores front-end y de directores que usan equilibrio de carga de DNS también deben tener implementado un equilibrador de carga de hardware. En la siguiente tabla se muestran los puertos que se deben abrir en estos equilibradores de carga de hardware.
  
**Puertos del equilibrador de carga de hardware si usa equilibrio de carga de DNS**

|Equilibrador de carga|Puerto|Protocolo|
|:-----|:-----|:-----|
|Equilibrador de carga del servidor front-end  |80  |HTTP  |
|Equilibrador de carga del servidor front-end  |443  |HTTPS  |
|Equilibrador de carga del servidor front-end  |8080  |TCP: recuperación de cliente y dispositivo del certificado raíz desde el servidor front-end: clientes y dispositivos autenticados por NTLM  |
|Equilibrador de carga del servidor front-end  |4443  |HTTPS (desde proxy inverso)  |
|Equilibrador de carga del director  |443  |HTTPS  |
|Equilibrador de carga del director  |4443  |HTTPS (desde proxy inverso)  |

**Puertos de cliente requeridos**

|Componente|Puerto|Protocolo|Notas|
|:-----|:-----|:-----|:-----|
|Clientes  |67/68  |DHCP  |Se usa Skype Empresarial Server para buscar el FQDN del registrador (es decir, si se produce un error en SRV de DNS y no se configura la configuración manual).  |
|Clientes  |443  |TCP (TLS)  |Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.  |
|Clientes  |443  |TCP (PSOM/TLS)  |Se usa para el acceso de usuarios externos a las sesiones de conferencia web.  |
|Clientes  |443  |TCP (STUN/MSTURN)  |Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP)  |
|Clientes  |3478  |UDP (STUN/MSTURN)  |Se usa para el acceso de usuarios externos a sesiones A/V y medios (UDP)  |
|Clientes  |5061  |TCP (MTLS)  |Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.  |
|Clientes  |6891-6901  |TCP  |Se usa para la transferencia de archivos Skype Empresarial clientes y clientes anteriores.  |
|Clientes  |1024-65535 \*  |TCP/UDP  |Intervalo de puertos de audio (se requieren 20 puertos como mínimo)  |
|Clientes  |1024-65535 \*  |TCP/UDP  |Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo)  |
|Clientes  |1024-65535 \*  |TCP  |Transferencias de archivos de punto a punto (para la transferencia de archivos de conferencia, los clientes usan PSOM).  |
|Clientes  |1024-65535 \*  |TCP  |Uso compartido de aplicaciones.  |
|Teléfono de área común Aastra 6721ip  <br/> Teléfono de escritorio Aastra 6725ip  <br/> HP 4110 IP Phone (teléfono de área común)  <br/> HP 4120 IP Phone (teléfono de escritorio)  <br/> Teléfono de área común Polycom CX500 IP  <br/> Teléfono de escritorio Polycom CX600 IP  <br/> Teléfono de escritorio Polycom CX700 IP  <br/> Teléfono de conferencia Polycom CX3000 IP  |67/68  |DHCP  |Usado por los dispositivos enumerados para buscar el certificado Skype Empresarial Server, el FQDN de aprovisionamiento y el FQDN del registrador.  |
   
\* Para configurar puertos específicos para estos tipos de medios, use el cmdlet CsConferencingConfiguration (parámetros ClientMediaPortRangeEnabled, ClientMediaPort y ClientMediaPortRange).
  
> [!NOTE]
> Los programas de instalación para Skype Empresarial clientes crean automáticamente las excepciones de firewall del sistema operativo necesarias en el equipo cliente. 

> [!NOTE]
> Los puertos que se usan para el acceso de usuarios externos son necesarios para cualquier escenario en el que el cliente debe atravesar el firewall de la organización (por ejemplo, cualquier comunicación externa o reuniones hospedadas por otras organizaciones). 
  
## <a name="ipsec-exceptions"></a>Excepciones de IPsec

Para las redes empresariales donde se ha implementado la seguridad del protocolo de Internet (IPsec) (vea IETF RFC 4301-4309), IPsec debe deshabilitarse en el intervalo de puertos usados para la entrega de audio, vídeo y vídeo panorámico. Esta recomendación se fundamenta en la necesidad de evitar retrasos en la asignación de los puertos de medios debido a la negociación de IPsec.
  
En la siguiente tabla se detalla la configuración de las excepciones de IPsec recomendadas. 
  
**Excepciones de IPsec recomendadas**

|Nombre de regla|IP de origen|IP de destino|Protocolo|Puerto de origen|Puerto de destino|Requisito de autenticación|
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |
|Servidor perimetral A/V interno entrante  |Cualquiera  |Servidor perimetral A/V interno  |UDP y TCP  |Cualquiera  |Cualquiera  |No autenticar  |
|Servidor perimetral A/V externo entrante  |Cualquiera  |Servidor perimetral A/V externo  |UDP y TCP  |Cualquiera  |Cualquiera  |No autenticar  |
|Servidor perimetral A/V interno saliente  |Servidor perimetral A/V interno  |Cualquiera  |UDP &amp; TCP  |Cualquiera  |Cualquiera  |No autenticar  |
|Servidor perimetral A/V externo saliente  |Servidor perimetral A/V externo  |Cualquiera  |UDP y TCP  |Cualquiera  |Cualquiera  |No autenticar  |
|Servidor de mediación entrante  |Cualquiera  |Mediación  <br/> Servidor(s)  |UDP y TCP  |Cualquiera  |Cualquiera  |No autenticar  |
|Servidor de mediación saliente  |Mediación  <br/> Servidor(s)  |Cualquiera  |UDP y TCP  |Cualquiera  |Cualquiera  |No autenticar  |
|Operador de conferencia entrante  |Cualquiera  |Servidor front-end que ejecuta operador de conferencia  |UDP y TCP  |Cualquiera  |Cualquiera  |No autenticar  |
|Operador de conferencia saliente  |Servidor front-end que ejecuta operador de conferencia  |Cualquiera  |UDP y TCP  |Cualquiera  |Cualquiera  |No autenticar  |
|Servidor de conferencia A/V entrante  |Cualquiera  |Servidores front-end  |UDP y TCP  |Cualquiera  |Cualquiera  |No autenticar  |
|Salida de conferencia A/V  |Servidores front-end  |Cualquiera  |UDP y TCP  |Cualquiera  |Cualquiera  |No autenticar  |
|Exchange entrante  |Cualquiera  |Mensajería unificada de Exchange  |UDP y TCP  |Cualquiera  |Cualquiera  |No autenticar  |
|Servidores de aplicaciones compartidas entrantes  |Cualquiera  |Servidores de aplicaciones compartidas  |TCP  |Cualquiera  |Cualquiera  |No autenticar  |
|Servidor de aplicaciones compartidas saliente  |Servidores de aplicaciones compartidas  |Cualquiera  |TCP  |Cualquiera  |Cualquiera  |No autenticar  |
|Exchange saliente  |Mensajería unificada de Exchange  |Cualquiera  |UDP y TCP  |Cualquiera  |Cualquiera  |No autenticar  |
|Clientes  |Cualquiera  |Cualquiera  |UDP  |Intervalo de puertos de medios especificado  |Cualquiera  |No autenticar  |