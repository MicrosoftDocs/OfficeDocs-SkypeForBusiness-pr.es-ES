---
title: 'Lync Server 2013: información general sobre los tipos de direcciones IP'
description: 'Lync Server 2013: información general sobre los tipos de direcciones IP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81492b2e006a6f44f6deb78e6a0560f6e319992f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559226"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Información general sobre los tipos de direcciones IP para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-01-29_

Tiene tres opciones para configurar las direcciones IP en Lync Server 2013. Puede configurar Lync Server 2013 para que admita solo IP versión 4 (IPv4), solo IP versión 6 (IPv6) o una combinación de ambas (conocidas como *pila dual*). Cada tipo de configuración entraña varios aspectos que debe tener en cuenta:

  - **Solo IPv4**     IPv6 se creó porque el mundo se está quedando sin direcciones IPv4. En última instancia, IPv6 será totalmente compatible en todo el mundo, pero en este momento, muchas compañías y dispositivos que su empresa puede que necesiten comunicarse con no son compatibles con IPv6, y es posible que no lo hagan durante algún tiempo. Una configuración de solo IPv4 le ayudará a asegurarse de que la implementación de Lync Server se puede comunicar con la mayoría de los dispositivos existentes.

  - **Solo IPv6**     Por el contrario, una implementación completa de IPv6, en este momento, excluirá la comunicación con muchos dispositivos existentes.

  - **Pila dual**     Pila dual es una red donde están habilitadas las direcciones IPv4 e IPv6. Esta configuración se admite en Lync Server 2013 porque, en la mayoría de los casos, la transición de Full-IPv4 a Full-IPv6 tardará varios años.

En las secciones siguientes se resume la compatibilidad entre estas tres configuraciones para varias características de Lync Server.

<div>


> [!NOTE]  
> La configuración de tipo solo IPv6 en el cliente o el servidor solo se admite en entornos de ensayo y con fines de validación, no se admite en implementaciones de producción.



</div>

<div>

## <a name="client-registration"></a>Registro de clientes


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Red de extremo de clientes</th>
<th>Red del servidor</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Pila dual</p></td>
</tr>
<tr class="odd">
<td><p>Pila dual</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Pila dual</p></td>
<td><p>Pila dual</p></td>
</tr>
<tr class="odd">
<td><p>Pila dual</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Pila dual</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a>Cliente de punto a punto

Las comunicaciones de punto a punto incluyen audio, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos. Después de que se hayan registrado con éxito ambos clientes, se admiten las combinaciones siguientes.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Extremo de cliente 1</th>
<th>Extremo de cliente 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Pila dual</p></td>
</tr>
<tr class="odd">
<td><p>Pila dual</p></td>
<td><p>Pila dual</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Pila dual</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a>Conferencia

Las conferencias incluyen audio y vídeo, uso compartido de aplicaciones y colaboración de datos (pizarra y uso compartido de archivos).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Red de extremo de cliente</th>
<th>Red del servidor</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Pila dual</p></td>
</tr>
<tr class="odd">
<td><p>Pila dual</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Pila dual</p></td>
<td><p>Pila dual</p></td>
</tr>
<tr class="odd">
<td><p>Pila dual</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Pila dual</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a>Servidor de mediación/RTC

Lync Server 2013 no admite el desvío de medios para llamadas de red telefónica conmutada (RTC) si el tráfico se realiza a través de una interfaz IPv6. Si se requiere la omisión de medios, se recomienda que la puerta de enlace RTC se configure con IPv4.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Interfaz principal*</th>
<th>Interfaz RTC (en el servidor de mediación)</th>
<th>Configuración de la puerta de enlace RTC</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>Pila dual</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Pila dual</p></td>
<td><p>Pila dual</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>Pila dual</p></td>
<td><p>Pila dual</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\* La interfaz principal es la interfaz que se comunica con los componentes de Lync Server.

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>Comunicaciones de punto a punto de usuarios remotos

Las comunicaciones de punto a punto con usuarios remotos incluyen mensajería instantánea, audio y vídeo, uso compartido de aplicaciones y transferencia de archivos.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Red de usuarios remotos</th>
<th>Servidor perimetral (perímetro externo)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Pila dual</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>Pila dual</p></td>
<td><p>Pila dual</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Pila dual</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a>Configuración del grupo de servidores front-end y del grupo de servidores perimetrales

En la siguiente tabla se muestra la matriz de compatibilidad entre el grupo de servidores front-end y el grupo de servidores perimetrales internos.

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>Matriz del grupo de servidores front-end y del grupo de servidores perimetrales (perímetro interno)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>Grupo de servidores perimetrales: IPv4</strong></p></td>
<td><p><strong>Grupo de servidores perimetrales: pila dual</strong></p></td>
<td><p><strong>Grupo de servidores perimetrales: IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Grupo de servidores front-end: IPv4</strong></p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p><strong>Grupo de servidores front-end: pila dual</strong></p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p><strong>Grupo de servidores front-end: IPv6</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>Sí*</p></td>
</tr>
</tbody>
</table>


\* Use esta combinación únicamente en un entorno de laboratorio.

La tabla siguiente es una matriz de combinaciones admitidas de las interfaces perimetrales interna y externa.

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>Matriz del grupo de servidores perimetrales (perímetro interno) y del grupo de servidores perimetrales (perímetro externo)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>Grupo de servidores perimetrales (perímetro externo): IPv4</strong></p></td>
<td><p><strong>Grupo de servidores perimetrales (perímetro externo): pila dual</strong></p></td>
<td><p><strong>Grupo de servidores perimetrales (perímetro externo): IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Grupo de servidores perimetrales (perímetro interno): IPv4</strong></p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p><strong>Grupo de servidores perimetrales (perímetro interno): pila dual</strong></p></td>
<td><p>No</p></td>
<td><p>Sí</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p><strong>Grupo de servidores perimetrales (perímetro interno): IPv6</strong></p></td>
<td><p>No</p></td>
<td><p>No</p></td>
<td><p>Sí*</p></td>
</tr>
</tbody>
</table>


\* Use esta combinación únicamente en un entorno de laboratorio.

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>Compatibilidad avanzada de Enterprise Voice para IPv6

Las implementaciones que incluyen el control de admisión de llamadas (CAC), Enhanced 9-1-1 (E9-1-1) o la omisión de medios se deben configurar como implementaciones de solo IPv4 o de pila dual.

<div>


> [!NOTE]  
> En una implementación de pila dual, incluso si un cliente de Lync se conecta a un Lync Server mediante IPv6, Lync hará un mejor esfuerzo para asignar una dirección IPv4 adecuada para admitir E9-1-1.



</div>

No se admite el servicio de información de ubicación con direcciones IPv6.

La mensajería unificada (MU) de Exchange no admite IPv6. Para la MU de Exchange, asegúrese de que la resolución de DNS no devuelve una dirección IPv6. El uso de IPv6 puede provocar un fallo cuando se envían las llamadas al correo de voz.

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>Otra compatibilidad con características de Lync Server 2013 para IPv6

Además de las características y los componentes mencionados anteriormente, Lync Server 2013 admite IPv6 para las siguientes características:

  - **Chat persistente**
    
    Configure IPv6 para chat persistente mediante el generador de topologías. Para obtener más información sobre cómo configurar chat persistente, consulte la documentación de implementación del servidor de chat persistente.

  - **Informes de Calidad de la experiencia (QoE) y registro de detalles de llamadas (CDR)**
    
    Los informes de supervisión incluyen la dirección IP cuando se guarda en la base de datos del servidor de supervisión, tanto del tipo IPv4 como IPv6.

</div>

</div>

<span> </span>

</div>

</div>

</div>

