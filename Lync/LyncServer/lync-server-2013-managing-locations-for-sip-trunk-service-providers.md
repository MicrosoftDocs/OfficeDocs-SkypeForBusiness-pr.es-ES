---
title: 'Lync Server 2013: administración de ubicaciones para proveedores de servicio de tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6aa7dce34aea04c851608f67d1412c1c3da4069
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498177"
---
# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a>Administración de ubicaciones para proveedores de servicio de tronco de SIP en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Para configurar Lync Server para ubicar automáticamente los clientes dentro de una red, debe rellenar la base de datos del servicio de información de ubicación con un cableado de red y publicar las ubicaciones o vincular a una base de datos externa que ya contenga las asignaciones correctas. Como parte de este proceso, valide las direcciones con el proveedor de servicios de E9-1-1. Para obtener más información, consulte [configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación sobre implementación.

Rellene la base de datos del servicio de información de ubicaciones con una ubicación de respuesta de emergencia (ERL), formada por una dirección postal y la dirección específica en un edificio. El campo **Ubicación** del servicio de información de ubicación, que es la ubicación específica dentro de un edificio, tiene una longitud máxima de 20 caracteres (espacios incluidos). Dentro de esa longitud limitada, intente incluir lo siguiente:

  - Un nombre fácil de entender que identifique la ubicación del autor de la llamada al 911 para garantizar que los servicios de emergencias encuentren la ubicación específica rápidamente una vez que estos lleguen a la dirección postal. Este nombre de ubicación puede incluir un número de edificio, un número de piso, un indicador de ala, un número de habitación, entre otros elementos. Evite nombres conocidos solo por los empleados, ya que podrían causar que los servicios de emergencia se dirijan a una ubicación equivocada.

  - Un identificador de ubicación para que a los usuarios les resulte más fácil ver que su cliente de Lync eligió la ubicación correcta. El cliente de Lync concatena y muestra automáticamente los campos **Location** y **City** en el encabezado. Un procedimiento recomendado es agregar la dirección de la calle del edificio a cada identificador de ubicación (por ejemplo, "1ª planta \<street number\> "). Si no se indica la calle, un identificador de ubicación genérico como "1ª planta" se podría aplicar a cualquier edificio de la ciudad.

  - Si la ubicación es aproximada porque está determinada por un punto de acceso inalámbrico, añada la palabra Near, por ejemplo, Cerca del 1r piso 1234.

<div>


> [!NOTE]  
> Las ubicaciones que se agregan a la base de datos de ubicaciones centrales no están disponibles para el cliente hasta que se publican mediante un comando del shell de administración de Lync Server y se replican en los almacenes locales del grupo. Para obtener más información, consulte <A href="lync-server-2013-publish-the-location-database.md">publicar la base de datos de ubicaciones en Lync Server 2013</A> en la documentación sobre implementación.



</div>

En las secciones siguientes se describen consideraciones que debe tener en cuenta a la hora de rellenar y mantener la base de datos de ubicaciones.

<div>

## <a name="populating-the-location-database"></a>Rellenar la base de datos de ubicaciones

Con las siguientes preguntas le será fácil determinar cómo rellenar la base de datos de ubicaciones.

  - **¿Qué proceso usará para rellenar la base de datos de ubicaciones?**  
    ¿Dónde se encuentran los datos y qué pasos debe realizar para convertirlos al formato que necesita la base de datos de ubicaciones? ¿Agregará las ubicaciones una por una o en bloque con un archivo CSV?

<!-- end list -->

  - **¿Dispone de una base de datos de otros fabricantes que ya contenga una asignación de ubicaciones?**  
    Mediante el uso de la opción servicio de información de ubicación secundaria de Lync Server para conectarse a una base de datos de terceros, puede agrupar y administrar las ubicaciones mediante una plataforma sin conexión. La ventana es que además de asociar las ubicaciones a identificadores de red, puede asociar las ubicaciones a un usuario. Esto significa que el servicio de información de ubicación puede devolver varias direcciones, que se originan del servicio de información de ubicación secundario, a un cliente de Lync Server. Y el usuario puede elegir la ubicación más adecuada.
    
    Para integrarse con el servicio de información de ubicaciones, la base de datos de terceros debe seguir el esquema de solicitud y respuesta de la ubicación de Lync Server. Para obtener más información, consulte " \[ MS-E911WS \] : servicio web para la especificación del Protocolo de soporte de E911" en <https://go.microsoft.com/fwlink/p/?linkid=213819> . Para obtener más información sobre cómo implementar un servicio de información de ubicaciones secundarias, vea [configurar un servicio de información de ubicaciones secundarias en Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) en la documentación sobre implementación.

Para obtener información detallada sobre cómo rellenar la base de datos de ubicaciones, consulte [Configure The location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación sobre implementación.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Mantener la base de datos de ubicaciones

Una vez rellenada la base de datos de ubicaciones, desarrolle una estrategia para actualizar la base de datos a medida que se produzcan cambios en la configuración de red. Con las siguientes preguntas le será fácil determinar cómo mantener la base de datos de ubicaciones.

  - **¿Cómo actualizará la base de datos de ubicaciones?**  
    Existen diversos escenarios que requieren una actualización de la base de datos de ubicaciones, como agregar WAP, cambiar el cableado de una oficina (lo que da lugar a asignaciones de conmutador nuevas) y la expansión de subredes. ¿Actualizará directamente cada ubicación o llevará a cabo una actualización en bloque de todas las ubicaciones con un archivo CSV?

<!-- end list -->

  - **¿Usará una aplicación SNMP para hacer coincidir las direcciones MAC con la información de conmutadores y puertos?**  
    Si usa una aplicación SNMP, desarrolle un proceso manual para que la información de chasis de conmutador y de puerto sea coherente entre la aplicación SNMP y la base de datos de ubicaciones. Si la aplicación SNMP devuelve una dirección IP o identificador de puerto del chasis que no está incluido en la base de datos, el servicio de información de ubicación no podrá devolver una ubicación al cliente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

