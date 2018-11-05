---
title: "Lync Server 2013: Determinar requisitos de los puertos y el firewall de A/V externos"
TOCTitle: Determinar los requisitos de los puertos y el firewall de A/V externos
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48274993
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Determinar los requisitos de los puertos y el firewall de A/V externos en Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

La comunicación de audio/vídeo (A/V) puede resultar compleja. Debido a la naturaleza de los protocolos usados en A/V y al modo en que los clientes y servidores usan los protocolos, se garantiza una sección especial para explicar las diferencias entre las versiones del cliente y del servidor.

Use la siguiente tabla para determinar los requisitos de firewall A/V y los puertos que se abren. A continuación, revise la terminología de traducción de direcciones de red (NAT) porque NAT puede implementarse de formas muy distintas. Para ver un ejemplo detallado de configuración de puertos de firewall, consulte las arquitecturas de referencia en [Escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

### Uso general de protocolo para UDP y TCP en tráfico multimedia y de audio y vídeo

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Transporte de audio y vídeo</th>
<th>Uso</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>Protocolo de capa de transporte preferido para audio y vídeo</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>Protocolo de capa de transporte de reserva para audio y vídeo</p>
<p>Protocolo de capa de transporte necesario para el uso compartido de aplicaciones en Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013</p>
<p>Protocolo de capa de transporte necesario para la transferencia de archivos en Lync Server 2010 y Lync Server 2013</p></td>
</tr>
</tbody>
</table>


## Requisitos de puerto de firewall A/V para el acceso de usuarios externos

Los requisitos de puerto de firewall para interfaces externas (e internas) de SIP y conferencias son coherentes, con independencia de la versión del cliente o del socio federado.

No sucede lo mismo con la interfaz perimetral externa de audio y vídeo. Para la federación con Office Communications Server 2007, el servicio perimetral A/V requiere que las reglas de firewall externo permitan que el tráfico RTP/TCP y RTP/UDP del intervalo de puertos de 50.000 a 59.999 fluya en ambas direcciones. En la tabla anterior se presupone que Lync Server 2013 es el principal socio federado y se configura para comunicarse con uno de los cuatro tipos de socio federado incluidos en la lista.

Al configurar el intervalo de puertos de audio y vídeo de 50.000 a 59.999, debe tener en cuenta que el intervalo de puertos incluirá los puertos de origen para las comunicaciones con los socios federados. En detalle, considere que una comunicación se inicia desde un socio federado. La comunicación desde los puertos de Servicio perimetral A/V en el intervalo de 50.000 a 59.999 se conectará con el puerto TCP 443 previsto del Servicio perimetral A/V del socio. Por el contrario, el tráfico entrante en su puerto TCP 443 de Servicio perimetral A/V tendrá un puerto de origen en el intervalo de 50.000 a 59.999.

Los distintos firewalls y directivas para la administración de firewall pueden requerir que se configuren solo reglas de destino, o bien pueden requerir la configuración tanto de reglas de origen como de destino. Si solo se requieren reglas en los puertos de destino, los requisitos de audio y vídeo son los siguientes:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>IP de origen</th>
<th>IP de destino</th>
<th>Puerto de destino</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interfaz de Servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interfaz de Servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Cualquiera</p></td>
<td><p>Interfaz de Servicio perimetral A/V</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Cualquiera</p></td>
<td><p>Interfaz de Servicio perimetral A/V</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


Si las directivas requieren definiciones de reglas de firewall tanto entrantes como salientes, los requisitos de audio y vídeo son los siguientes:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>IP de origen</th>
<th>IP de destino</th>
<th>Puerto de origen</th>
<th>Puerto de destino</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interfaz de Servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>TCP 50.000-59.999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interfaz de Servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Cualquiera</p></td>
<td><p>Interfaz de Servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Cualquiera</p></td>
<td><p>Interfaz de Servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


> [!IMPORTANT]  
> Microsoft Office Communications Server 2007 requiere una configuración ligeramente diferente. El intervalo de puertos TCP y UDP de 50.000 a 59.999 debe tener la entrada y la salida abiertas. Este requisito solo se aplica a Office Communicator 2007. Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013 solo requieren la salida abierta del intervalo de TCP de 50.000 a 59.999.



## Requisitos de NAT para el acceso de usuarios externos

NAT suele ser una función de enrutamiento, pero los dispositivos más recientes, como los firewalls e incluso los equilibradores de carga de hardware, pueden configurarse para NAT. En lugar de centrarse en el dispositivo en que se ejecuta NAT, en este tema se describe el comportamiento necesario de NAT.

El Lync Server 2013  software de comunicaciones no admite NAT para tráfico procedente de la interfaz perimetral interna ni hacia ella, pero para la interfaz perimetral externa, se requiere el siguiente comportamiento de NAT.

> [!IMPORTANT]  
> Debe configurar NAT simétrico para el tráfico entrante y saliente. NAT simétrico es la tecnología NAT descrita en este tema.



En esta documentación se usan los acrónimos ChangeDST y ChangeSRC en tablas y dibujos para definir el siguiente comportamiento necesario:

  - **ChangeDST**   Proceso de cambio de la dirección IP de destino en paquetes destinados a la red que usa NAT. También se denomina transparencia, enrutamiento de puerto, modo NAT de destino o modo NAT medio.

  - **ChangeSRC**   Proceso de cambio de la dirección IP de origen en paquetes que salen de la red que usa NAT. También se denomina proxy, NAT segura, NAT con estado, NAT de origen o modo NAT completo.

Con independencia de la convención de nomenclatura usada, el comportamiento de NAT necesario para la interfaz externa del servidor perimetral es el siguiente:

  - Para tráfico desde Internet hacia la interfaz perimetral externa:
    
      - Cambiar la dirección IP de destino del paquete entrante de la dirección IP pública de la interfaz perimetral externa a la dirección IP traducida de la interfaz perimetral externa.
    
      - Dejar la dirección IP de origen intacta para que haya una ruta de retorno para el tráfico.

  - Para tráfico desde la interfaz perimetral externa hacia Internet:
    
      - Cambiar la dirección IP de origen del paquete que sale de la interfaz perimetral externa, de la dirección IP traducida a la dirección IP pública de la interfaz perimetral externa, para que la dirección IP del servidor perimetral no quede expuesta y porque se trata de una dirección IP que no se puede enrutar.
    
      - Dejar la dirección IP de destino intacta en los paquetes salientes.

En la figura siguiente se muestra la distinción entre cambiar la dirección IP de destino (ChangeDST) para el tráfico entrante y cambiar la dirección IP de origen (ChangeSRC) para el tráfico saliente con el servidor perimetral A/V como ejemplo.

**Cambio de la dirección IP de destino (ChangeDST) para el tráfico entrante y cambio de la dirección IP de origen para el tráfico saliente (ChangeSRC)**

![Cambio de direcciones IP de destino/origen](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Cambio de direcciones IP de destino/origen")

Los puntos clave son los siguientes:

  - Para el tráfico entrante al servidor que ejecuta el Servicio perimetral A/V, la dirección IP de origen no cambia pero la dirección IP de destino cambia de 131.107.155.30 a la dirección IP traducida de 10.45.16.10.

  - Para el tráfico saliente del servidor que ejecuta el Servicio perimetral A/V que vuelve a la estación de trabajo, la dirección IP de origen cambia de la dirección IP pública del servidor a la dirección IP pública del servidor que ejecuta el Servicio perimetral A/V. La dirección IP de destino permanece en la dirección IP pública de la estación de trabajo. Después de que el paquete sale del primer dispositivo NAT saliente, la regla del dispositivo NAT cambia la dirección IP de origen, de la dirección IP de la interfaz externa del servidor que ejecuta el Servicio perimetral A/V (10.45.16.10) a su dirección IP pública (131.107.155.30).

