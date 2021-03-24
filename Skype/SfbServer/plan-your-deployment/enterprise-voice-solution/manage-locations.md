---
title: Administrar ubicaciones para proveedores de servicios troncales SIP en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Decisiones necesarias para planear una base de datos de información de ubicación, o una base de datos externa similar, para una implementación de E9-1-1 con proveedores de enlace troncal SIP, en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: b175c2cc3d0ed02a124a365787c8cb5d7cd37d10
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101446"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Administrar ubicaciones para proveedores de servicios troncales SIP en Skype Empresarial Server

Decisiones necesarias para planear una base de datos de información de ubicación, o una base de datos externa similar, para una implementación de E9-1-1 con proveedores de enlace troncal SIP, en Skype Empresarial Server Telefonía IP empresarial.

Para configurar Skype Empresarial Server para ubicar automáticamente clientes dentro de una red, debe rellenar la base de datos del servicio de información de ubicación con un mapa de conexión de red y publicar las ubicaciones, o bien vincular a una base de datos externa que ya contiene las asignaciones correctas. Como parte de este proceso, valide las direcciones con el proveedor de servicios de E9-1-1. Para más información, vea [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) en la documentación sobre implementación.

Rellene la base de datos del servicio de información de ubicaciones con una ubicación de respuesta de emergencia (ERL), formada por una dirección postal y la dirección específica en un edificio. El campo Ubicación **del** servicio de información de ubicación, que es la ubicación específica dentro de un edificio, tiene una longitud máxima de 20 caracteres (incluidos los espacios). Dentro de esa longitud limitada, intente incluir lo siguiente:

- Un nombre fácil de entender que identifique la ubicación del autor de la llamada al 911 para garantizar que los servicios de emergencias encuentren la ubicación específica rápidamente una vez que estos lleguen a la dirección postal. Este nombre de ubicación puede incluir un número de edificio, un número de piso, un indicador de ala, un número de habitación, entre otros elementos. Evite nombres conocidos solo por los empleados, ya que podrían causar que los servicios de emergencia se dirijan a una ubicación equivocada.

- Un identificador de ubicación que ayuda a los usuarios a ver fácilmente que su cliente de Skype Empresarial ha elegido la ubicación correcta. El cliente de Skype Empresarial concatena automáticamente y muestra los campos **Location** y **City** detectados en su encabezado. Una buena práctica es agregar la dirección de calle del edificio a cada identificador de ubicación (por ejemplo, "1st <street number> Floor"). Si no se indica la calle, un identificador de ubicación genérico como "1ª planta" se podría aplicar a cualquier edificio de la ciudad.

- Si la ubicación es aproximada porque está determinada por un punto de acceso inalámbrico, puedes agregar la palabra **[Cerca]** (por ejemplo, "Near 1st Floor 1234").

> [!NOTE]
> Las ubicaciones agregadas a la base de datos de ubicaciones centrales no están disponibles para el cliente hasta que se publican mediante un comando del Shell de administración de Skype Empresarial Server y se replican en los almacenes locales del grupo. Para más información, vea [Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database) en la documentación de implementación.

En las secciones siguientes se describen consideraciones que debe tener en cuenta a la hora de rellenar y mantener la base de datos de ubicaciones.

## <a name="populating-the-location-database"></a>Rellenar la base de datos de ubicaciones

Con las siguientes preguntas le será fácil determinar cómo rellenar la base de datos de ubicaciones.

 **¿Qué proceso usará para rellenar la base de datos de ubicaciones?**

¿Dónde se encuentran los datos y qué pasos debe realizar para convertirlos al formato que necesita la base de datos de ubicaciones? ¿Agregará las ubicaciones una por una o en bloque con un archivo CSV?

 **¿Dispone de una base de datos de otros fabricantes que ya contenga una asignación de ubicaciones?**

Al usar la opción Servicio de información de ubicación secundaria para conectarse a una base de datos de terceros, puede agrupar y administrar ubicaciones mediante una plataforma sin conexión. La ventana es que además de asociar las ubicaciones a identificadores de red, puede asociar las ubicaciones a un usuario. Esto significa que el servicio de información de ubicación puede devolver varias direcciones, originadas desde el servicio de información de ubicación secundaria, a un cliente de Skype Empresarial. Y el usuario puede elegir la ubicación más adecuada.

Para integrarse con el servicio de información de ubicación, la base de datos de terceros debe seguir el esquema de solicitud y respuesta de ubicación de Lync Server. Para obtener más información, vea  ["[MS-E911WS]: Web Service for E911 Support Protocol Specification"](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd). Para obtener más información sobre cómo implementar un servicio de información de ubicación secundaria, vea [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) en la documentación sobre implementación.

Para más información sobre cómo rellenar la base de datos de ubicaciones, vea [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) en la documentación sobre implementación.

## <a name="maintaining-the-location-database"></a>Mantener la base de datos de ubicaciones

Una vez rellenada la base de datos de ubicaciones, desarrolle una estrategia para actualizar la base de datos a medida que se produzcan cambios en la configuración de red. Con las siguientes preguntas le será fácil determinar cómo mantener la base de datos de ubicaciones.

 **¿Cómo actualizará la base de datos de ubicaciones?**

Existen diversos escenarios que requieren una actualización de la base de datos de ubicaciones, como agregar WAP, cambiar el cableado de una oficina (lo que da lugar a asignaciones de conmutador nuevas) y la expansión de subredes. ¿Actualizará directamente cada ubicación o llevará a cabo una actualización en bloque de todas las ubicaciones con un archivo CSV?

 **¿Usará una aplicación SNMP para hacer coincidir las direcciones MAC con la información de conmutadores y puertos?**

Si usa una aplicación SNMP, desarrolle un proceso manual para que la información de chasis de conmutador y de puerto sea coherente entre la aplicación SNMP y la base de datos de ubicaciones. Si la aplicación SNMP devuelve una dirección IP de chasis o un identificador de puerto que no se incluye en la base de datos, el servicio de información de ubicación no podrá devolver una ubicación al cliente.