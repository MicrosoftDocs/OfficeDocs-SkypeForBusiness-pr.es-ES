---
title: Administrar las ubicaciones de las puertas de enlace de ELIN en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Decisiones necesarias para planear una base de datos de información de ubicación o una base de datos externa similar, para una implementación de E9 con puertas de enlace de ELIN, en Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 39e6c4170adc18687b284ec6f69a252c6efefab4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803040"
---
# <a name="manage-locations-for-elin-gateways-in-skype-for-business-server"></a>Administrar las ubicaciones de las puertas de enlace de ELIN en Skype empresarial Server

Decisiones necesarias para planear una base de datos de información de ubicación o una base de datos externa similar, para una implementación de E9 con puertas de enlace de ELIN, en Skype empresarial Server Enterprise Voice.

Para que Skype empresarial Server proporcione automáticamente ubicaciones para clientes dentro de una red, debe realizar las siguientes tareas:

- Rellene la información de ubicación de la base de datos del servicio con un Wiremap de red e incluya los números de identificación de ubicación de emergencia (ELINs) en el campo NombreCompañía.

- Publica las ubicaciones para que estén disponibles para los clientes en tu red.

- Carga los ELIN en la base de datos de identificación de ubicación automática (ALI) del proveedor de la red telefónica conmutada (RTC).

Para obtener más información sobre la ejecución de estas tareas, mira [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) en la documentación de implementación.

> [!NOTE]
> Las ubicaciones que se agreguen a la base de datos de ubicación central no estarán disponibles para el cliente hasta que se hayan publicado con un comando del shell de administración de Skype empresarial Server y se repliquen en las tiendas locales del grupo. Para obtener más información, mira [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) en la documentación de implementación.

Esta sección describe qué necesitas tener en cuenta cuando planificas la actualización y el mantenimiento de la base de datos de ubicaciones.

## <a name="planning-emergency-locations"></a>Planificar las ubicaciones de emergencia

Cuando use puertas de enlace ELIN, deberá rellenar la base de datos de servicios de información de ubicación con la dirección cívica, una ubicación específica dentro de un edificio y, al menos, una ELIN para cada ubicación. Durante la fase de planificación, recomendamos que decidas el nombre que quieras dar a las ubicaciones y cómo deseas asignar los ELIN.

### <a name="planning-location-names"></a>Planificar nombres de ubicación

El campo **Ubicación** del servicio de información de ubicación, que contiene la ubicación específica dentro de un edificio, tiene una longitud máxima de 20 caracteres (incluidos los espacios). Dentro de esa longitud limitada, intenta incluir lo siguiente:

- Un nombre fácil de comprender que identifique la ubicación del autor de la llamada al 911 para que a los encargados de emergencias les resulte más fácil encontrar rápidamente la ubicación específica cuando lleguen a la dirección postal. Este nombre de ubicación puede incluir un número de edificio, la planta, la escalera, la puerta, etc. Evita los apodos que solo conozcan los empleados, ya que los encargados de emergencias podrían equivocarse de ubicación.

- Un identificador de ubicación que permita a los usuarios ver fácilmente que su cliente ha recogido la ubicación correcta. El cliente de Skype empresarial concatena automáticamente y muestra los campos **Ubicación** detectada y **ciudad** en el encabezado. Una buena práctica es agregar la dirección del edificio a cada identificador de ubicación (por ejemplo, "primer piso <street number>"). Sin la calle, un identificador genérico como "1.ª planta" podría referirse a cualquier edificio de la ciudad.

- Si la ubicación es aproximada porque está determinada por un punto de acceso inalámbrico, es posible que desee agregar la palabra **[cerca]** (por ejemplo, "cerca del primer piso 1234").

### <a name="planning-elins"></a>Planificar ELIN

Después de decidir cómo vas a dividir el espacio del edificio en ubicaciones, necesitas decidir cuántos ELIN asignarás a cada ubicación. Por ejemplo, en un edificio de varias plantas o varios inquilinos, puede haber diferentes zonas de emergencia para las diversas áreas del edificio. Por lo general, se considera que cada planta de un edificio es una ubicación. Después, asigna a cada ubicación uno o más ELIN, que se usan como número(s) de llamada durante una llamada de emergencia. Ponte en contacto con tu proveedor de RTC para que te brinde los números de teléfono que puedes usar para los ELIN. La tabla siguiente proporciona un ejemplo de ubicaciones para una dirección postal concreta.

**Ubicación y asignaciones de ELIN de ejemplo**

|**Área del edificio**|**Ubicación**|**ELIN**|
|:-----|:-----|:-----|
|Primera planta  <br/> |1  <br/> |425-555-0100  <br/> |
|Segunda planta  <br/> |1  <br/> |425-555-0111  <br/> |
|Tercera planta  <br/> |3  <br/> |425-555-0123  <br/> |

Las ubicaciones que definas necesitan:

- Cumplir las normativas nacionales o regionales en cuanto al área máxima por ubicación y a la cantidad de ubicaciones por dirección postal.

- Tener la precisión suficiente como para que sea fácil ubicar a la persona que realiza la llamada de emergencia.

## <a name="populating-the-location-database"></a>Rellenar la base de datos de ubicaciones

Con las siguientes preguntas te será más fácil determinar cómo rellenar la base de datos de ubicaciones.

 **¿Qué proceso usará para rellenar la base de datos de ubicaciones?**

¿Dónde se encuentran los datos y qué pasos necesitas realizar para convertirlos al formato que necesita la base de datos de ubicaciones? ¿Agregarás las ubicaciones una por una o en bloque con un archivo CSV?

 **¿Dispone de una base de datos de otros fabricantes que ya contenga una asignación de ubicaciones?**

Al usar la opción servicio de información de ubicación secundaria para conectarse a una base de datos de terceros, puede agrupar y administrar ubicaciones mediante una plataforma sin conexión. La ventaja es que además de asociar las ubicaciones a identificadores de red, puedes asociar las ubicaciones a un usuario. Esto significa que el servicio de información de ubicación puede devolver varias direcciones, que se originan en el servicio de información de ubicación secundaria, a un cliente de Skype empresarial. Luego, el usuario podrá elegir la ubicación más adecuada.

Para integrar con el servicio de información de ubicación, la base de datos de terceros debe seguir el esquema de solicitud/respuesta de la ubicación del servidor de Skype empresarial. Para obtener más información, vea [servicio web para el protocolo de soporte técnico de E911](https://go.microsoft.com/fwlink/p/?linkid=213819). Para obtener detalles sobre cómo implementar un servicio de información de ubicación secundaria, vea [configurar un servicio de información de ubicación secundaria en Skype empresarial Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) en la documentación de implementación.

Para obtener más información sobre cómo rellenar la base de datos de ubicaciones, mira [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) en la documentación sobre implementación.

## <a name="maintaining-the-location-database"></a>Mantener la base de datos de ubicaciones

Una vez rellenada la base de datos de ubicaciones, desarrolla una estrategia para actualizar la base de datos a medida que se produzcan cambios en la configuración de red. Con las siguientes preguntas te será fácil determinar cómo mantener la base de datos de ubicaciones.

 **¿Cómo actualizará la base de datos de ubicaciones?**

Existen diversos escenarios que requieren una actualización de la base de datos de ubicaciones, como agregar puntos de acceso inalámbricos (WAP), cambiar el cableado de una oficina (lo que da lugar a asignaciones de conmutador diferentes) o la expansión de subredes. ¿Actualizarás directamente cada ubicación individual o llevarás a cabo una actualización en bloque de todas las ubicaciones con un archivo CSV?

 **¿Usará una aplicación SNMP para que las direcciones MAC de cliente de Skype empresarial coincidan con los identificadores de puertos y conmutadores?**

Si usas una aplicación SNMP, necesitas desarrollar un proceso manual para mantener sincronizada la información de conmutadores y puertos entre la aplicación SNMP y la base de datos de ubicaciones. Si la aplicación SNMP devuelve una dirección IP del chasis o un identificador de puerto que no está incluido en la base de datos, el servicio de información de ubicación no podrá devolver una ubicación al cliente.


