---
title: "Lync Server 2013: Admin. ubicaciones de proveedores de servicio enlaces troncales SIP"
TOCTitle: Administrar ubicaciones para proveedores de servicio de enlaces troncales SIP
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48276857
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administrar ubicaciones para proveedores de servicio de enlaces troncales SIP en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Para configurar Lync Server para localizar automáticamente los clientes de una red, debe rellenar la base de datos de Servicio de información de ubicaciones con un diagrama de cableado de red y publicar las ubicaciones, o bien definir una base de datos externa que ya contenga la asignación correcta. Como parte de este proceso, valide las direcciones con el proveedor de servicios de E9-1-1. Para más información, vea [Configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación sobre implementación.

Rellene la base de datos del servicio de información de ubicaciones con una ubicación de respuesta de emergencia (ERL), formada por una dirección postal y la dirección específica en un edificio. El campo Servicio de información de ubicaciones**Location**, que es la ubicación específica dentro de un edificio, tiene una longitud máxima de 20 caracteres (espacios incluidos). Dentro de esa longitud limitada, intente incluir lo siguiente:

  - Un nombre fácil de entender que identifique la ubicación del autor de la llamada al 911 para garantizar que los servicios de emergencias encuentren la ubicación específica rápidamente una vez que estos lleguen a la dirección postal. Este nombre de ubicación puede incluir un número de edificio, un número de piso, un indicador de ala, un número de habitación, entre otros elementos. Evite nombres conocidos solo por los empleados, ya que podrían causar que los servicios de emergencia se dirijan a una ubicación equivocada.

  - Un identificador de ubicación que permita a los usuarios ver fácilmente que su cliente Lync ha recogido la ubicación correcta. El cliente Lync concatena y muestra automáticamente los campos **Location** y **City** detectados en su encabezado. Recomendamos agregar el nombre de la calle del edificio para cada identificador de ubicación (por ejemplo, "1r piso \<número de calle\>"). Sin la calle, un identificador genérico como "1r piso" podría referirse a cualquier edificio de la ciudad.

  - Si la ubicación es aproximada porque está determinada por un punto de acceso inalámbrico, añada la palabra Near, por ejemplo, Cerca del 1r piso 1234.


> [!NOTE]
> Las ubicaciones agregadas a la base de datos central de ubicaciones no estarán disponibles para el cliente hasta que no se hayan publicado ejecutando un comando de Shell de administración de Lync Server y no se hayan replicado en los almacenes locales del grupo de servidores. Para más información, vea <A href="lync-server-2013-publish-the-location-database.md">Publicar la base de datos de ubicación desde Lync Server 2013</A> en la documentación de implementación.



En las secciones siguientes se describen consideraciones que debe tener en cuenta a la hora de rellenar y mantener la base de datos de ubicaciones.

## Rellenar la base de datos de ubicaciones

Con las siguientes preguntas le será fácil determinar cómo rellenar la base de datos de ubicaciones.

  - **¿Qué proceso usará para rellenar la base de datos de ubicaciones?**  
    ¿Dónde se encuentran los datos y qué pasos debe realizar para convertirlos al formato que necesita la base de datos de ubicaciones? ¿Agregará las ubicaciones una por una o en bloque con un archivo CSV?

<!-- end list -->

  - **¿Dispone de una base de datos de otros fabricantes que ya contenga una asignación de ubicaciones?**  
    Si usa la opción de Servicio de información de ubicaciones secundaria de Lync Server para conectarse a una base de datos de otro fabricante, puede agrupar y administrar las ubicaciones con una plataforma sin conexión. La ventaja es que además de asociar las ubicaciones a identificadores de red, puede asociar las ubicaciones a un usuario. Esto significa que el Servicio de información de ubicaciones puede devolver varias direcciones que provienen del servidor de información de Servicio de información de ubicaciones secundario a un cliente de Lync Server. Y el usuario podrá elegir la ubicación más adecuada.
    
    Para integrarse con el Servicio de información de ubicaciones, la base de datos de otro fabricante debe seguir el esquema de solicitud de ubicación/respuesta de Lync Server. Para más información, vea "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" <http://go.microsoft.com/fwlink/p/?linkid=213819>. Para más información sobre la implementación de un Servicio de información de ubicaciones secundario, vea [Configurar un servicio de información de ubicación secundario en Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) en la documentación sobre implementación.

Para más información sobre cómo rellenar la base de datos de ubicaciones, vea [Configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación sobre implementación.

## Mantenimiento de la base de datos de ubicaciones

Una vez rellenada la base de datos de ubicaciones, desarrolle una estrategia para actualizar la base de datos a medida que se produzcan cambios en la configuración de red. Con las siguientes preguntas le será fácil determinar cómo mantener la base de datos de ubicaciones.

  - **¿Cómo actualizará la base de datos de ubicaciones?**  
    Existen diversos escenarios que requieren una actualización de la base de datos de ubicaciones, como agregar WAP, cambiar el cableado de una oficina (lo que da lugar a asignaciones de conmutador nuevas) y la expansión de subredes. ¿Actualizará directamente cada ubicación o llevará a cabo una actualización en bloque de todas las ubicaciones con un archivo CSV?

<!-- end list -->

  - **¿Usará una aplicación SNMP para hacer coincidir las direcciones MAC con la información de conmutadores y puertos?**  
    Si usa una aplicación SNMP, desarrolle un proceso manual para que la información de chasis de conmutador y de puerto sea coherente entre la aplicación SNMP y la base de datos de ubicaciones. Si la aplicación SNMP devuelve una dirección IP de chasis o un identificador de puerto que no está incluido en la base de datos, el Servicio de información de ubicaciones no podrá devolver una ubicación al cliente.

