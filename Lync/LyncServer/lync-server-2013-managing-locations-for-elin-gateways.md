---
title: 'Lync Server 2013: Administrar ubicaciones para puertas de enlace ELIN'
TOCTitle: Administrar ubicaciones para puertas de enlace ELIN
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48276705
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administrar ubicaciones para puertas de enlace ELIN en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Para que Lync Server proporcione automáticamente las ubicaciones para clientes en una red, haga lo siguiente:

  - Rellene la base de datos de Servicio de información de ubicaciones con un diagrama de cables de red e incluya los números de identificación de ubicación de emergencia (ELIN) en el campo CompanyName.

  - Publique las ubicaciones para que estén disponibles para los clientes de la red.

  - Cargue los ELIN en la base de datos de identificación de ubicación automática (ALI) del proveedor de la red telefónica conmutada (RTCP).

Para obtener información detallada sobre la ejecución de estas tareas, vea [Configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación de implementación.


> [!NOTE]
> Las ubicaciones agregadas a la base de datos central de ubicaciones no estarán disponibles para el cliente hasta que no se hayan publicado ejecutando un comando de Shell de administración de Lync Server y no se hayan replicado en los almacenes locales del grupo de servidores. Para más información, vea <A href="lync-server-2013-publish-the-location-database.md">Publicar la base de datos de ubicación desde Lync Server 2013</A> en la documentación de implementación.



Esta sección describe qué debe tener en cuenta cuando planea la actualización y el mantenimiento de la base de datos de ubicaciones.

## Planear las ubicaciones de emergencia

Cuando usa puertas de enlace ELIN, rellena la base de datos de Servicio de información de ubicaciones con la dirección postal, una ubicación específica en un edificio y un ELIN como mínimo para cada ubicación. Durante la fase de planeación, le recomendamos que decida el nombre que quiere dar a las ubicaciones y cómo desea asignar los ELIN.

## Planear nombres de ubicación

El campo Servicio de información de ubicaciones**Location**, que contiene la ubicación específica en un edificio, tiene una longitud máxima de 20 caracteres (espacios incluidos). Dentro de esa longitud limitada, intente incluir lo siguiente:

  - Un nombre fácil de comprender que identifique la ubicación del autor de la llamada al 911 para que a los encargados de emergencias les resulte más fácil encontrar rápidamente la ubicación específica cuando lleguen a la dirección postal. Este nombre de ubicación puede incluir un número de edificio, la planta, la escalera, la puerta, etc. Evite los apodos que solo conozcan los empleados, ya que los encargados de emergencias podrían equivocarse de ubicación.

  - Un identificador de ubicación que permita a los usuarios ver fácilmente que su cliente Lync ha recogido la ubicación correcta. El cliente Lync concatena y muestra automáticamente los campos **Location** y **City** detectados en su encabezado. Recomendamos agregar el nombre de la calle del edificio para cada identificador de ubicación (por ejemplo, "1r piso \<número de calle\>"). Sin la calle, un identificador genérico como "1r piso" podría referirse a cualquier edificio de la ciudad.

  - Si la ubicación es aproximativa, porque se determina con un punto de acceso inalámbrico, agregue la palabra Near (por ejemplo, "Cerca 1ª planta 1234").

## Planear ELIN

Después de decidir cómo va a dividir el espacio del edificio en ubicaciones, decida cuántos ELIN asignará a cada ubicación. Por ejemplo, en un edificio de varias plantas o inquilinos, puede haber diferentes zonas de emergencia para las diversas áreas del edificio. Por lo general, se considera que cada planta de un edificio es una ubicación. Después, asigne a cada ubicación uno o más ELIN, que se usan como número de llamada durante una llamada de emergencia. Póngase en contacto con el proveedor de RTC para que le dé los números de teléfono para los ELIN. La tabla siguiente proporciona un ejemplo de ubicaciones para una dirección postal concreta.

### Ubicación y asignaciones ELIN de ejemplo

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
<td><p>2</p></td>
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

## Rellenar la base de datos de ubicaciones

Con las siguientes preguntas le será más fácil determinar cómo rellenar la base de datos de ubicaciones.

  - **¿Qué proceso usará para rellenar la base de datos de ubicaciones?**  
    ¿Dónde se encuentran los datos y qué pasos debe realizar para convertirlos al formato que necesita la base de datos de ubicaciones? ¿Agregará las ubicaciones una por una o en bloque con un archivo CSV?

<!-- end list -->

  - **¿Dispone de una base de datos de otros fabricantes que ya contenga una asignación de ubicaciones?**  
    Si usa la opción de Servicio de información de ubicaciones secundaria de Lync Server para conectarse a una base de datos de otro fabricante, puede agrupar y administrar las ubicaciones con una plataforma sin conexión. La ventaja es que además de asociar las ubicaciones a identificadores de red, puede asociar las ubicaciones a un usuario. Esto significa que el Servicio de información de ubicaciones puede devolver varias direcciones que provienen del servidor de información de Servicio de información de ubicaciones secundario a un cliente de Lync Server. Y el usuario podrá elegir la ubicación más adecuada.
    
    Para integrarse con el Servicio de información de ubicaciones, la base de datos de otro fabricante debe seguir el esquema de solicitud de ubicación/respuesta de Lync Server. Para más información, vea [http://go.microsoft.com/fwlink/?linkid=213819\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=213819%26clcid=0xc0a). Para más información sobre la implementación de un Servicio de información de ubicaciones secundario, vea [Configurar un servicio de información de ubicación secundario en Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) en la documentación sobre implementación.

Para más información sobre cómo rellenar la base de datos de ubicaciones, vea [Configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación sobre implementación.

## Mantenimiento de la base de datos de ubicaciones

Una vez rellenada la base de datos de ubicaciones, desarrolle una estrategia para actualizar la base de datos a medida que se produzcan cambios en la configuración de red. Con las siguientes preguntas le será fácil determinar cómo mantener la base de datos de ubicaciones.

  - **¿Cómo actualizará la base de datos de ubicaciones?**  
    Existen diversos escenarios que requieren una actualización de la base de datos de ubicaciones, como agregar puntos de acceso inalámbricos (WAP), cambiar el cableado de una oficina (lo que da lugar a asignaciones de conmutador diferentes) o la expansión de subredes. ¿Actualizará directamente cada ubicación individual o llevará a cabo una actualización en bloque de todas las ubicaciones con un archivo CSV?

<!-- end list -->

  - **¿Usará una aplicación SNMP para hacer coincidir las direcciones MAC con la información de conmutadores y puertos?**  
    Si usa una aplicación SNMP, desarrolle un proceso manual para que la información de chasis de conmutador y de puerto sea coherente entre la aplicación SNMP y la base de datos de ubicaciones. Si la aplicación SNMP devuelve una dirección IP de chasis o un identificador de puerto que no está incluido en la base de datos, el Servicio de información de ubicaciones no podrá devolver una ubicación al cliente.

