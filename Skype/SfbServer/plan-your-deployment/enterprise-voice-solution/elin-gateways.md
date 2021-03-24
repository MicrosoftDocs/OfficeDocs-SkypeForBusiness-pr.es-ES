---
title: Administrar ubicaciones para puertas de enlace ELIN en Skype Empresarial Server
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
ms.assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
description: Decisiones necesarias para planear una base de datos de información de ubicación, o una base de datos externa similar, para una implementación de E9-1-1 con puertas de enlace ELIN, en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: dd16270aa5a41e3ca50e92859bd1a789426e647b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092918"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Administrar ubicaciones para puertas de enlace ELIN en Skype Empresarial Server

Decisiones necesarias para planear una base de datos de información de ubicación, o una base de datos externa similar, para una implementación de E9-1-1 con puertas de enlace ELIN, en Skype Empresarial Server Telefonía IP empresarial.

Para que Skype Empresarial Server proporcione automáticamente ubicaciones para clientes dentro de una red, debe realizar las siguientes tareas:

- Rellene la base de datos del servicio de información de ubicación con un mapa de conexión de red e incluya los números de identificación de ubicación de emergencia (ELIN) en el campo CompanyName.

- Publique las ubicaciones para que estén disponibles para los clientes de la red.

- Cargue los ELIN en la base de datos de identificación de ubicación automática (ALI) del proveedor de la red telefónica conmutada (RTCP).

Para más información sobre la ejecución de estas tareas, vea [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) en la documentación de implementación.

> [!NOTE]
> Las ubicaciones agregadas a la base de datos de ubicaciones centrales no están disponibles para el cliente hasta que se han publicado mediante un comando del Shell de administración de Skype Empresarial Server y se replican en los almacenes locales del grupo. Para más información, vea [Publishing the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-location-database) en la documentación de implementación.

Esta sección describe qué debe tener en cuenta cuando planea la actualización y el mantenimiento de la base de datos de ubicaciones.

## <a name="planning-emergency-locations"></a>Planear las ubicaciones de emergencia

Cuando se usan puertas de enlace ELIN, se rellena la base de datos del servicio de información de ubicación con la dirección cívica, una ubicación específica dentro de un edificio y al menos un ELIN para cada ubicación. Durante la fase de planeación, le recomendamos que decida el nombre que quiere dar a las ubicaciones y cómo desea asignar los ELIN.

### <a name="planning-location-names"></a>Planear nombres de ubicación

El campo Ubicación del **servicio** de información de ubicación, que contiene la ubicación específica dentro de un edificio, tiene una longitud máxima de 20 caracteres (incluidos los espacios). Dentro de esa longitud limitada, intente incluir lo siguiente:

- Un nombre fácil de comprender que identifique la ubicación del autor de la llamada al 911 para que a los encargados de emergencias les resulte más fácil encontrar rápidamente la ubicación específica cuando lleguen a la dirección postal. Este nombre de ubicación puede incluir un número de edificio, la planta, la escalera, la puerta, etc. Evite los apodos que solo conozcan los empleados, ya que los encargados de emergencias podrían equivocarse de ubicación.

- Un identificador de ubicación que ayuda a los usuarios a ver fácilmente que su cliente ha elegido la ubicación correcta. El cliente de Skype Empresarial concatena automáticamente y muestra los campos **Location** y **City** detectados en su encabezado. Una buena práctica es agregar la dirección de calle del edificio a cada identificador de ubicación (por ejemplo, "1st <street number> Floor"). Si no se indica la calle, un identificador de ubicación genérico como "1ª planta" se podría aplicar a cualquier edificio de la ciudad.

- Si la ubicación es aproximada porque está determinada por un punto de acceso inalámbrico, es posible que desee agregar la palabra **[Cerca]** (por ejemplo, "Near 1st Floor 1234").

### <a name="planning-elins"></a>Planear ELIN

Después de decidir cómo va a dividir el espacio del edificio en ubicaciones, decida cuántos ELIN asignará a cada ubicación. Por ejemplo, en un edificio de varias plantas o inquilinos, puede haber diferentes zonas de emergencia para las diversas áreas del edificio. Por lo general, se considera que cada planta de un edificio es una ubicación. Después, asigne a cada ubicación uno o más ELIN, que se usan como número de llamada durante una llamada de emergencia. Póngase en contacto con el proveedor de RTC para que le dé los números de teléfono para los ELIN. La tabla siguiente proporciona un ejemplo de ubicaciones para una dirección postal concreta.

**Ubicación y asignaciones ELIN de ejemplo**

|**Área del edificio**|**Location**|**ELIN**|
|:-----|:-----|:-----|
|Primera planta  <br/> |1  <br/> |425-555-0100  <br/> |
|Segunda planta  <br/> |2  <br/> |425-555-0111  <br/> |
|Tercera planta  <br/> |3  <br/> |425-555-0123  <br/> |

Las ubicaciones que defina deben:

- Cumplir las normativas nacionales o regionales en cuanto al área máxima por ubicación y número de ubicaciones por dirección postal.

- Tener la concreción suficiente como para que sea fácil ubicar a la persona que realiza la llamada de emergencia.

## <a name="populating-the-location-database"></a>Rellenar la base de datos de ubicaciones

Con las siguientes preguntas le será más fácil determinar cómo rellenar la base de datos de ubicaciones.

 **¿Qué proceso usará para rellenar la base de datos de ubicaciones?**

¿Dónde se encuentran los datos y qué pasos debe realizar para convertirlos al formato que necesita la base de datos de ubicaciones? ¿Agregará las ubicaciones una por una o en bloque con un archivo CSV?

 **¿Dispone de una base de datos de otros fabricantes que ya contenga una asignación de ubicaciones?**

Al usar la opción Servicio de información de ubicación secundaria para conectarse a una base de datos de terceros, puede agrupar y administrar ubicaciones mediante una plataforma sin conexión. La ventana es que además de asociar las ubicaciones a identificadores de red, puede asociar las ubicaciones a un usuario. Esto significa que el servicio de información de ubicación puede devolver varias direcciones, originadas desde el servicio de información de ubicación secundaria, a un cliente de Skype Empresarial. Y el usuario puede elegir la ubicación más adecuada.

Para integrarse con el servicio de información de ubicación, la base de datos de terceros debe seguir el esquema de solicitud y respuesta de ubicación de Skype Empresarial Server. Para obtener más información, [vea Web Service for E911 Support Protocol](/openspecs/office_protocols/ms-e911ws/ab5d7449-2c15-434b-bf65-fdf38b8ffabd). Para obtener más información sobre cómo implementar un servicio de información de ubicación secundaria, vea [Configure a secondary Location Information service in Skype for Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) en la documentación sobre implementación.

Para más información sobre cómo rellenar la base de datos de ubicaciones, vea [Configure the Location Database](/previous-versions/office/lync-server-2013/lync-server-2013-configure-the-location-database) en la documentación sobre implementación.

## <a name="maintaining-the-location-database"></a>Mantener la base de datos de ubicaciones

Una vez rellenada la base de datos de ubicaciones, desarrolle una estrategia para actualizar la base de datos a medida que se produzcan cambios en la configuración de red. Con las siguientes preguntas le será fácil determinar cómo mantener la base de datos de ubicaciones.

 **¿Cómo actualizará la base de datos de ubicaciones?**

Existen diversos escenarios que requieren una actualización de la base de datos de ubicaciones, como agregar puntos de acceso inalámbricos (WAP), cambiar el cableado de una oficina (lo que da lugar a asignaciones de conmutador diferentes) o la expansión de subredes. ¿Actualizará directamente cada ubicación individual o llevará a cabo una actualización en bloque de todas las ubicaciones con un archivo CSV?

 **¿Usará una aplicación SNMP para hacer coincidir las direcciones MAC del cliente de Skype Empresarial con los identificadores de puerto y cambio?**

Si usa una aplicación SNMP, desarrolle un proceso manual para que la información de chasis de conmutador y de puerto sea coherente entre la aplicación SNMP y la base de datos de ubicaciones. Si la aplicación SNMP devuelve una dirección IP de chasis o un identificador de puerto que no se incluye en la base de datos, el servicio de información de ubicación no podrá devolver una ubicación al cliente.