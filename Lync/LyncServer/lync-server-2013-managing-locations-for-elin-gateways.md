---
title: 'Lync Server 2013: administración de ubicaciones de puertas de enlace de ELIN'
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
ms.openlocfilehash: ba5a7e9067e4cd59ca42e60c620dbb4e8ee5b901
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a>Administrar ubicaciones de puertas de enlace de ELIN en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Para que Lync Server proporcione automáticamente ubicaciones para los clientes dentro de una red, debe realizar las siguientes tareas:

  - Rellene la información de ubicación de la base de datos del servicio con un Wiremap de red e incluya los números de identificación de ubicación de emergencia (ELINs) en el campo NombreCompañía.

  - Publica las ubicaciones para que estén disponibles para los clientes en tu red.

  - Carga los ELIN en la base de datos de identificación de ubicación automática (ALI) del proveedor de la red telefónica conmutada (RTC).

Para obtener más información sobre cómo realizar estas tareas, vea [configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación de implementación.

<div>


> [!NOTE]  
> Las ubicaciones que se agreguen a la base de datos de ubicación central no estarán disponibles para el cliente hasta que se hayan publicado mediante un comando de Shell de administración de Lync Server y se repliquen en las tiendas locales del grupo. Para obtener más información, vea <A href="lync-server-2013-publish-the-location-database.md">publicar la base de datos de ubicaciones de Lync Server 2013</A> en la documentación de implementación.



</div>

Esta sección describe qué necesitas tener en cuenta cuando planificas la actualización y el mantenimiento de la base de datos de ubicaciones.

<div>

## <a name="planning-emergency-locations"></a>Planificar las ubicaciones de emergencia

Cuando use puertas de enlace ELIN, deberá rellenar la base de datos de servicios de información de ubicación con la dirección cívica, una ubicación específica dentro de un edificio y, al menos, una ELIN para cada ubicación. Durante la fase de planificación, recomendamos que decidas el nombre que quieras dar a las ubicaciones y cómo deseas asignar los ELIN.

<div>

## <a name="planning-location-names"></a>Planificar nombres de ubicación

El campo **Ubicación** del servicio de información de ubicación, que contiene la ubicación específica dentro de un edificio, tiene una longitud máxima de 20 caracteres (incluidos los espacios). Dentro de esa longitud limitada, intenta incluir lo siguiente:

  - Un nombre fácil de comprender que identifique la ubicación del autor de la llamada al 911 para que a los encargados de emergencias les resulte más fácil encontrar rápidamente la ubicación específica cuando lleguen a la dirección postal. Este nombre de ubicación puede incluir un número de edificio, la planta, la escalera, la puerta, etc. Evita los apodos que solo conozcan los empleados, ya que los encargados de emergencias podrían equivocarse de ubicación.

  - Un identificador de ubicación que permite a los usuarios ver fácilmente que el cliente de Lync ha recogido la ubicación correcta. El cliente de Lync concatena y muestra automáticamente los campos **Ubicación** detectada y **ciudad** en el encabezado. Una buena práctica es agregar la dirección del edificio a cada identificador de ubicación (por ejemplo, "número \<\>de calle del primer piso"). Sin la calle, un identificador genérico como "1.ª planta" podría referirse a cualquier edificio de la ciudad.

  - Si la ubicación es aproximada, porque se determina con un punto de acceso inalámbrico, agrega la palabra Near (por ejemplo, "Cerca 1.ª planta 1234").

</div>

<div>

## <a name="planning-elins"></a>Planificar ELIN

Después de decidir cómo vas a dividir el espacio del edificio en ubicaciones, necesitas decidir cuántos ELIN asignarás a cada ubicación. Por ejemplo, en un edificio de varias plantas o varios inquilinos, puede haber diferentes zonas de emergencia para las diversas áreas del edificio. Por lo general, se considera que cada planta de un edificio es una ubicación. Después, asigna a cada ubicación uno o más ELIN, que se usan como número(s) de llamada durante una llamada de emergencia. Ponte en contacto con tu proveedor de RTC para que te brinde los números de teléfono que puedes usar para los ELIN. La tabla siguiente proporciona un ejemplo de ubicaciones para una dirección postal concreta.

### <a name="sample-location-and-elin-assignments"></a>Ubicación y asignaciones de ELIN de ejemplo

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
<td><p>1</p></td>
<td><p>425-555-0111</p></td>
</tr>
<tr class="odd">
<td><p>Tercera planta</p></td>
<td><p>3</p></td>
<td><p>425-555-0123</p></td>
</tr>
</tbody>
</table>


Las ubicaciones que definas necesitan:

  - Cumplir las normativas nacionales o regionales en cuanto al área máxima por ubicación y a la cantidad de ubicaciones por dirección postal.

  - Tener la precisión suficiente como para que sea fácil ubicar a la persona que realiza la llamada de emergencia.

</div>

</div>

<div>

## <a name="populating-the-location-database"></a>Rellenar la base de datos de ubicaciones

Con las siguientes preguntas te será más fácil determinar cómo rellenar la base de datos de ubicaciones.

  - **¿Qué proceso usará para rellenar la base de datos de ubicaciones?**  
    ¿Dónde se encuentran los datos y qué pasos necesitas realizar para convertirlos al formato que necesita la base de datos de ubicaciones? ¿Agregarás las ubicaciones una por una o en bloque con un archivo CSV?

<!-- end list -->

  - **¿Dispone de una base de datos de otros fabricantes que ya contenga una asignación de ubicaciones?**  
    Al usar la opción de servicio de información de ubicación secundaria de Lync Server para conectarse a una base de datos de terceros, puede agrupar y administrar ubicaciones mediante una plataforma sin conexión. La ventaja es que además de asociar las ubicaciones a identificadores de red, puedes asociar las ubicaciones a un usuario. Esto significa que el servicio de información de ubicación puede devolver varias direcciones, que se originan en el servicio de información de ubicación secundaria, en un cliente de Lync Server. Luego, el usuario podrá elegir la ubicación más adecuada.
    
    Para integrar con el servicio de información de ubicación, la base de datos de terceros debe seguir el esquema de solicitud/respuesta de la ubicación de Lync Server. Para obtener más información <http://go.microsoft.com/fwlink/p/?linkid=213819>, consulte. Para obtener detalles sobre cómo implementar un servicio de información de ubicación secundaria, vea [configurar un servicio de información de ubicación secundaria en Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) en la documentación de implementación.

Para obtener detalles sobre cómo rellenar la base de datos de ubicación, vea [configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación de implementación.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Mantener la base de datos de ubicaciones

Una vez rellenada la base de datos de ubicaciones, desarrolla una estrategia para actualizar la base de datos a medida que se produzcan cambios en la configuración de red. Con las siguientes preguntas te será fácil determinar cómo mantener la base de datos de ubicaciones.

  - **¿Cómo actualizará la base de datos de ubicaciones?**  
    Existen diversos escenarios que requieren una actualización de la base de datos de ubicaciones, como agregar puntos de acceso inalámbricos (WAP), cambiar el cableado de una oficina (lo que da lugar a asignaciones de conmutador diferentes) o la expansión de subredes. ¿Actualizarás directamente cada ubicación individual o llevarás a cabo una actualización en bloque de todas las ubicaciones con un archivo CSV?

<!-- end list -->

  - **¿Usará una aplicación SNMP para hacer coincidir las direcciones MAC del cliente Lync con los identificadores de conmutadores y puertos?**  
    Si usas una aplicación SNMP, necesitas desarrollar un proceso manual para mantener sincronizada la información de conmutadores y puertos entre la aplicación SNMP y la base de datos de ubicaciones. Si la aplicación SNMP devuelve una dirección IP del chasis o un identificador de puerto que no está incluido en la base de datos, el servicio de información de ubicación no podrá devolver una ubicación al cliente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

