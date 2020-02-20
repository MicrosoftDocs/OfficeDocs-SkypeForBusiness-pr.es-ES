---
title: 'Lync Server 2013: administrar ubicaciones para puertas de enlace de ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17fa27b82260a05ded5ca025d56005c864247844
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a>Administración de ubicaciones para puertas de enlace de ELIN en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Para que Lync Server proporcione automáticamente ubicaciones a los clientes de una red, debe realizar las siguientes tareas:

  - Rellene la base de datos del servicio de información de ubicación con un cableado de red e incluya los números de identificación de ubicación de emergencia (Elin) en el campo NombreCompañía.

  - Publique las ubicaciones para que estén disponibles para los clientes de la red.

  - Cargue los ELIN en la base de datos de identificación de ubicación automática (ALI) del proveedor de la red telefónica conmutada (RTCP).

Para obtener más información sobre cómo realizar estas tareas, vea [configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación sobre implementación.

<div>


> [!NOTE]  
> Las ubicaciones que se agregan a la base de datos de ubicaciones centrales no están disponibles para el cliente hasta que se han publicado mediante un comando del shell de administración de Lync Server y se replican en los almacenes locales del grupo. Para obtener más información, consulte <A href="lync-server-2013-publish-the-location-database.md">publicar la base de datos de ubicaciones en Lync Server 2013</A> en la documentación sobre implementación.



</div>

Esta sección describe qué debe tener en cuenta cuando planea la actualización y el mantenimiento de la base de datos de ubicaciones.

<div>

## <a name="planning-emergency-locations"></a>Planear las ubicaciones de emergencia

Cuando use puertas de enlace ELIN, rellene la base de datos del servicio de información de ubicaciones con la dirección cívica, una ubicación específica dentro de un edificio y al menos una ELIN para cada ubicación. Durante la fase de planeación, le recomendamos que decida el nombre que quiere dar a las ubicaciones y cómo desea asignar los ELIN.

<div>

## <a name="planning-location-names"></a>Planear nombres de ubicación

El campo **Ubicación** del servicio de información de ubicación, que contiene la ubicación específica dentro de un edificio, tiene una longitud máxima de 20 caracteres (espacios incluidos). Dentro de esa longitud limitada, intente incluir lo siguiente:

  - Un nombre fácil de comprender que identifique la ubicación del autor de la llamada al 911 para que a los encargados de emergencias les resulte más fácil encontrar rápidamente la ubicación específica cuando lleguen a la dirección postal. Este nombre de ubicación puede incluir un número de edificio, la planta, la escalera, la puerta, etc. Evite los apodos que solo conozcan los empleados, ya que los encargados de emergencias podrían equivocarse de ubicación.

  - Un identificador de ubicación para que a los usuarios les resulte más fácil ver que su cliente de Lync eligió la ubicación correcta. El cliente de Lync concatena y muestra automáticamente los campos **Location** y **City** en el encabezado. Un procedimiento recomendado es agregar la dirección de la calle del edificio a cada identificador de ubicación (por ejemplo, "número \<\>de calle del 1 piso"). Si no se indica la calle, un identificador de ubicación genérico como "1ª planta" se podría aplicar a cualquier edificio de la ciudad.

  - Si la ubicación es aproximativa, porque se determina con un punto de acceso inalámbrico, agregue la palabra Near (por ejemplo, "Cerca 1ª planta 1234").

</div>

<div>

## <a name="planning-elins"></a>Planear ELIN

Después de decidir cómo va a dividir el espacio del edificio en ubicaciones, decida cuántos ELIN asignará a cada ubicación. Por ejemplo, en un edificio de varias plantas o inquilinos, puede haber diferentes zonas de emergencia para las diversas áreas del edificio. Por lo general, se considera que cada planta de un edificio es una ubicación. Después, asigne a cada ubicación uno o más ELIN, que se usan como número de llamada durante una llamada de emergencia. Póngase en contacto con el proveedor de RTC para que le dé los números de teléfono para los ELIN. La tabla siguiente proporciona un ejemplo de ubicaciones para una dirección postal concreta.

### <a name="sample-location-and-elin-assignments"></a>Ubicación y asignaciones ELIN de ejemplo

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Área del edificio</th>
<th>Ubicación</th>
<th>ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Primera planta</p></td>
<td><p>1</p></td>
<td><p>425-555-0100</p></td>
</tr>
<tr class="even">
<td><p>Segunda planta</p></td>
<td><p>segundo</p></td>
<td><p>425-555-0111</p></td>
</tr>
<tr class="odd">
<td><p>Tercera planta</p></td>
<td><p>3</p></td>
<td><p>425-555-0123</p></td>
</tr>
</tbody>
</table>


Las ubicaciones que defina deben:

  - Cumplir las normativas nacionales o regionales en cuanto al área máxima por ubicación y número de ubicaciones por dirección postal.

  - Tener la concreción suficiente como para que sea fácil ubicar a la persona que realiza la llamada de emergencia.

</div>

</div>

<div>

## <a name="populating-the-location-database"></a>Rellenar la base de datos de ubicaciones

Con las siguientes preguntas le será más fácil determinar cómo rellenar la base de datos de ubicaciones.

  - **¿Qué proceso usará para rellenar la base de datos de ubicaciones?**  
    ¿Dónde se encuentran los datos y qué pasos debe realizar para convertirlos al formato que necesita la base de datos de ubicaciones? ¿Agregará las ubicaciones una por una o en bloque con un archivo CSV?

<!-- end list -->

  - **¿Dispone de una base de datos de otros fabricantes que ya contenga una asignación de ubicaciones?**  
    Mediante el uso de la opción servicio de información de ubicación secundaria de Lync Server para conectarse a una base de datos de terceros, puede agrupar y administrar las ubicaciones mediante una plataforma sin conexión. La ventana es que además de asociar las ubicaciones a identificadores de red, puede asociar las ubicaciones a un usuario. Esto significa que el servicio de información de ubicación puede devolver varias direcciones, que se originan del servicio de información de ubicación secundario, a un cliente de Lync Server. Y el usuario puede elegir la ubicación más adecuada.
    
    Para integrarse con el servicio de información de ubicaciones, la base de datos de terceros debe seguir el esquema de solicitud y respuesta de la ubicación de Lync Server. Para obtener más información <https://go.microsoft.com/fwlink/p/?linkid=213819>, consulte. Para obtener más información sobre cómo implementar un servicio de información de ubicaciones secundarias, vea [configurar un servicio de información de ubicaciones secundarias en Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) en la documentación sobre implementación.

Para obtener información detallada sobre cómo rellenar la base de datos de ubicaciones, consulte [Configure The location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación sobre implementación.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Mantener la base de datos de ubicaciones

Una vez rellenada la base de datos de ubicaciones, desarrolle una estrategia para actualizar la base de datos a medida que se produzcan cambios en la configuración de red. Con las siguientes preguntas le será fácil determinar cómo mantener la base de datos de ubicaciones.

  - **¿Cómo actualizará la base de datos de ubicaciones?**  
    Existen diversos escenarios que requieren una actualización de la base de datos de ubicaciones, como agregar puntos de acceso inalámbricos (WAP), cambiar el cableado de una oficina (lo que da lugar a asignaciones de conmutador diferentes) o la expansión de subredes. ¿Actualizará directamente cada ubicación individual o llevará a cabo una actualización en bloque de todas las ubicaciones con un archivo CSV?

<!-- end list -->

  - **¿Usará una aplicación SNMP para hacer coincidir las direcciones MAC clientes de Lync con los identificadores de conmutadores y puertos?**  
    Si usa una aplicación SNMP, desarrolle un proceso manual para que la información de chasis de conmutador y de puerto sea coherente entre la aplicación SNMP y la base de datos de ubicaciones. Si la aplicación SNMP devuelve una dirección IP o identificador de puerto del chasis que no está incluido en la base de datos, el servicio de información de ubicación no podrá devolver una ubicación al cliente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

