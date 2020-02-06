---
title: Administrar las ubicaciones de los proveedores de servicios de tronco de SIP en Skype empresarial Server
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
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Decisiones necesarias para planear una base de datos de información de ubicación o una base de datos externa similar, para una implementación E9-1-1 con proveedores de Troncalización SIP, Skype empresarial Server Enterprise Voice.
ms.openlocfilehash: 81ec257b30d2916bb4df2a4590b9abfc1b270375
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802730"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Administrar las ubicaciones de los proveedores de servicios de tronco de SIP en Skype empresarial Server

Decisiones necesarias para planear una base de datos de información de ubicación o una base de datos externa similar, para una implementación E9-1-1 con proveedores de Troncalización SIP, Skype empresarial Server Enterprise Voice.

Para configurar Skype empresarial Server para ubicar automáticamente los clientes dentro de una red, debe rellenar la base de datos del servicio de información de ubicación con un Wiremap de red y publicar las ubicaciones o vincular a una base de datos externa que ya contiene las asignaciones correctas. Como parte de este proceso, necesitas validar las direcciones postales con el proveedor de servicios de E9-1-1. Para obtener más información, mira [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) en la documentación sobre implementación.

Rellena la base de datos del servicio de información de ubicaciones con una ubicación de respuesta de emergencia (ERL), formada por una dirección postal y la dirección específica en un edificio. El campo **Ubicación** del servicio de información de ubicación, que es la ubicación específica dentro de un edificio, tiene una longitud máxima de 20 caracteres (incluidos los espacios). Dentro de esa longitud limitada, intenta incluir lo siguiente:

- Un nombre fácil de comprender que identifique la ubicación del autor de la llamada al 911 para que a los encargados de emergencias les resulte más fácil encontrar rápidamente la ubicación específica cuando lleguen a la dirección postal. Este nombre de ubicación puede incluir un número de edificio, la planta, la escalera, la puerta, etc. Evita los apodos que solo conozcan los empleados, ya que los encargados de emergencias podrían equivocarse de ubicación.

- Un identificador de ubicación que permite a los usuarios ver fácilmente que su cliente de Skype empresarial seleccionó la ubicación correcta. El cliente de Skype empresarial concatena automáticamente y muestra los campos **Ubicación** detectada y **ciudad** en el encabezado. Una buena práctica es agregar la dirección del edificio a cada identificador de ubicación (por ejemplo, "primer piso <street number>"). Sin la calle, un identificador genérico como "1.ª planta" podría referirse a cualquier edificio de la ciudad.

- Si la ubicación es aproximada porque está determinada por un punto de acceso inalámbrico, puede Agregar la palabra **[Near]** (por ejemplo, "cerca del primer piso 1234").

> [!NOTE]
> Las ubicaciones que se agreguen a la base de datos de ubicación central no estarán disponibles para el cliente hasta que se publiquen mediante un comando de Shell de administración de Skype empresarial Server y se repliquen en las tiendas locales del grupo. Para obtener más información, mira [Publishing the Location Database](https://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) en la documentación de implementación.

En las secciones siguientes se describen consideraciones que necesitas tener en cuenta a la hora de rellenar y mantener la base de datos de ubicaciones.

## <a name="populating-the-location-database"></a>Rellenar la base de datos de ubicaciones

Con las siguientes preguntas te será fácil determinar cómo rellenar la base de datos de ubicaciones.

 **¿Qué proceso usará para rellenar la base de datos de ubicaciones?**

¿Dónde se encuentran los datos y qué pasos necesitas realizar para convertirlos al formato que necesita la base de datos de ubicaciones? ¿Agregarás las ubicaciones una por una o en bloque con un archivo CSV?

 **¿Dispone de una base de datos de otros fabricantes que ya contenga una asignación de ubicaciones?**

Al usar la opción servicio de información de ubicación secundaria para conectarse a una base de datos de terceros, puede agrupar y administrar ubicaciones mediante una plataforma sin conexión. La ventaja es que además de asociar las ubicaciones a identificadores de red, puedes asociar las ubicaciones a un usuario. Esto significa que el servicio de información de ubicación puede devolver varias direcciones, que se originan en el servicio de información de ubicación secundaria, a un cliente de Skype empresarial. Luego, el usuario podrá elegir la ubicación más adecuada.

Para integrar con el servicio de información de ubicación, la base de datos de terceros debe seguir el esquema de solicitud/respuesta de la ubicación de Lync Server. Para obtener más información, consulte ["[ms-E911WS]: servicio web para la especificación del Protocolo de soporte técnico de E911"](https://go.microsoft.com/fwlink/p/?linkid=213819). Para obtener detalles sobre cómo implementar un servicio de información de ubicación secundaria, vea [configurar un servicio de información de ubicación secundaria en Skype empresarial Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) en la documentación de implementación.

Para obtener más información sobre cómo rellenar la base de datos de ubicaciones, mira [Configure the Location Database](https://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) en la documentación sobre implementación.

## <a name="maintaining-the-location-database"></a>Mantener la base de datos de ubicaciones

Una vez rellenada la base de datos de ubicaciones, desarrolla una estrategia para actualizar la base de datos a medida que se produzcan cambios en la configuración de red. Con las siguientes preguntas te será fácil determinar cómo mantener la base de datos de ubicaciones.

 **¿Cómo actualizará la base de datos de ubicaciones?**

Existen diversos escenarios que requieren una actualización de la base de datos de ubicaciones, como agregar WAP, cambiar el cableado de una oficina (lo que da lugar a asignaciones de conmutador nuevas) y la expansión de subredes. ¿Actualizarás directamente cada ubicación o llevarás a cabo una actualización en bloque de todas las ubicaciones con un archivo CSV?

 **¿Usará una aplicación SNMP para hacer coincidir las direcciones MAC del cliente Lync con los identificadores de conmutadores y puertos?**

Si usas una aplicación SNMP, necesitas desarrollar un proceso manual para mantener sincronizada la información de conmutadores y puertos entre la aplicación SNMP y la base de datos de ubicaciones. Si la aplicación SNMP devuelve una dirección IP del chasis o un identificador de puerto que no está incluido en la base de datos, el servicio de información de ubicación no podrá devolver una ubicación al cliente.


