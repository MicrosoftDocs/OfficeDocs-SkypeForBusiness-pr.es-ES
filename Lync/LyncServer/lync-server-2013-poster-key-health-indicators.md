---
title: Indicadores clave de estado de Lync Server 2013
TOCTitle: 'Póster: Indicadores clave de estado'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084820
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Indicadores clave de estado de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Este artículo es complementario al póster [Indicadores clave de estado: las bases para el mantenimiento de los servidores de Lync en buen estado](http://go.microsoft.com/fwlink/?linkid=391838), que puede descargar desde el Centro de descarga.

![Póster sobre la solución de problemas mediante los datos de KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Póster sobre la solución de problemas mediante los datos de KHI")

Puede usar este póster para conocer los indicadores clave de estado (KHI), los contadores de rendimiento con umbrales dirigidos a detectar problemas en la experiencia de los usuarios. Recopilar datos de KHI suele ser el primer paso para implementar la Metodología de calidad de llamadas (CQM), que se centra en garantizar una experiencia de audio de calidad para los usuarios de Lync.

Si tiene alguna pregunta sobre el uso de CQM, puede enviarla a cqmfeedback@microsoft.com.

En el póster se explican los siguientes puntos:

  - ¿Qué son los indicadores clave de estado?

  - Recopilar datos de KHI

  - Flujo de solución para todos los roles de servidor

  - Glosario

  - Servidores front end

  - Servidores SQL Server back end

  - Servidores de mediación

  - Servidores perimetrales

## ¿Qué son los indicadores clave de estado?

Los indicadores clave de estado (KHI) son contadores de rendimiento con umbrales destinados a detectar problemas en la experiencia de los usuarios. Recopilar datos de KHI suele ser el primer paso para implementar la Metodología de calidad de llamada (CQM), una metodología centrada en garantizar una experiencia de audio de calidad para los usuarios de Lync.

Los KHI se utilizan junto con las soluciones de supervisión estándar de Lync (por ejemplo, System Center Operations Manager, transacciones sintéticas y servidores de supervisión), pero no las sustituyen.

Recopile los contadores de rendimiento KHI y rellene las hojas de cálculo KHI distribuidas junto con la guía de conexión de redes para obtener un boletín de puntuaciones que nos ayude a determinar el estado del servidor de una implementación de Lync. La información de las hojas de cálculo le será de ayuda a la hora de reparar el entorno y de conocer mejor otros factores que intervienen. Analice los KHI mensualmente e incorpórelos a los procesos operativos de la implementación que ya tiene en marcha.

Descargue la [Guía para la conexión de redes de Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677) para ver la lista completa de KHI y las hojas de cálculo relacionadas.

## Recopilar datos de KHI

1.  Ejecute el script de KHI incluido en la Guía para la conexión de redes de Lync Server en cada servidor Lync. Se creará un recopilador de datos dentro de cada monitor de rendimiento y le pondrá el nombre KHI. De manera predeterminada, se sondearán los datos cada 15 segundos.

2.  Antes de comenzar la jornada laboral, vaya a cada servidor de Lync e inicie el recopilador de datos.

3.  Al final del día, detenga el recopilador de datos de KHI y copie los datos en una ubicación central.

4.  Después de utilizar el monitor de rendimiento para rellenar la hoja de datos de KHI incluida en la Guía para la conexión de redes de Lync Server, compare los resultados con los valores recomendados.

## Flujo de solución para todos los roles de servidor

Para cada servidor de la implementación de Lync, comience por comprobar que el rendimiento del sistema y el estado del componente del servidor es igual o mayor que el nivel deseado. A continuación, mire los indicadores relacionados con el rol del servidor en la totalidad de la implementación de Lync.

Begin by collecting KHI  Performance Data for all servers. For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets. If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation. Component health for all roles is defined as:

  - Utilización de la CPU \< 80%

  - Escritura media en disco \< 10 ms

  - Lectura media en disco \< 10 ms

  - Available memory  \>20% System Total MB

  - Longitud de cola de red \< 2

  - Paquetes descartados (entrada / salida) = 0

## Glosario

Los términos y acrónimos siguientes se utilizan en este póster:

AS MCU = Unidad de control multipunto para el uso compartido de aplicaciones

AV MCU = Unidad de control multipunto de audio y vídeo

IM MCU = Unidad de control multipunto de mensajería instantánea

UCWA = API web de comunicaciones unificadas

AV Edge = Transversal de audio y vídeo vía perímetro

AV Auth = Autenticación de audio y vídeo

Pila SIP = Contiene la implementación SIP de Lync

Data Proxy = Usado en las conferencias perimetrales

LySS = Servicio de almacenamiento de Lync

## Servidores front end

Los siguientes objetivos KHI recomendados son específicos de servidores front end además del estado de componentes básicos:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Área funcional</th>
<th>Métricas objetivo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AS/AV/IM MCU</p></td>
<td><p>Estado MCU &lt;2</p></td>
</tr>
<tr class="even">
<td><p>Componentes web</p></td>
<td><p>Tiempos máximos de espera de AD en expansión de lista de distribución &lt;0</p>
<p>Errores de ABWQ = 0</p>
<p>Errores de LIS = 0</p>
<p>Errores de autenticación &lt; 1/s</p>
<p>Solicitudes de ASP.NET v4 rechazadas = 0</p></td>
</tr>
<tr class="odd">
<td><p>Pila SIP</p></td>
<td><p>Procesamiento medio de mensajes entrantes &lt; 1 s</p>
<p>Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</p>
<p>Latencia cola &lt; 100 ms</p>
<p>Latencia Sproc &lt; 100 ms</p>
<p>Solicitudes aceleradas = 0</p>
<p>Errores de autenticación &lt; 1/s</p>
<p>Tiempo de espera excedido para mensajes entrantes &lt; 2</p>
<p>Espera media de mensajes entrantes &lt; 1 s</p>
<p>Conexiones controladas por flujo &lt; 2</p>
<p>Retraso medio cola de salida &lt; 2 s</p></td>
</tr>
<tr class="even">
<td><p>LySS</p></td>
<td><p>% de espacio usado por la base de datos del servicio de almacenamiento &lt; 80</p>
<p>N.º de réplicas errores de replicación = 0</p>
<p>N.º de eventos de pérdida de datos = 0</p></td>
</tr>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Esperanza de vida de la página &gt; 300 s</p>
<p>Solicitudes en lote / s &lt; 2500</p></td>
</tr>
</tbody>
</table>


## Servidores SQL Server back end

Los siguientes objetivos KHI recomendados son específicos de servidores de SQL Server además del estado de componentes básicos:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Área funcional</th>
<th>Métricas objetivo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SQL</p></td>
<td><p>Esperanza de vida de la página &gt; 300 s</p>
<p>Solicitudes en lote / s &lt; 2500</p></td>
</tr>
</tbody>
</table>


## Servidores de mediación

Los siguientes objetivos KHI recomendados son específicos de servidores de mediación además del estado de componentes básicos:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Área funcional</th>
<th>Métricas objetivo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servicio del servidor de mediación</p></td>
<td><p>Índice de error de llamadas de carga = 0</p>
<p>Llamadas fallidas a causa de Proxy &lt;10</p>
<p>Llamadas fallidas a causa de puerta de enlace &lt;10</p>
<p>Llamadas (entrada o salida) rechazadas = 0</p>
<p>Candidatos medios ausentes = 0</p>
<p>Errores en comprobación de conectividad de medios = 0</p></td>
</tr>
</tbody>
</table>


## Servidores perimetrales

Los siguientes objetivos KHI recomendados son específicos de servidores perimetrales además del estado de componentes básicos:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Área funcional</th>
<th>Métricas objetivo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorización AV</p></td>
<td><p>Solicitudes incorrectas &lt; 20/s</p></td>
</tr>
<tr class="even">
<td><p>Perimetral AV</p></td>
<td><p>Errores en autenticación &lt;20/s</p>
<p>Errores en asignación &lt;20/s</p>
<p>Paquetes perdidos &lt;300/s</p></td>
</tr>
<tr class="odd">
<td><p>Proxy de datos</p></td>
<td><p>Conexiones de servidor acelerado &lt; 3</p>
<p>El sistema está acelerado &lt;1</p></td>
</tr>
<tr class="even">
<td><p>Pila SIP</p></td>
<td><p>Conexiones por encima del límite perdidas &lt; 1</p>
<p>Tiempo de espera excedido para envíos &lt;10</p>
<p>Conexiones controladas por flujo &lt;100</p>
<p>Solicitudes entrantes perdidas &lt; 1/s</p>
<p>Procesamiento medio de mensajes &lt; 3 s</p></td>
</tr>
</tbody>
</table>


## Vea también

#### Otros recursos

[Guía para la conexión de redes de Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Indicadores de estado clave: la base para el mantenimiento de Lync Server en buen estado](http://go.microsoft.com/fwlink/?linkid=391838)  
[Metodología para la calidad de llamadas en Lync](http://go.microsoft.com/fwlink/?linkid=391841)

