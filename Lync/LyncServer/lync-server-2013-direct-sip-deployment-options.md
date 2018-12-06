---
title: 'Lync Server 2013: Opciones de implementación SIP directa'
TOCTitle: Opciones de implementación SIP directa
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48275888
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Opciones de implementación SIP directa en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Este tema contiene ejemplos de topologías para implementar conexiones SIP directas.

## Lync Server independiente

Si su organización usa una de las implementaciones descritas en esta sección, puede usar Lync Server 2013 como la única solución de telefonía para toda una organización o parte de ella. En esta sección se describen detalladamente las implementaciones siguientes:

  - **Implementación incremental:**. En esta opción, se da por supuesto que tiene una infraestructura central de conmutación (PBX) existente y que piensa introducir Telefonía IP empresarial de forma incremental en grupos o equipos más pequeños dentro de su organización.

  - **Implementación de Lync Server con VoIP solo:** en esta opción, se presupone que se está planteando la implementación de Telefonía IP empresarial en un sitio que no tiene la infraestructura de telefonía tradicional.

## Implementación incremental

En la implementación departamental, Lync Server 2013 es la única solución de telefonía para departamentos o equipos individuales, mientras que el resto de los usuarios de la organización continúa usando un PBX. Esta estrategia de implementación incremental es un modo de introducir la telefonía IP en la empresa a través de programas piloto controlados. Se migran a Telefonía IP empresarial los grupos de trabajo cuyas necesidades de comunicación se satisfacen mejor con las comunicaciones unificadas de Microsoft, mientras que los demás usuarios siguen con el PBX existente. Se pueden migrar a Telefonía IP empresarial más grupos de trabajo según sea necesario.

La opción incremental se recomienda para grupos de usuarios claramente definidos que tienen requisitos de comunicación en común y se prestan a la administración centralizada. Esta opción también es efectiva para los equipos o departamentos que están dispersos por amplias áreas geográficas y para los que el ahorro en gastos de llamadas de larga distancia puede ser significativo. De hecho, esta opción es útil para crear equipos virtuales cuyos miembros estén dispersos por todo el planeta. Estos equipos se pueden crear, modificar o disolver rápidamente según cambien las necesidades empresariales.

En la ilustración siguiente, se muestra la topología genérica para la implementación de Telefonía IP empresarial detrás de un PBX. Esta es la topología recomendada para la implementación incremental.

**Opción de implementación incremental**

![Diagrama de opción de migración departamental](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagrama de opción de migración departamental")


> [!NOTE]
> Si está conectando la implementación de Lync Server a un socio directo SIP certificado, no es necesaria ninguna puerta de enlace red telefónica conmutada (RTC) entre el Servidor de mediación y el PBX. Para ver una lista de los socios directos SIP certificados, consulte el sitio web del Programa de interoperabilidad abierta de comunicaciones unificadas de Microsoft, en <A href="http://go.microsoft.com/fwlink/?linkid=203309%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=203309&amp;clcid=0xC0A</A>.




> [!NOTE]
> La ruta de acceso a medios que se muestra en esta ilustración tiene habilitado el desvío de medios (la configuración recomendada). Si decide deshabilitar el desvío de medios, la ruta de acceso a medios se enrutará a través de la Servidor de mediación.



En esta topología, se habilitan determinados departamentos o grupos de trabajo para Telefonía IP empresarial. Una puerta de enlace RTC vincula el grupo de trabajo habilitado para voz sobre Internet (VoIP) al PBX. Los usuarios habilitados para Telefonía IP empresarial, incluidos los empleados remotos, se comunican a través de la red IP. Las llamadas realizadas por los usuarios de Telefonía IP empresarial a la RTC y a los compañeros de trabajo no habilitados para Telefonía IP empresarial se enrutan a la puerta de enlace RTC correspondiente. Las llamadas procedentes de los compañeros que todavía usan el sistema PBX, o de usuarios de la RTC, se enrutan a la puerta de enlace RTC, que las transfiere a Lync Server para su enrutamiento.

Hay dos configuraciones recomendadas para conectar Telefonía IP empresarial con una infraestructura PBX existente por motivos de interoperabilidad: Telefonía IP empresarial detrás del PBX y Telefonía IP empresarial delante del PBX.

## Enterprise Voice detrás del PBX

Cuando se implementa Telefonía IP empresarial detrás del PBX, todas las llamadas de la RTC llegan al PBX, que enruta las llamadas a los usuarios de Telefonía IP empresarial a una puerta de enlace RTC y llama a los usuarios de PBX al PBX.

## Enterprise Voice delante del PBX

Cuando se implementa Telefonía IP empresarial delante del PBX, todas las llamadas llegan a la puerta de enlace RTC, que enruta las llamadas a los usuarios de Telefonía IP empresarial a Lync Server y llama a los usuarios de PBX al PBX. Las llamadas a la RTC procedentes de los usuarios de Telefonía IP empresarial y PBX se enrutan a través de la red IP a la puerta de enlace RTC más rentable. En la siguiente tabla se muestran las ventajas y desventajas de esta configuración.

### Ventajas y desventajas de implementar Telefonía IP empresarial delante de PBX

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ventajas</th>
<th>Inconvenientes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PBX sigue prestando servicio a los usuarios no habilitados para Telefonía IP empresarial.</p></td>
<td><p>Es posible que las puertas de enlace existentes no admitan las características o la capacidad que desee.</p></td>
</tr>
<tr class="even">
<td><p>PBX administra todos los dispositivos anteriores.</p></td>
<td><p>Necesita un tronco de la puerta de enlace al PBX y de la puerta de enlace al Servidor de mediación. Es posible que necesite más troncos del proveedor de servicio.</p></td>
</tr>
<tr class="odd">
<td><p>Los usuarios de Telefonía IP empresarial mantienen los mismos números de teléfono.</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


## Implementación de Lync Server con VoIP solo

Telefonía IP empresarial brinda a las nuevas empresas y también las oficinas nuevas de empresas ya existentes, la oportunidad de implementar una solución VoIP completa, sin que tengan que preocuparse por la integración de PBX ni incurrir en los gastos considerables de implementación y mantenimiento de una infraestructura PBX IP. Esta solución admite tanto los usuarios locales como los remotos.

En esta implementación, todas las llamadas se enrutan a través de la red IP. Las llamadas a la RTC se enrutan a la puerta de enlace RTC correspondiente. Lync 2013 o Lync Phone Edition sirve de softphone. El control remoto de llamadas no está disponible ni es necesario, porque no hay teléfonos PBX que deban controlar los usuarios. Los servicios de operador automático y correo de voz están disponibles mediante la implementación opcional de Mensajería unificada de Exchange (UM).


> [!NOTE]
> Además de la infraestructura de red necesaria para admitir Lync Server 2013, la implementación de solo VoIP puede usar una puerta de enlace pequeña y cualificada para admitir dispositivos analógicos y equipos de fax.



La ilustración siguiente muestra una topología típica de una implementación de solo VoIP.

**Opción de implementación de solo VoIP**

![Opción de implementación en entorno virgen](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Opción de implementación en entorno virgen")


> [!NOTE]
> La ruta de acceso a medios que se muestra en esta ilustración tiene habilitado el desvío de medios (la configuración recomendada). Si decide deshabilitar el desvío de medios, la ruta de acceso a medios se enrutará a través de la Servidor de mediación.


