---
title: Administración de ubicaciones para proveedores de servicios de tronco SIP en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
description: Las decisiones necesarias para la planeación de una base de datos de información de la ubicación, o una base de datos externa similar, para una implementación de E9-1-1 con los proveedores de enlace troncal SIP, en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 079e921debe9e5b61839795e61db199a018879aa
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20996777"
---
# <a name="manage-locations-for-sip-trunk-service-providers-in-skype-for-business-server"></a>Administración de ubicaciones para proveedores de servicios de tronco SIP en Skype para Business Server
 
Las decisiones necesarias para la planeación de una base de datos de información de la ubicación, o una base de datos externa similar, para una implementación de E9-1-1 con los proveedores de enlace troncal SIP, en Skype para Business Server Enterprise Voice.
  
Para configurar Skype para Business Server ubicar automáticamente los clientes dentro de una red, es necesario rellenar la base de datos del servicio de información de ubicación con un diagrama de cables de red y publique las ubicaciones o bien vincular a una base de datos externa que ya contiene las asignaciones correctas. Como parte de este proceso, necesitas validar las direcciones postales con el proveedor de servicios de E9-1-1. Para obtener información detallada, vea [Configurar la base de datos de la ubicación](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) en la documentación de implementación.
  
Rellena la base de datos del servicio de información de ubicaciones con una ubicación de respuesta de emergencia (ERL), formada por una dirección postal y la dirección específica en un edificio. El campo de **ubicación** de servicio de información de ubicación, que es la ubicación específica dentro de un edificio, tiene una longitud máxima de 20 caracteres (incluidos los espacios). Dentro de esa longitud limitada, intenta incluir lo siguiente:
  
- Un nombre fácil de comprender que identifique la ubicación del autor de la llamada al 911 para que a los encargados de emergencias les resulte más fácil encontrar rápidamente la ubicación específica cuando lleguen a la dirección postal. Este nombre de ubicación puede incluir un número de edificio, la planta, la escalera, la puerta, etc. Evita los apodos que solo conozcan los empleados, ya que los encargados de emergencias podrían equivocarse de ubicación.
    
- Un identificador de ubicación que ayuda a los usuarios a ver fácilmente que sus Skype para cliente empresarial obtenida la ubicación correcta. El Skype para clientes empresariales concatena y muestra los campos de **ubicación** y **Ciudad** detectados en su encabezado automáticamente. Es una práctica recomendada agregar la dirección postal del edificio a cada identificador de ubicación (por ejemplo, "1ª planta <street number>"). Sin la calle, un identificador genérico como "1.ª planta" podría referirse a cualquier edificio de la ciudad.
    
- Si la ubicación es aproximada porque está determinada por un punto de acceso inalámbrico, puede agregar la palabra **[cerca]** (por ejemplo, "cerca 1ª planta 1234").
    
> [!NOTE]
> Las ubicaciones agregadas a la base de datos de ubicación central no están disponibles para el cliente hasta que se publican mediante el uso de un Skype para el comando de Shell de administración de servidor empresarial y se replican en tiendas locales del grupo de servidores. Para obtener información detallada, consulte [la base de datos de la ubicación de publicación](http://technet.microsoft.com/library/dd032b5b-df0e-4017-ac46-e17570c1ab1e.aspx) en la documentación de implementación.
  
En las secciones siguientes se describen consideraciones que necesitas tener en cuenta a la hora de rellenar y mantener la base de datos de ubicaciones.
  
## <a name="populating-the-location-database"></a>Rellenar la base de datos de ubicaciones

Con las siguientes preguntas te será fácil determinar cómo rellenar la base de datos de ubicaciones.
  
 **¿Qué proceso usará para rellenar la base de datos de ubicaciones?**
  
¿Dónde se encuentran los datos y qué pasos necesitas realizar para convertirlos al formato que necesita la base de datos de ubicaciones? ¿Agregarás las ubicaciones una por una o en bloque con un archivo CSV? 
  
 **¿Dispone de una base de datos de otros fabricantes que ya contenga una asignación de ubicaciones?**
  
Mediante el uso de la opción de servicio de información de ubicación secundaria para conectarse a una base de datos de terceros, puede agrupar y administrar ubicaciones mediante el uso de una plataforma sin conexión. La ventaja es que además de asociar las ubicaciones a identificadores de red, puedes asociar las ubicaciones a un usuario. Esto significa que el servicio de información de ubicación puede devolver varias direcciones, que se originan desde el servicio de información de ubicación secundaria a una Skype para clientes empresariales. Luego, el usuario podrá elegir la ubicación más adecuada. 
  
Para integrar con el servicio de información de ubicación, la base de datos de terceros debe seguir el esquema de solicitud y respuesta de Lync Server ubicación. Para obtener información detallada, vea ["[MS-E911WS]: servicio Web para la especificación del protocolo E911 compatibilidad con"](https://go.microsoft.com/fwlink/p/?linkid=213819). Para obtener información detallada sobre la implementación de un servicio de información de ubicación secundaria, vea [Configure un servicio de información de ubicación secundario en Skype para Business Server](../../deploy/deploy-enterprise-voice/secondary-location-information-service.md) en la documentación de implementación.
  
Para obtener información detallada sobre cómo rellenar la base de datos de ubicación, vea [Configure la base de datos de la ubicación](http://technet.microsoft.com/library/8544be31-6958-47ef-b926-fdc80d56191c.aspx) en la documentación de implementación.
  
## <a name="maintaining-the-location-database"></a>Mantener la base de datos de ubicaciones

Una vez rellenada la base de datos de ubicaciones, desarrolla una estrategia para actualizar la base de datos a medida que se produzcan cambios en la configuración de red. Con las siguientes preguntas te será fácil determinar cómo mantener la base de datos de ubicaciones.
  
 **¿Cómo actualizará la base de datos de ubicaciones?**
  
Existen diversos escenarios que requieren una actualización de la base de datos de ubicaciones, como agregar WAP, cambiar el cableado de una oficina (lo que da lugar a asignaciones de conmutador nuevas) y la expansión de subredes. ¿Actualizarás directamente cada ubicación o llevarás a cabo una actualización en bloque de todas las ubicaciones con un archivo CSV?
  
 **¿Usará una aplicación SNMP para hacer coincidir las direcciones MAC del cliente Lync con los identificadores de conmutadores y puertos?**
  
Si usas una aplicación SNMP, necesitas desarrollar un proceso manual para mantener sincronizada la información de conmutadores y puertos entre la aplicación SNMP y la base de datos de ubicaciones. Si la aplicación SNMP devuelve un identificador IP de chasis dirección o el puerto que no está incluido en la base de datos, el servicio de información de ubicación no podrán devolver una ubicación para el cliente.
  

