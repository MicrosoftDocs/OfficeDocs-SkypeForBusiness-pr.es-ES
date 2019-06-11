---
title: 'Lync Server 2013: administración de ubicaciones para proveedores de servicios de tronco de SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eba237ae4e984169a354339ce0222dfd58f324c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a>Administración de ubicaciones para proveedores de servicios de tronco de SIP en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

Para configurar Lync Server para ubicar automáticamente clientes dentro de una red, debe rellenar la base de datos del servicio de información de ubicación con un Wiremap de red y publicar las ubicaciones, o vincular a una base de datos externa que ya contenga la configuración correcta asignaciones. Como parte de este proceso, necesitas validar las direcciones postales con el proveedor de servicios de E9-1-1. Para obtener más información, vea [configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación de implementación.

Rellena la base de datos del servicio de información de ubicaciones con una ubicación de respuesta de emergencia (ERL), formada por una dirección postal y la dirección específica en un edificio. El campo **Ubicación** del servicio de información de ubicación, que es la ubicación específica dentro de un edificio, tiene una longitud máxima de 20 caracteres (incluidos los espacios). Dentro de esa longitud limitada, intenta incluir lo siguiente:

  - Un nombre fácil de comprender que identifique la ubicación del autor de la llamada al 911 para que a los encargados de emergencias les resulte más fácil encontrar rápidamente la ubicación específica cuando lleguen a la dirección postal. Este nombre de ubicación puede incluir un número de edificio, la planta, la escalera, la puerta, etc. Evita los apodos que solo conozcan los empleados, ya que los encargados de emergencias podrían equivocarse de ubicación.

  - Un identificador de ubicación que permite a los usuarios ver fácilmente que el cliente de Lync ha recogido la ubicación correcta. El cliente de Lync concatena y muestra automáticamente los campos **Ubicación** detectada y **ciudad** en el encabezado. Una buena práctica es agregar la dirección del edificio a cada identificador de ubicación (por ejemplo, "número \<\>de calle del primer piso"). Sin la calle, un identificador genérico como "1.ª planta" podría referirse a cualquier edificio de la ciudad.

  - Si la ubicación es aproximada, porque se determina por un punto de acceso inalámbrico, puedes agregar la palabra Near (por ejemplo, "Cerca" 1.ª planta 1234).

<div>


> [!NOTE]  
> Las ubicaciones que se agreguen a la base de datos de ubicación central no estarán disponibles para el cliente hasta que se publiquen mediante un comando del shell de administración de Lync Server y se repliquen en las tiendas locales del grupo. Para obtener más información, vea <A href="lync-server-2013-publish-the-location-database.md">publicar la base de datos de ubicaciones de Lync Server 2013</A> en la documentación de implementación.



</div>

En las secciones siguientes se describen consideraciones que necesitas tener en cuenta a la hora de rellenar y mantener la base de datos de ubicaciones.

<div>

## <a name="populating-the-location-database"></a>Rellenar la base de datos de ubicaciones

Con las siguientes preguntas te será fácil determinar cómo rellenar la base de datos de ubicaciones.

  - **¿Qué proceso usará para rellenar la base de datos de ubicaciones?**  
    ¿Dónde se encuentran los datos y qué pasos necesitas realizar para convertirlos al formato que necesita la base de datos de ubicaciones? ¿Agregarás las ubicaciones una por una o en bloque con un archivo CSV?

<!-- end list -->

  - **¿Dispone de una base de datos de otros fabricantes que ya contenga una asignación de ubicaciones?**  
    Al usar la opción de servicio de información de ubicación secundaria de Lync Server para conectarse a una base de datos de terceros, puede agrupar y administrar ubicaciones mediante una plataforma sin conexión. La ventaja es que además de asociar las ubicaciones a identificadores de red, puedes asociar las ubicaciones a un usuario. Esto significa que el servicio de información de ubicación puede devolver varias direcciones, que se originan en el servicio de información de ubicación secundaria, en un cliente de Lync Server. Luego, el usuario podrá elegir la ubicación más adecuada.
    
    Para integrar con el servicio de información de ubicación, la base de datos de terceros debe seguir el esquema de solicitud/respuesta de la ubicación de Lync Server. Para obtener más información,\[consulte "MS\]-E911WS: servicio web para la especificación de protocolo <http://go.microsoft.com/fwlink/p/?linkid=213819>de compatibilidad de E911" en. Para obtener detalles sobre cómo implementar un servicio de información de ubicación secundaria, vea [configurar un servicio de información de ubicación secundaria en Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) en la documentación de implementación.

Para obtener detalles sobre cómo rellenar la base de datos de ubicación, vea [configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación de implementación.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Mantener la base de datos de ubicaciones

Una vez rellenada la base de datos de ubicaciones, desarrolla una estrategia para actualizar la base de datos a medida que se produzcan cambios en la configuración de red. Con las siguientes preguntas te será fácil determinar cómo mantener la base de datos de ubicaciones.

  - **¿Cómo actualizará la base de datos de ubicaciones?**  
    Existen diversos escenarios que requieren una actualización de la base de datos de ubicaciones, como agregar WAP, cambiar el cableado de una oficina (lo que da lugar a asignaciones de conmutador nuevas) y la expansión de subredes. ¿Actualizarás directamente cada ubicación o llevarás a cabo una actualización en bloque de todas las ubicaciones con un archivo CSV?

<!-- end list -->

  - **¿Usará una aplicación SNMP para hacer coincidir las direcciones MAC del cliente Lync con los identificadores de conmutadores y puertos?**  
    Si usas una aplicación SNMP, necesitas desarrollar un proceso manual para mantener sincronizada la información de conmutadores y puertos entre la aplicación SNMP y la base de datos de ubicaciones. Si la aplicación SNMP devuelve una dirección IP del chasis o un identificador de puerto que no está incluido en la base de datos, el servicio de información de ubicación no podrá devolver una ubicación al cliente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

