---
title: ¿Qué son las ubicaciones de emergencia y el enrutamiento de llamadas?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Descubra qué son las ubicaciones de emergencia, los lugares y el enrutamiento de llamadas de emergencia, y cómo planear y asignarlos a los usuarios. '
ms.openlocfilehash: 4dbfe8d2a10c24ae66967030007328d2b9422e34
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925391"
---
# <a name="what-are-emergency-locations-places-and-call-routing"></a>¿Qué son las ubicaciones de emergencia y el enrutamiento de llamadas?

Al configurar los planes de llamadas, tiene que asignar una ubicación de emergencia a cada número de teléfono al comprar el número de teléfono o al asignarlo a un usuario para que sea compatible con las llamadas de emergencia. Antes de poder asignar una ubicación de emergencia a un número de teléfono, debe agregar y validar una ubicación de emergencia. La validación asegura que la ubicación de emergencia se reconoce y que está en un formato adecuado que pueden usar los servicios de respuesta de emergencia. Si lo desea, puede Agregar un lugar dentro de la ubicación de emergencia para proporcionar una ubicación más específica para el usuario. Por ejemplo, el lugar podría ser un piso, una alas o una oficina que esté vinculada a una ubicación de emergencia específica. A pesar de que las ubicaciones de emergencia se validan, los lugares no.
  
## <a name="what-are-emergency-locations"></a>¿Qué son las ubicaciones de emergencia?

Se necesita una ubicación de emergencia para los números de teléfono activos y, cuando sea necesario, dependerá del país o la región. En los Estados Unidos, se requiere una ubicación de emergencia cuando se asigna un número a un usuario. Para otros países, como Europa, Oriente Medio y África (EMEA), se necesita una ubicación de emergencia cuando recibe el número de teléfono de Teams o cuando se transfiere desde otro proveedor de servicios u operador a teams.
  
Una ubicación de emergencia puede denominarse dirección de ciudad, dirección postal o dirección física con el lugar opcional. Es la calle o la dirección cívica de un lugar de trabajo para su organización. Por ejemplo, la dirección *12345 North Main Street, Redmond, WA 98052* se usa para enrutar llamadas de emergencia a las autoridades de distribución correspondientes y para ayudar a localizar a la persona que llama de emergencia. Es probable que necesites más de una ubicación de emergencia si tu empresa tiene más de una ubicación de empresa física.
  
Validar una dirección de emergencia implica asegurarse de que está correctamente formateada para los servicios de respuesta de emergencia. Es posible agregar y guardar una ubicación de emergencia no validada, pero solo se pueden asociar ubicaciones validadas con un usuario. Una vez validada y guardada una ubicación de emergencia, puede asignarla a un usuario. Para cambiar una ubicación de emergencia guardada y validada, tendrá que crear una nueva.
  
## <a name="what-are-places"></a>¿Qué son los lugares?

Un lugar está asociado a una ubicación de emergencia para dar una ubicación más exacta dentro de un edificio. Un lugar suele ser un piso, un ala de construcción o un número de oficina donde se encuentra el usuario. Puedes tener un número ilimitado de lugares asociados con una dirección de emergencia.
  
Cuando se asigna una ubicación de emergencia a un usuario, en realidad es un identificador de ubicación al que se hace referencia al asignar la ubicación. El identificador de ubicación incluye la dirección de emergencia a la que se hace referencia (la calle o la dirección cívica). Se incluye un lugar predeterminado con una ubicación de emergencia para casos en los que no son necesarios los lugares en los edificios.
  
## <a name="what-is-emergency-call-routing"></a>¿Qué es un enrutamiento de llamadas SOS?

Las ubicaciones y lugares de emergencia se usan durante el proceso de enrutamiento de llamadas de emergencia al centro de distribución correspondiente cuando se distribuyen los primeros respondedores de emergencia. Cuando un usuario de un equipo marca un número de emergencia, el modo en que se dirige la llamada al punto de respuesta de seguridad pública (PSAP) varía según el país y la región. En algunos países, como los Estados Unidos y el Reino Unido, las llamadas se muestran en primer lugar para determinar la ubicación actual del usuario antes de conectar la llamada al centro de distribución correspondiente. En otros países y regiones, las llamadas se dirigen directamente al centro de distribución que atiende el número de teléfono asociado a la persona que llama.
  
## <a name="create-add-and-assign-emergency-locations-and-places-to-your-users"></a>Crear, agregar y asignar ubicaciones y lugares de emergencia a los usuarios

1. **Planear las ubicaciones de emergencia**. El primer paso es planear las ubicaciones de emergencia. Enumera todas tus direcciones físicas. A continuación, en función de eso, determine si se necesitan lugares para las ubicaciones de emergencia y, si es así, qué son. Por ejemplo, si una empresa tiene tres edificios de oficina con cuatro pisos, es probable que tenga que haber tres ubicaciones de emergencia con plantas de una a cuatro como un lugar para cada una de ellas.
    
2. **Agregue sus ubicaciones de emergencia**. El siguiente paso es agregar sus ubicaciones de emergencia. Para obtener más información, vea [Agregar, cambiar o quitar una ubicación de emergencia de su organización](add-change-remove-emergency-location-organization.md).
    
    > [!IMPORTANT]
    > Validar una calle o una dirección cívica implica asegurarse de que el formato es legítimo y correcto. Es posible que una dirección de emergencia parcialmente correcta, como un nombre escrito de la ciudad, pueda seguir pasando la validación. El proceso de validación usa todas las partes de una dirección determinada para determinar si contiene suficiente información para enrutar la llamada al centro de distribución de emergencia adecuado. Si es así, se devolverá como validada y, a continuación, se le puede asignar a un número de teléfono.
  
3. **Obtener números de teléfono**. El siguiente paso es obtener números de teléfono para los usuarios. Para ello, obtenga los nuevos números de teléfono de Office 365 o inicie una portabilidad o transfiera sus números de teléfono existentes a Office 365. Para ver los pasos completos, consulte [transferir números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
    
4. **Asignar números de teléfono**. El último paso es permitir que los usuarios realicen y reciban llamadas telefónicas. Para ello, es necesario asignar un número de teléfono a cada usuario. Consulte [asignar, cambiar o quitar un número de teléfono para que un usuario](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) asigne un número de teléfono.

> [!NOTE]
> Si necesita obtener más números de teléfono, [póngase en contacto con el servicio de asistencia al cliente de RTC](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).

    
## <a name="related-topics"></a>Temas relacionados

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Términos y condiciones de llamadas de emergencia](emergency-calling-terms-and-conditions.md)