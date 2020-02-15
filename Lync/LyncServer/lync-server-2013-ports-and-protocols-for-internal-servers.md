---
title: 'Lync Server 2013: puertos y protocolos para servidores internos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c748a79fe118c9b1d233a7a276bd8298a0e1c3e4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a>Puertos y protocolos para servidores internos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-04-06_

En esta sección se resumen los puertos y protocolos que usan los servidores, los equilibradores de carga y los clientes en una implementación de Lync Server.

<div>


> [!IMPORTANT]  
> Los clientes de Lync y Communicator cuando participan en una comunicación de una a una, a menudo se denominan de punto a punto. Técnicamente, los dos clientes se comunican en una conversación de una a una, con la unidad de control multipunto (IMMCU) de mensajería instantánea en la parte central. IMMCU es un componente del servidor front-end. La colocación de IMMCU en el flujo de trabajo de comunicación necesario permite el registro detallado de llamadas y otras características que permite el servidor front-end. La comunicación es desde un puerto de origen dinámico en el cliente al puerto del servidor front-end TLS/TCP/5061 (asumiendo el uso de la seguridad de la capa de transporte recomendada). Por diseño, la comunicación punto a punto (así como la mensajería instantánea de varios participantes) solo es posible cuando Lync Server y el IMMCU está activo y disponible.



</div>

<div>

## <a name="port-and-protocol-details"></a>Detalles de puerto y protocolo

<div>


> [!NOTE]  
> Firewall de Windows debe estar en ejecución antes de iniciar los servicios de Lync Server en un servidor, ya que esto se debe a que Lync Server abre los puertos necesarios en el firewall.



</div>

Para obtener más información sobre la configuración del firewall para los componentes perimetrales, consulte [determine external a/V Firewall and Port Requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

En la tabla siguiente se enumeran los puertos que debe abrir en cada rol del servidor interno.

### <a name="required-server-ports-by-server-role"></a>Puertos de servidor obligatorios (por rol del servidor)

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Rol de servidor</th>
<th>Nombre del servicio</th>
<th>Puerto</th>
<th>Protocolo</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Todos los servidores</p></td>
<td><p>Explorador SQL</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>Explorador SQL para la copia replicada local de la base de datos del almacén de administración central.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio front-end de Lync Server</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>Opcionalmente lo usan los servidores Standard Edition y front-end para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio front-end de Lync Server</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Lo usan los servidores Standard Edition y los grupos de servidores front-end para todas la comunicaciones SIP internas entre los servidores (MTLS), para las comunicaciones SIP entre el cliente y del servidor (TLS) y para las comunicaciones entre los servidores front-end y los servidores de mediación (MTLS). También se usa para las comunicaciones con el servidor de supervisión.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio front-end de Lync Server</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Se usa para la comunicación HTTPS entre el foco (el componente de Lync Server que administra el estado de conferencia) y los servidores individuales.</p>
<p>Este puerto también se usa para la comunicación TCP entre las aplicaciones de sucursal con funciones de supervivencia y los servidores front-end.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio front-end de Lync Server</p></td>
<td><p>135</p></td>
<td><p>DCOM y llamada a procedimiento remoto (RPC)</p></td>
<td><p>Se usa para operaciones basadas en DCOM como la migración de los usuarios, la sincronización del replicador de usuarios y la sincronización de la libreta de direcciones.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de conferencia de mensajería instantánea de Lync Server</p></td>
<td><p>5062</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para las solicitudes SIP entrantes de las conferencias de mensajería instantánea.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de conferencia Web de Lync Server</p></td>
<td><p>8057</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de compatibilidad con conferencias web de Lync Server</p></td>
<td><p>8058</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Se usa para escuchar las conexiones del modelo de objetos compartidos persistentes (PSOM) desde el cliente de Live Meeting y las versiones anteriores de Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de conferencia de audio y vídeo de Lync Server</p></td>
<td><p>5063</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para las solicitudes SIP entrantes de las conferencias de audio y vídeo (A/V).</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de conferencia de audio y vídeo de Lync Server</p></td>
<td><p>57501-65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Intervalo de puerto de medios usado para conferencias de vídeo.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de compatibilidad Web de Lync Server</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>Se usa para la comunicación entre los servidores front-end y los FQDN (direcciones URL usadas por los componentes web IIS) cuando no se usa HTTPS.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de compatibilidad Web de Lync Server</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Se usa para la comunicación entre los servidores front-end y los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS).</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de compatibilidad Web de Lync Server</p></td>
<td><p>8080</p></td>
<td><p>TCP y HTTP</p></td>
<td><p>Lo usan los componentes Web para el acceso externo.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Componente del servidor Web</p></td>
<td><p>4443</p></td>
<td><p>HTTPS</p></td>
<td><p>HTTPS (desde proxy inverso) y comunicaciones entre grupos de servidores front-end de HTTPS para el inicio de sesión con detección automática.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Componente del servidor Web</p></td>
<td><p>8060</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Componente del servidor Web</p></td>
<td><p>8061</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Componente de servicios de movilidad</p></td>
<td><p>5086</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Puerto SIP usado por los procesos internos de Mobility Services</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Componente de servicios de movilidad</p></td>
<td><p>5087</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Puerto SIP usado por los procesos internos de Mobility Services</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Componente de servicios de movilidad</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de operador de conferencia de Lync Server (Conferencia de acceso telefónico local)</p></td>
<td><p>5064</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para las solicitudes SIP entrantes de las conferencias telefónicas.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de operador de conferencia de Lync Server (Conferencia de acceso telefónico local)</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para las solicitudes SIP entrantes para el operador (llamadas de conferencia de acceso telefónico local).</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end que también ejecutan un servidor de mediación instalado</p></td>
<td><p>Servicio de mediación de Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end al servidor de mediación.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end que también ejecutan un servidor de mediación instalado</p></td>
<td><p>Servicio de mediación de Lync Server</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end que también ejecutan un servidor de mediación instalado</p></td>
<td><p>Servicio de mediación de Lync Server</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end que también ejecutan un servidor de mediación instalado</p></td>
<td><p>Servicio de mediación de Lync Server</p></td>
<td><p>5081</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end que también ejecutan un servidor de mediación instalado</p></td>
<td><p>Servicio de mediación de Lync Server</p></td>
<td><p>5082</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de uso compartido de aplicaciones de Lync Server</p></td>
<td><p>5065</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para las solicitudes de escucha SIP entrantes para compartir las aplicaciones.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de uso compartido de aplicaciones de Lync Server</p></td>
<td><p>49152-65535</p></td>
<td><p>TCP</p></td>
<td><p>Intervalo de puerto de medios usado para compartir aplicaciones.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de anuncio de conferencia de Lync Server</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para las solicitudes SIP entrantes para el servicio de anuncio de conferencia de Lync Server (es decir, para las conferencias de acceso telefónico local).</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de estacionamiento de llamadas de Lync Server</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para las solicitudes SIP entrantes de la aplicación Estacionamiento de llamadas.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de prueba de audio de Lync Server</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para las solicitudes SIP entrantes del servicio de prueba de audio.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>No aplicable</p></td>
<td><p>5066</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para la puerta de enlace 9-1-1 mejorado (E9-1-1) saliente</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de grupo de respuesta de Lync Server</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de grupo de respuesta de Lync Server</p></td>
<td><p>8404</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Se usa para las solicitudes SIP entrantes de la aplicación Grupo de respuesta.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de directiva de ancho de banda de Lync Server</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
<td><p>Lo usa el servicio de directiva de ancho de banda del tráfico TURN perimetral A/V para el control de admisión de llamadas.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de directiva de ancho de banda de Lync Server</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para el control de admisión de llamadas por el servicio de directiva de ancho de banda de Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end donde reside el almacén de administración central</p></td>
<td><p>Agente de replicador maestro de Microsoft Lync Server</p></td>
<td><p>445</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para insertar los datos de configuración desde el almacén de administración central en los servidores que ejecutan Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Todos los servidores</p></td>
<td><p>Explorador SQL</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>Explorador SQL para la copia replicada local de los datos del almacén de administración central en la instancia local de SQL Server</p></td>
</tr>
<tr class="odd">
<td><p>Todos los usuarios internos</p></td>
<td><p>Varios</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>El intervalo de puerto de medios se usa para audioconferencias en todos los servidores internos. Usada por todos los servidores que terminan audio: servidores front-end (para el servicio de operador de conferencia de Lync Server, el servicio de anuncio de conferencia de Lync Server y el servicio de conferencia de audio y vídeo de Lync Server) y el servidor de mediación.</p></td>
</tr>
<tr class="even">
<td><p>Servidores de Office Web Apps</p></td>
<td></td>
<td><p>443</p></td>
<td></td>
<td><p>Se usa en Lync Server 2013 para conectarse a Office Web Apps Server.</p></td>
</tr>
<tr class="odd">
<td><p>Reparto</p></td>
<td><p>Servicio front-end de Lync Server</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>Se usa opcionalmente para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.</p></td>
</tr>
<tr class="even">
<td><p>Reparto</p></td>
<td><p>Servicio front-end de Lync Server</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Comunicación entre servidores front-end y director. Además, la publicación de certificados de cliente (para los servidores front-end) o la validación si ya se ha publicado el certificado de cliente.</p></td>
</tr>
<tr class="odd">
<td><p>Reparto</p></td>
<td><p>Servicio de compatibilidad Web de Lync Server</p></td>
<td><p>80</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para la comunicación inicial desde los directores a los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS). En condiciones normales, cambiará a tráfico HTTPS usando el puerto 443 y el tipo de protocolo TCP.</p></td>
</tr>
<tr class="even">
<td><p>Reparto</p></td>
<td><p>Servicio de compatibilidad Web de Lync Server</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Se usa para la comunicación desde los directores a los FQDN de la granja de servidores web (direcciones URL usadas por los componentes web IIS).</p></td>
</tr>
<tr class="odd">
<td><p>Reparto</p></td>
<td><p>Servicio front-end de Lync Server</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para comunicaciones internas entre servidores y para conexiones de cliente.</p></td>
</tr>
<tr class="even">
<td><p>Servidores de mediación</p></td>
<td><p>Servicio de mediación de Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores de mediación</p></td>
<td><p>Servicio de mediación de Lync Server</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.</p></td>
</tr>
<tr class="even">
<td><p>Servidores de mediación</p></td>
<td><p>Servicio de mediación de Lync Server</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores de mediación</p></td>
<td><p>Servicio de mediación de Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Se usa para solicitudes SIP desde los servidores front-end.</p></td>
</tr>
<tr class="even">
<td><p>Servidor front-end de chat persistente</p></td>
<td><p>SIP de chat persistente</p></td>
<td><p>5041</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Servidor front-end de chat persistente</p></td>
<td><p>Chat persistente Windows Communication Foundation (WCF)</p></td>
<td><p>881</p></td>
<td><p>TCP (TLS) y TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Servidor front-end de chat persistente</p></td>
<td><p>Servicio de transferencia de archivos de chat persistente</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Algunos escenarios de control remoto de llamadas requieren una conexión entre el servidor front-end o el director y la PBX. Aunque Lync Server ya no usa el puerto TCP 5060, durante la implementación de control remoto de llamadas, se crea una configuración de servidor de confianza, que asocia el FQDN del servidor de línea RCC con el puerto TCP que el director o el servidor front-end usará para conectarse al sistema PBX. Para obtener más información, consulte el cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> en la documentación del shell de administración de Lync Server.



</div>

Para los grupos de servidores que solo usan equilibrio de carga de hardware (no equilibrio de carga de DNS), en la siguiente tabla se muestran los puertos que necesitan para abrir los equilibradores de carga de hardware.

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a>Puertos del equilibrador de carga de hardware si solo usa equilibrio de carga de hardware

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Equilibrador de carga</th>
<th>Puerto</th>
<th>Protocolo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>135</p></td>
<td><p>DCOM y llamada a procedimiento remoto (RPC)</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>8080</p></td>
<td><p>TCP - Recuperación cliente y dispositivo del certificado raíz del servidor de front-end – clientes y dispositivos autenticados por NTLM</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (desde proxy inverso)</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del servidor de mediación</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del servidor front-end (si el grupo también ejecuta el servidor de mediación)</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del director</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del director</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del director</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del director</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (desde proxy inverso)</p></td>
</tr>
</tbody>
</table>


Los grupos de servidores front-end y de directores que usan equilibrio de carga de DNS también deben tener implementado un equilibrador de carga de hardware. En la siguiente tabla se muestran los puertos que se deben abrir en estos equilibradores de carga de hardware.

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a>Puertos del equilibrador de carga de hardware si usa equilibrio de carga de DNS

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Equilibrador de carga</th>
<th>Puerto</th>
<th>Protocolo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>8080</p></td>
<td><p>TCP - Recuperación cliente y dispositivo del certificado raíz del servidor de front-end – clientes y dispositivos autenticados por NTLM</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (desde proxy inverso)</p></td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del director</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del director</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (desde proxy inverso)</p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a>Puertos de cliente requeridos

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Puerto</th>
<th>Protocolo</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>67/68</p></td>
<td><p>DCHP</p></td>
<td><p>Lo usa Lync Server para buscar el FQDN del registrador (es decir, si se produce un error en el SRV de DNS y no se configura la configuración manual).</p></td>
</tr>
<tr class="even">
<td><p>Clientes</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>443</p></td>
<td><p>TCP (PSOM/TLS)</p></td>
<td><p>Se usa para el acceso de usuarios externos a las sesiones de conferencia web.</p></td>
</tr>
<tr class="even">
<td><p>Clientes</p></td>
<td><p>443</p></td>
<td><p>TCP (STUN/MSTURN)</p></td>
<td><p>Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP)</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>3478</p></td>
<td><p>UDP (STUN/MSTURN)</p></td>
<td><p>Se usa para el acceso de usuarios externos a las sesiones y los medios de a/V (UDP)</p></td>
</tr>
<tr class="even">
<td><p>Clientes</p></td>
<td><p>5061</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Se usa para el tráfico SIP de cliente a servidor para el acceso de usuarios externos.</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>6891-6901</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para la transferencia de archivos entre clientes de Lync y clientes anteriores (clientes de Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 y Live Communications Server 2005).</p></td>
</tr>
<tr class="even">
<td><p>Clientes</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Intervalo de puertos de audio (se requieren 20 puertos como mínimo)</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo)</p></td>
</tr>
<tr class="even">
<td><p>Clientes</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>Transferencias de archivos de punto a punto (para la transferencia de archivos de conferencia, los clientes usan PSOM).</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>Uso compartido de aplicaciones.</p></td>
</tr>
<tr class="even">
<td><p>Teléfono de área común Aastra 6721ip</p>
<p>Teléfono de escritorio Aastra 6725ip</p>
<p>HP 4110 IP Phone (teléfono de área común)</p>
<p>HP 4120 IP Phone (teléfono de escritorio)</p>
<p>Teléfono de área común Polycom CX500 IP</p>
<p>Teléfono de escritorio Polycom CX600 IP</p>
<p>Teléfono de escritorio Polycom CX700 IP</p>
<p>Teléfono de conferencia Polycom CX3000 IP</p></td>
<td><p>67/68</p></td>
<td><p>DCHP</p></td>
<td><p>Usada por los dispositivos enumerados para buscar el certificado de Lync Server, el FQDN de aprovisionamiento y el FQDN del registrador.</p></td>
</tr>
</tbody>
</table>


**\*** Para configurar los puertos específicos para estos tipos de medios, use el cmdlet CsConferencingConfiguration (los parámetros clientmediaportrangeenabled, ClientMediaPort y ClientMediaPortRange).

<div>


> [!NOTE]  
> Los clientes de set programs for Lync crean automáticamente las excepciones de firewall del sistema operativo necesarias en el equipo cliente.



</div>

<div>


> [!NOTE]  
> Los puertos que se utilizan para el acceso de usuarios externos son necesarios en cualquier escenario en el que el cliente deba atravesar el firewall de la organización (por ejemplo, las comunicaciones o reuniones externas alojadas por otras organizaciones).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

