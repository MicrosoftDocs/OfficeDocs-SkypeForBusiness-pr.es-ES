---
title: 'Lync Server 2013: determinar los requisitos de los puertos y el Firewall de A/V externos'
description: 'Lync Server 2013: determinar los requisitos de los puertos y el Firewall de A/V externos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38c2a8c1e8e332a4a1e65adb87a1e962e82941c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550936"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>Determinación de los requisitos de los puertos y el Firewall de A/V externos para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-29_

La comunicación de audio y vídeo (A/V) puede ser compleja. Debido a la naturaleza de los protocolos que se usan en A/V y cómo los clientes y servidores usan los protocolos, se garantiza una sección especial para explicar las diferencias entre las versiones de cliente y servidor.

Use la siguiente tabla de puertos y firewall de a/V para determinar los requisitos de firewall y los puertos que se abrirán. A continuación, revise la terminología de traducción de direcciones de red (NAT) porque NAT puede implementarse de formas muy distintas. Para obtener un ejemplo detallado de la configuración del puerto del firewall, consulte las arquitecturas de referencia en [escenarios para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>Uso de protocolos generales para UDP y TCP en el tráfico de audio, vídeo y multimedia

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
<p>Protocolo de capa de transporte necesario para compartir aplicaciones con Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013</p>
<p>Protocolo de capa de transporte necesario para la transferencia de archivos a Lync Server 2010 y Lync Server 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>Requisitos de puerto de firewall A/V para el acceso de usuarios externos

Los requisitos de puerto de Firewall para las interfaces SIP y de conferencia externas (y internas) son coherentes, independientemente de la versión de su cliente o de la versión del asociado de Federación.

No sucede lo mismo con la interfaz perimetral externa de audio y vídeo. Para la Federación con Office Communications Server 2007, el servicio perimetral A/V necesita que las reglas del firewall externo permitan que el tráfico RTP/TCP y RTP/UDP del intervalo de puertos de 50.000 a 59.999 fluya en ambas direcciones. En la tabla anterior se supone que Lync Server 2013 es el socio de Federación principal y que se ha configurado para comunicarse con uno de los otros tipos de asociados de Federación que aparecen en la lista.

La configuración del intervalo de puertos de audio y vídeo de 50000-59.999 debe tener en cuenta que el intervalo de puertos contendrá los puertos de origen para las comunicaciones con los socios de Federación. En detalle, tenga en cuenta que se inicia una comunicación desde un socio de Federación. La comunicación desde los puertos del servicio perimetral A/V del intervalo de 50000-59.999 se conectará al puerto TCP 443 esperado del servicio perimetral A/V del asociado. Por el contrario, el tráfico entrante a su puerto del servicio perimetral a/V TCP 443 tendrá un puerto de origen en el rango de 50000 59.999.

Los diferentes firewalls y directivas para la administración de firewalls pueden requerir que solo se configuren reglas de destino, o bien es posible que necesite configurar tanto el origen como el destino. Si sus requisitos son solo para puertos de destino, los requisitos de audio y vídeo son los siguientes:


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
<td><p>Interfaz del servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interfaz del servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Cualquiera</p></td>
<td><p>Interfaz del servicio perimetral A/V</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Cualquiera</p></td>
<td><p>Interfaz del servicio perimetral A/V</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


Si las directivas requieren definiciones de reglas de Firewall de entrada y de salida, los requisitos de audio y vídeo son los siguientes:


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
<td><p>Interfaz del servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>TCP 50000-59.999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interfaz del servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Cualquiera</p></td>
<td><p>Interfaz del servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Cualquiera</p></td>
<td><p>Interfaz del servicio perimetral A/V</p></td>
<td><p>Cualquiera</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Microsoft Office Communications Server 2007 requiere una configuración ligeramente distinta. El intervalo de puertos TCP y UDP de 50000-59.999 debe estar abierto entrante y saliente. Este requisito es solo para Office Communicator 2007. Office Communications Server 2007 R2, Lync Server 2010 y Lync Server 2013 solo requieren el intervalo TCP 50000-59.999 abierto saliente.



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>Requisitos de NAT para el servicio perimetral

Si elige configurar direcciones IP privadas no enrutables para el servicio perimetral, se aplicarán los siguientes requisitos de NAT:

  - NAT solo se puede usar con el equilibrio de carga de DNS. NAT no es compatible con una topología perimetral de equilibrio de carga de hardware (HLB).

  - NAT solo se puede usar en la interfaz perimetral externa. NAT no es compatible con la interfaz perimetral interna.

  - La NAT debe ser simétrica para el tráfico entrante y saliente.
    
  - Para el tráfico de Internet, NAT debe cambiar la dirección IP de destino de la dirección IP pública habilitada para NAT del servicio perimetral a/V a su dirección IP externa. La dirección IP de origen debe permanecer intacta, de modo que el servicio perimetral A/V pueda encontrar la ruta de medios óptima.
  
  Por ejemplo, en la dirección de entrada en la figura siguiente, la dirección IP pública 131.107.155.30 se cambió a la dirección IP externa (privada) 10.45.16.10. La dirección IP de origen permanece inalterada.
  
  - Para el tráfico del servicio perimetral a/V a Internet, NAT debe cambiar la dirección IP de origen de la dirección IP externa del servicio perimetral a/V a la dirección IP pública habilitada para NAT.

Por ejemplo, en la dirección de salida de la figura siguiente, la dirección IP externa (privada) 10.45.16.10 se cambió a la dirección IP pública 131.107.155.30.

**En la siguiente figura se muestra la forma en que NAT cambia la dirección IP de destino para el tráfico entrante y la dirección IP de origen para el tráfico saliente.**

![Cambio de direcciones IP de destino/origen](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Cambio de direcciones IP de destino/origen")

Los puntos clave son los siguientes:

  - Tráfico entrante al servidor que ejecuta el servicio perimetral A/V, la dirección IP de origen no cambia, pero la dirección IP de destino cambia de 131.107.155.30 a la dirección IP traducida de 10.45.16.10.

  - El tráfico saliente del servidor que ejecuta el servicio perimetral a/V a la estación de trabajo, la dirección IP de origen cambia desde la dirección IP pública del servidor a la dirección IP pública del servidor que ejecuta el servicio perimetral A/V. La IP de destino sigue siendo la dirección IP pública de la estación de trabajo. Una vez que el paquete deja el primer dispositivo NAT saliente, la regla del dispositivo NAT cambia la dirección IP de origen del servidor que ejecuta la dirección IP de la interfaz externa del servicio perimetral A/V (10.45.16.10) a su dirección IP pública (131.107.155.30).

</div>

</div>

<span> </span>

</div>

</div>

</div>

