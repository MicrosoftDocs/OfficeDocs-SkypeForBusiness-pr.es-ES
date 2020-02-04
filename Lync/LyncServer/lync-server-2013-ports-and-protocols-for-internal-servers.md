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
ms.openlocfilehash: 1001cce83d9b23125b177725c77715bd19a00e03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a>Puertos y protocolos para servidores internos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-04-06_

En esta sección se resumen los puertos y protocolos usados por servidores, equilibradores de carga y clientes en una implementación de Lync Server.

<div>


> [!IMPORTANT]  
> Los clientes de Lync y Communicator, cuando participan en una sola comunicación, se suelen denominar de punto a punto. Técnicamente, los dos clientes se comunican en una conversación de una en una, con la unidad de control multipunto de mensajería instantánea (IMMCU) en el medio. El IMMCU es un componente de servidor front-end. La colocación de IMMCU en el flujo de trabajo de comunicaciones requerido permite la grabación de detalles de llamadas y otras características que permite el servidor front-end. La comunicación es de un puerto de origen dinámico en el cliente al puerto del servidor front-end TLS/TCP/5061 (asumiendo el uso de la seguridad de la capa de transporte recomendada). Por diseño, la comunicación de punto a punto (así como la de mensajería instantánea de varios participantes) solo es posible cuando Lync Server y IMMCU está activo y disponible.



</div>

<div>

## <a name="port-and-protocol-details"></a>Detalles de protocolo y puerto

<div>


> [!NOTE]  
> El Firewall de Windows debe estar ejecutándose antes de iniciar los servicios de Lync Server en un servidor, porque es cuando Lync Server abre los puertos necesarios en el firewall.



</div>

Para obtener más información sobre la configuración del firewall para los componentes de Edge, consulte [determinar el firewall externo a/V y los requisitos de puerto para Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

En la tabla siguiente se enumeran los puertos que debe abrir en cada rol del servidor interno.

### <a name="required-server-ports-by-server-role"></a>Puertos de servidor obligatorios (por rol de servidor)

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
<th>Nombre de servicio</th>
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
<td><p>Explorador SQL para la copia replicada local de la base de datos del almacén central de administración.</p></td>
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
<td><p>Lo usan los servidores Standard Edition y los grupos de servidores front-end para todas las comunicaciones SIP internas entre los servidores (MTLS), para las comunicaciones SIP entre el cliente y el servidor (TLS) y para las comunicaciones SIP entre los servidores front-end y los servidores de mediación (MTLS). También se usa para comunicaciones con el servidor de supervisión.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio front-end de Lync Server</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Se usa para la comunicación HTTPS entre el foco (el componente de Lync Server que administra el estado de la Conferencia) y los servidores individuales.</p>
<p>Este puerto también se usa para la comunicación TCP entre los equipos de las sucursales y los servidores de aplicaciones para el usuario.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio front-end de Lync Server</p></td>
<td><p>135</p></td>
<td><p>DCOM y llamada a procedimiento remoto (RPC)</p></td>
<td><p>Se usa para operaciones basadas en DCOM, como la migración de los usuarios, la sincronización del replicador de usuarios y la sincronización de la libreta de direcciones.</p></td>
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
<td><p>Servicio de conferencias web de Lync Server</p></td>
<td><p>8057</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Se usa para escuchar las conexiones del Modelo de objetos compartidos persistentes (PSOM) desde un cliente.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de compatibilidad con conferencias web de Lync Server</p></td>
<td><p>8058</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Se usa para escuchar conexiones persistentes del modelo de objetos compartidos (PSOM) desde el cliente de Live Meeting y las versiones anteriores de Lync Server.</p></td>
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
<td><p>Intervalo de puertos de medios que se usa para conferencias de vídeo.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de compatibilidad Web de Lync Server</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>Se usa para la comunicación entre los servidores front-end y los FQDN (direcciones URL que usan los componentes web de IIS) cuando no se usa HTTPS.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de compatibilidad Web de Lync Server</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Se usa para la comunicación entre los servidores front-end y los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS).</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de compatibilidad Web de Lync Server</p></td>
<td><p>8080</p></td>
<td><p>TCP y HTTP</p></td>
<td><p>Lo usan los componentes web para acceso externo.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Componente de servidor web</p></td>
<td><p>4443</p></td>
<td><p>HTTPS</p></td>
<td><p>Comunicaciones entre grupos de HTTPS (desde proxy inverso) y HTTPS front-end para el inicio de sesión con detección automática.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Componente de servidor web</p></td>
<td><p>8060</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Componente de servidor web</p></td>
<td><p>8061</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Componente de servicios de movilidad</p></td>
<td><p>5086</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Puerto SIP que usan los procesos internos de los servicios de movilidad</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Componente de servicios de movilidad</p></td>
<td><p>5087</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Puerto SIP que usan los procesos internos de los servicios de movilidad</p></td>
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
<td><p>Servicio del operador de conferencias de Lync Server (Conferencia de acceso telefónico local)</p></td>
<td><p>5064</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para las solicitudes SIP entrantes de las conferencias de acceso telefónico local.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio del operador de conferencias de Lync Server (Conferencia de acceso telefónico local)</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para las solicitudes SIP entrantes para operadores (llamar en conferencia).</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end que también ejecutan un servidor de mediación combinado</p></td>
<td><p>Servicio de mediación de Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Lo usa el servidor de mediación para solicitudes entrantes desde el servidor front-end al servidor de mediación.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end que también ejecutan un servidor de mediación combinado</p></td>
<td><p>Servicio de mediación de Lync Server</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end que también ejecutan un servidor de mediación combinado</p></td>
<td><p>Servicio de mediación de Lync Server</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para solicitudes SIP entrantes desde la puerta de enlace RTC al servidor de mediación.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end que también ejecutan un servidor de mediación combinado</p></td>
<td><p>Servicio de mediación de Lync Server</p></td>
<td><p>5081</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para solicitudes SIP salientes desde el servidor de mediación a la puerta de enlace RTC.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end que también ejecutan un servidor de mediación combinado</p></td>
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
<td><p>Intervalo de puertos de medios que se usa para compartir aplicaciones.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de anuncios de conferencias de Lync Server</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para las solicitudes SIP entrantes para el servicio de anuncios de conferencias de Lync Server (es decir, para conferencias de acceso telefónico local).</p></td>
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
<td><p>Se usa para la puerta de enlace 9-1-1 mejorado (E9-1-1) saliente.</p></td>
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
<td><p>Lo usa el servicio de directiva de ancho de banda del tráfico TURN perimetral A/V para el servicio de control de admisión de llamadas.</p></td>
</tr>
<tr class="even">
<td><p>Servidores front-end</p></td>
<td><p>Servicio de directiva de ancho de banda de Lync Server</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
<td><p>Usado por el servicio de directivas de ancho de banda de Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>Servidores front-end en los que reside el almacén de administración central</p></td>
<td><p>Servicio agente de replicación maestra de Lync Server</p></td>
<td><p>445</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para insertar los datos de configuración desde el almacén de administración central en servidores que ejecutan Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Todos los servidores</p></td>
<td><p>Explorador SQL</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>Explorador SQL para la copia replicada local de los datos del almacén central de administración en la instancia local de SQL Server</p></td>
</tr>
<tr class="odd">
<td><p>Todos los usuarios internos</p></td>
<td><p>Varios</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>El intervalo de puertos de medios se usa para audioconferencias en todos los servidores internos. Usado por todos los servidores que terminan audio: servidores front-end (para el servicio del operador de conferencias de Lync Server, servicio de anuncios de conferencias de Lync Server y el servicio de audioconferencias de audio y vídeo de Lync) y servidor de mediación.</p></td>
</tr>
<tr class="even">
<td><p>Servidores de Office Web Apps</p></td>
<td></td>
<td><p>443</p></td>
<td></td>
<td><p>Usado por Lync Server 2013 para conectarse a Office Web Apps Server.</p></td>
</tr>
<tr class="odd">
<td><p>Directores</p></td>
<td><p>Servicio front-end de Lync Server</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>Se usa opcionalmente para rutas estáticas a servicios de confianza, como los servidores de control remoto de llamadas.</p></td>
</tr>
<tr class="even">
<td><p>Directores</p></td>
<td><p>Servicio front-end de Lync Server</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Comunicación entre servidores front-end y Director. Además, la publicación de certificados de cliente (a servidores de aplicaciones para el usuario) o la validación si el certificado de cliente ya se ha publicado.</p></td>
</tr>
<tr class="odd">
<td><p>Directores</p></td>
<td><p>Servicio de compatibilidad Web de Lync Server</p></td>
<td><p>80</p></td>
<td><p>TCP</p></td>
<td><p>Se usa para la comunicación inicial desde los Directores a los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS). En condiciones normales, cambiará a tráfico HTTPS a través del puerto 443 y el tipo de protocolo TCP.</p></td>
</tr>
<tr class="even">
<td><p>Directores</p></td>
<td><p>Servicio de compatibilidad Web de Lync Server</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Se usa para la comunicación desde los Directores a los FQDN de la granja de servidores web (direcciones URL que usan los componentes web de IIS).</p></td>
</tr>
<tr class="odd">
<td><p>Directores</p></td>
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
<td><p>Windows Communication Foundation (WCF) de chat persistente</p></td>
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
> Algunos escenarios de control remoto de llamadas requieren una conexión entre el servidor front-end o el Director y la PBX. Aunque Lync Server ya no usa el puerto TCP 5060, durante la implementación de control remoto de llamadas, se crea una configuración de servidor de confianza, que asocia el FQDN del servidor de línea RCC con el puerto TCP que usará el servidor o director de front-end para conectarse al sistema PBX. Para obtener más información, vea el cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> en la documentación del shell de administración de Lync Server.



</div>

Para los grupos que solo usan equilibrio de carga de hardware (no equilibrio de carga de DNS), en la siguiente tabla se muestran los puertos que necesitan para abrir los equilibradores de carga de hardware.

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
<td><p>TCP, Recuperación cliente y dispositivo del certificado raíz del servidor de front-end, clientes y dispositivos autenticados por NTLM</p></td>
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
<td><p>Equilibrador de carga del Director</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del Director</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del Director</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del Director</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (desde proxy inverso)</p></td>
</tr>
</tbody>
</table>


Los grupos de servidores front-end y de Directores que usan equilibrio de carga de DNS también deben tener implementado un equilibrador de carga de hardware. En la siguiente tabla se muestran los puertos que se deben abrir en estos equilibradores de carga de hardware.

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
<td><p>TCP, Recuperación cliente y dispositivo del certificado raíz del servidor de front-end, clientes y dispositivos autenticados por NTLM</p></td>
</tr>
<tr class="even">
<td><p>Equilibrador de carga del servidor front-end</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (desde proxy inverso)</p></td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del Director</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Equilibrador de carga del Director</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (desde proxy inverso)</p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a>Puertos de cliente necesarios

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
<td><p>DHCP</p></td>
<td><p>Utilizado por Lync Server para encontrar el nombre completo del registrador (es decir, si no se puede establecer la configuración manual de DNS SRV).</p></td>
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
<td><p>Se usa para el acceso de usuarios externos a las sesiones de A/V y a los medios (TCP).</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>3478</p></td>
<td><p>UDP (STUN/MSTURN)</p></td>
<td><p>Se usa para el acceso de usuarios externos a los medios y las sesiones de A/V (UDP)</p></td>
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
<td><p>1024-65535*</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Intervalo de puertos de audio (se requieren 20 puertos como mínimo).</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>1024-65535*</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Intervalo de puertos de vídeo (se requieren 20 puertos como mínimo).</p></td>
</tr>
<tr class="even">
<td><p>Clientes</p></td>
<td><p>1024-65535*</p></td>
<td><p>TCP</p></td>
<td><p>Transferencias de archivos de punto a punto (para la transferencia de archivos de conferencia, los clientes usan PSOM).</p></td>
</tr>
<tr class="odd">
<td><p>Clientes</p></td>
<td><p>1024-65535*</p></td>
<td><p>TCP</p></td>
<td><p>Uso compartido de aplicaciones.</p></td>
</tr>
<tr class="even">
<td><p>Teléfono de área común Aastra 6721ip</p>
<p>Teléfono de escritorio Aastra 6725ip</p>
<p>Teléfono IP HP 4110 (teléfono de área común)</p>
<p>Teléfono IP HP 4120 (teléfono de escritorio)</p>
<p>Teléfono de área común Polycom CX500 IP</p>
<p>Teléfono de escritorio Polycom CX600 IP</p>
<p>Teléfono de escritorio Polycom CX700 IP</p>
<p>Teléfono de conferencia Polycom CX3000 IP</p></td>
<td><p>67/68</p></td>
<td><p>DHCP</p></td>
<td><p>Usado por los dispositivos de la lista para buscar el certificado de Lync Server, el FQDN de aprovisionamiento y el registrador de FQDN.</p></td>
</tr>
</tbody>
</table>


**\*** Para configurar puertos específicos para estos tipos de medios, use el cmdlet CsConferencingConfiguration (ClientMediaPortRangeEnabled, ClientMediaPort y ClientMediaPortRange parámetros).

<div>


> [!NOTE]  
> El conjunto de programas para clientes de Lync crea automáticamente las excepciones de firewall del sistema operativo necesarias en el equipo cliente.



</div>

<div>


> [!NOTE]  
> Los puertos que se usan para el acceso de usuarios externos son necesarios en cualquier escenario en el que el cliente deba atravesar el firewall de la organización (por ejemplo, las comunicaciones o reuniones externas que se hospedan en otras organizaciones).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

