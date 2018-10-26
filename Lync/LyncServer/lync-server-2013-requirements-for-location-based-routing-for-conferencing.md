---
title: Requisitos para establecer el enrutamiento basado en ubicación en las conferencias
TOCTitle: Requisitos para establecer el enrutamiento basado en ubicación en las conferencias
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56271291
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos para establecer el enrutamiento basado en ubicación en las conferencias

 

_**Última modificación del tema:** 2016-12-08_

Estos son los requisitos necesarios para instalar y configurar la aplicación de conferencias del enrutamiento basado en ubicación:

  - La actualización acumulativa 2 de Lync Server 2013 se debe implementar en todos los servidores o grupos de servidores de la topología.


> [!NOTE]
> Si un servidor o grupo de servidores de Lync existente en la topología no tiene instalada la actualización acumulativa&nbsp;2 de Lync Server&nbsp;2013 u otra posterior, no se garantiza la aplicación del enrutamiento basado en ubicación de las reuniones de Lync.



  - El enrutamiento basado en ubicación de Lync Server 2013 es un requisito previo de la aplicación de conferencias de enrutamiento basado en ubicación. Para más información sobre cómo configurar el enrutamiento basado en ubicación de Lync Server 2013, vea [Configuración del enrutamiento basado en ubicación](lync-server-2013-configuring-location-based-routing.md).

  - Los requisitos de la aplicación de conferencias de enrutamiento basado en ubicación son los mismos que los del enrutamiento basado en ubicación de Lync Server 2013. Para más información, vea [Planeación del enrutamiento basado en ubicación](lync-server-2013-planning-for-location-based-routing.md).

## Servidores compatibles

Para usar la aplicación de conferencias de enrutamiento basado en ubicación, hay que implementar la actualización acumulativa 2 de Lync Server 2013 en todos los grupos de servidores front-end y servidores Standard Edition de la topología. Si la actualización acumulativa 2 de Lync Server 2013 no está instalada en algunos servidores de Lync de la topología, las restricciones del enrutamiento basado en ubicación no se pueden aplicar totalmente en las transferencias de llamadas consultativas y las reuniones de Lync.

La siguiente tabla recoge la combinación de versiones y roles de servidor que son compatibles con el enrutamiento basado en ubicación.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Versión del grupo de servidores front-end</p></td>
<td><p>Versión del servidor de mediación</p></td>
<td><p>Compatible</p></td>
</tr>
<tr class="even">
<td><p>Actualización acumulativa 2 de Lync Server 2013</p></td>
<td><p>Actualización acumulativa 2 de Lync Server 2013</p></td>
<td><p>Sí</p></td>
</tr>
<tr class="odd">
<td><p>Actualización acumulativa 2 de Lync Server 2013</p></td>
<td><p>Actualización acumulativa 1 de Lync Server 2013</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Actualización acumulativa 2 de Lync Server 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Actualización acumulativa 2 de Lync Server 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Actualización acumulativa 1 de Lync Server 2013</p></td>
<td><p>Cualquiera</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>Cualquiera</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Cualquiera</p></td>
<td><p>No</p></td>
</tr>
</tbody>
</table>


## Clientes compatibles

Los clientes de Lync compatibles con el enrutamiento basado en ubicación de las reuniones de Lync son los mismos clientes que son compatibles con el enrutamiento basado en ubicación de Lync Server 2013. Para más información, vea [Compatibilidad de cliente y servidor para el enrutamiento basado en ubicación](lync-server-2013-client-and-server-support-for-location-based-routing.md).

## Requisitos del servidor de mediación para las transferencias de llamadas consultativas

La aplicación de conferencias de enrutamiento basado en ubicación requiere implementar servidores de mediación independientes para aplicar las restricciones del enrutamiento basado en ubicación en las transferencias de llamadas consultativas.

Para aplicar el enrutamiento basado en ubicación en las transferencias de llamadas consultativas, el servidor de mediación se debe asociar con un solo de servidor de mediación del mismo nivel (es decir, PBX, puerta de enlace SIP, etc.), en regiones de red donde sea obligatorio el enrutamiento basado en ubicación. Si se implementan más servidores de mediación del mismo nivel en la misma región de red, el servidor de mediación del mismo nivel se debe asociar con un servidor de mediación diferente. Este requisito se detalla del modo siguiente:

  - Servidor de mediación único por varios servidores de mediación del mismo nivel: cuando una transferencia de llamada consultativa se redirige a un servidor de mediación del mismo nivel a través de un servidor de mediación que está configurado con varios troncos SIP a varios servidores del mismo nivel (es decir, PBX y puertas de enlace), la transferencia de llamada consultativa se bloquea para evitar la omisión de tarifas RTC si la transferencia de llamada consultativa se permite a través de algunos troncos SIP pero se impide a través de otros troncos SIP.
    
    Por ejemplo, en el caso de un servidor de mediación único que ofrezca asistencia a un servidor de mediación del mismo nivel de una puerta de enlace RTC y a un servidor de mediación PBX del mismo nivel, se observa este comportamiento:
    
      - Cuando un usuario de Lync de un sitio determinado (por ej., sitio 1) trate de transferir una llamada con un extremo de RTC a un usuario de Lync de un sitio distinto (por ej., sitio 2) a través de una transferencia consultativa, la llamada se impedirá para evitar la omisión de tarifas RTC.
    
      - Cuando un usuario de Lync de un sitio determinado (por ej., sitio 1) trate de transferir una llamada con un extremo de PBX del mismo sitio (sitio 1) a un usuario de Lync de un sitio distinto (por ej., sitio 2) a través de una transferencia consultativa, la llamada se impedirá aunque no exista la posibilidad de que las tarifas RTC se omitan.

  - Servidores de mediación independientes por servidor de mediación del mismo nivel
    
    Cuando una transferencia consultativa se dirige a un servidor de mediación del mismo nivel, la transferencia consultativa se evalúa según el servidor de mediación del mismo nivel al que da asistencia el servidor de mediación. La llamada se permitirá o no según la posibilidad de que se puedan omitir las tarifas RTC independientemente de todos los demás servidores de mediación del mismo nivel que haya en el sitio, ya que estos reciben asistencia de servidores de mediación independientes.
    
    Por ejemplo, en el caso de un servidor de mediación independiente que ofrezca asistencia a un servidor de mediación del mismo nivel de una puerta de enlace RTC y a un servidor de mediación PBX del mismo nivel, se observa este comportamiento:
    
      - Cuando un usuario de Lync de un sitio determinado (por ej., sitio 1) trate de transferir una llamada con un extremo de RTC a un usuario de Lync de un sitio distinto (por ej., sitio 2) a través de una transferencia consultativa, la llamada se impedirá para evitar la omisión de tarifas RTC.
    
      - Cuando un usuario de Lync de un sitio determinado (por ej., sitio 1) trate de transferir una llamada con un extremo de PBX del mismo sitio (sitio 1) a un usuario de Lync de un sitio distinto (por ej., sitio 2) a través de una transferencia consultativa, la llamada se permitirá porque no existe la posibilidad de que las tarifas RTC se omitan.

## Capacidades no compatibles con la aplicación de conferencias del enrutamiento basado en ubicación

Las siguientes capacidades no son compatibles con la aplicación de conferencias del enrutamiento basado en ubicación:

  - Conferencias de acceso telefónico: el enrutamiento basado en ubicación no se puede aplicar en las conferencias de acceso telefónico. El enrutamiento basado en ubicación no restringirá las solicitudes de acceso telefónico enviadas a conferencias aunque el organizador de una conferencia sea un usuario de Lync habilitado para el enrutamiento basado en ubicación.

  - Recomendamos no aprovisionar números de acceso a conferencias en regiones donde se deban aplicar restricciones al enrutamiento basado en ubicación.

