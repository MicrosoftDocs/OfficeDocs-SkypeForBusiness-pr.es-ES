---
title: 'Lync Server 2013: Información general sobre los tipos de direcciones IP'
TOCTitle: Información general sobre los tipos de direcciones IP para Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48277109
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general sobre los tipos de direcciones IP en Lync Server para Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

Al configurar direcciones IP en Lync Server 2013, tendrá tres opciones. Puede configurar Lync Server 2013 para admitir solo la versión 4 de IP (IPv4), solo la versión 6 de IP (IPv6) o una combinación de ambas versiones (conocida como *pila dual* ). Cada tipo de configuración entraña varios aspectos que debe tener en cuenta:

  - **Solo IPv4 :** IPv6 se creó porque se estaban agotando las direcciones IPv4. Con el paso del tiempo, IPv6 será completamente compatible en todo el mundo, pero en este momento muchas empresas y dispositivos con los que su empresa necesitará comunicarse aún no admiten IPv6 y pueden tardar mucho en admitirlo. Una configuración de solo IPv4 le garantizará que su implementación de Lync Server se pueda comunicar con la mayoría de dispositivos existentes.

  - **Solo IPv6 :** por el contrario, en este momento una implementación completa de IPv6 excluirá la comunicación con muchos dispositivos existentes.

  - **Pila dual :** la pila dual es una red habilitada tanto las direcciones IPv4 como IPv6. Lync Server 2013 es compatible con esta configuración porque en la mayoría de los casos la transición de solo IPv4 a solo IPv6 tardará varios años.

En los apartados siguientes se resume la compatibilidad entre estas tres configuraciones para varias características de Lync Server.


> [!NOTE]
> La configuración de tipo solo IPv6 en el cliente o el servidor solo se admite en entornos de ensayo y con fines de validación, no se admite en implementaciones de producción.



## Registro de clientes


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


## Cliente de punto a punto

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


## Conferencia

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


## Servidor de mediación/RTC

Lync Server 2013 no admite la omisión de medios para las llamadas de la red telefónica conmutada (RTC) si el tráfico se produce a través de una interfaz IPv6. Si se requiere la omisión de medios, se recomienda que la puerta de enlace RTC se configure con IPv4.


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

## Comunicaciones de punto a punto de usuarios remotos

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


## Configuración del grupo de servidores front-end y del grupo de servidores perimetrales

La tabla siguiente muestra la matriz de compatibilidad entre el grupo de servidores Servidor front-end y el grupo de servidores Servidor perimetral interno.

### Matriz del grupo de servidores front-end y del grupo de servidores perimetrales (perímetro interno)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><strong>Grupo de servidores perimetrales: IPv4</strong></p></td>
<td><p><strong>Grupo de servidores perimetrales: pila dual</strong></p></td>
<td><p><strong>Grupo de servidores perimetrales: IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Grupo de servidores front-end: IPv4</strong></p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>N.º</p></td>
</tr>
<tr class="odd">
<td><p><strong>Grupo de servidores front-end: pila dual</strong></p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>N.º</p></td>
</tr>
<tr class="even">
<td><p><strong>Grupo de servidores front-end: IPv6</strong></p></td>
<td><p>N.º</p></td>
<td><p>N.º</p></td>
<td><p>Sí</p></td>
</tr>
</tbody>
</table>


\* Use esta combinación únicamente en un entorno de ensayo.

La tabla siguiente es una matriz de combinaciones admitidas de las interfaces perimetrales interna y externa.

### Matriz del grupo de servidores perimetrales (perímetro interno) y del grupo de servidores perimetrales (perímetro externo)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><strong>Grupo de servidores perimetrales (perímetro externo): IPv4</strong></p></td>
<td><p><strong>Grupo de servidores perimetrales (perímetro externo): pila dual</strong></p></td>
<td><p><strong>Grupo de servidores perimetrales (perímetro externo): IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Grupo de servidores perimetrales (perímetro interno): IPv4</strong></p></td>
<td><p>Sí</p></td>
<td><p>Sí</p></td>
<td><p>N.º</p></td>
</tr>
<tr class="odd">
<td><p><strong>Grupo de servidores perimetrales (perímetro interno): pila dual</strong></p></td>
<td><p>N.º</p></td>
<td><p>Sí</p></td>
<td><p>N.º</p></td>
</tr>
<tr class="even">
<td><p><strong>Grupo de servidores perimetrales (perímetro interno): IPv6</strong></p></td>
<td><p>N.º</p></td>
<td><p>N.º</p></td>
<td><p>Sí</p></td>
</tr>
</tbody>
</table>


\* Use esta combinación únicamente en un entorno de ensayo.

## Compatibilidad avanzada de Telefonía IP empresarial para IPv6

Las implementaciones que incluyen el control de admisión de llamadas (CAC), Enhanced 9-1-1 (E9-1-1) o la omisión de medios se deben configurar como implementaciones de solo IPv4 o de pila dual.


> [!NOTE]
> En una implementación de pila dual, incluso si un cliente de Lync se conecta a un Lync Server mediante IPv6, Lync hará un gran esfuerzo para asignar una dirección IPv4 adecuada que admita E9-1-1.



No se puede usar Servicio de información de ubicaciones con direcciones IPv6.

La mensajería unificada (MU) de Exchange no admite IPv6. Para la MU de Exchange, asegúrese de que la resolución de DNS no devuelve una dirección IPv6. El uso de IPv6 puede provocar un fallo cuando se envían las llamadas al correo de voz.

## Compatibilidad con otras características de Lync Server 2013 para IPv6

Además de las características y los componentes mencionados anteriormente, Lync Server 2013 admite IPv6 para las siguientes características:

  - **Chat persistente**
    
    Puede configurar IPv6 para Chat persistente utilizando Generador de topologías. Para obtener información detallada acerca de la configuración de Chat persistente, consulte la documentación acerca de la implementación del servidor de chat persistente.

  - **Informes de Calidad de la experiencia (QoE) y registro de detalles de llamadas (CDR)**
    
    Los informes de supervisión incluyen la dirección IP cuando se guarda en la base de datos del servidor de supervisión, tanto del tipo IPv4 como IPv6.

