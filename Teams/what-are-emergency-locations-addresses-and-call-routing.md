---
title: ¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?
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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: 979fab1cd099d568278efd61d06a3f8a75b04541
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483873"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?

Al configurar planes de llamadas en Office 365, tiene que asignar una dirección de emergencia a cada número de teléfono al obtener el número de teléfono o asignarlo a un usuario para que admita las llamadas de emergencia. Y antes de poder asignar una dirección de emergencia a un número de teléfono, debe crear y validar la dirección de emergencia. La validación asegura que la dirección de emergencia se reconoce y que está en un formato adecuado que pueden usar los servicios de respuesta de emergencia. De manera opcional, puede Agregar una ubicación dentro de la dirección de emergencia para proporcionar una ubicación más específica para el usuario. Por ejemplo, la ubicación de emergencia podría ser un piso, un ala u oficina que está vinculado a una dirección de emergencia específica. Aunque la dirección de emergencia se valida, las ubicaciones no lo son.
  
## <a name="what-are-emergency-addresses"></a>¿Qué son las direcciones de emergencia?

Para los números de teléfono activos se necesita una dirección de emergencia, pero cuando es necesario depende del país o de la región. En los Estados Unidos, se requiere una dirección de emergencia cuando se asigna un número a un usuario. Para otros países, como en Europa, Oriente Medio y África (EMEA), se necesita una dirección de emergencia cuando obtiene el número de teléfono de Office 365 o cuando se transfiere desde otro proveedor u operador de servicios.
  
Una dirección de emergencia puede denominarse dirección de ciudad, dirección postal o dirección física. Es la dirección postal o civil del domicilio social de su organización. Por ejemplo, la dirección *12345 North Main Street, Redmond, WA 98052* se usa para enrutar llamadas de emergencia a las autoridades de distribución correspondientes y para ayudar a localizar a la persona que llama de emergencia. Es probable que necesites más de una dirección de emergencia si tu empresa tiene más de una ubicación de empresa física.
  
Validar una dirección de emergencia implica asegurarse de que es legítima y tiene el formato adecuado para los servicios de respuesta de emergencia. Es posible crear y guardar una dirección de emergencia que no está validada, pero solo se pueden asociar direcciones validadas con un usuario. Después de validar y guardar una dirección de emergencia, se puede asignar a un usuario. Si necesita cambiar una dirección de emergencia validada y guardada, tendrá que crear una.
  
## <a name="what-are-emergency-locations"></a>¿Qué son las ubicaciones de emergencia?

Una ubicación de emergencia está asociada a una dirección de emergencia para proporcionar una ubicación más exacta dentro de un edificio. Una ubicación de emergencia es normalmente un piso, el pabellón de un edificio o un número de oficina donde se encuentra el usuario. Puede tener un número ilimitado de ubicaciones asociadas con una dirección de emergencia. 
  
Al asignar una dirección de emergencia a un usuario, en realidad es un identificador de ubicación al que se hace referencia al asignar la dirección. El identificador de ubicación incluye la dirección de emergencia a la que se hace referencia (la calle o la dirección cívica). Se incluye una ubicación de emergencia predeterminada con una dirección de emergencia para aquellos casos en los que no se necesitan instalaciones de creación. 
  
## <a name="what-is-emergency-call-routing"></a>¿Qué es un enrutamiento de llamadas SOS?

Las direcciones y ubicaciones de emergencia se usan durante el proceso de enrutamiento de llamadas de emergencia al centro de distribución correspondiente cuando se distribuyen los primeros respondedores de emergencia. Cuando un usuario de un equipo o de Skype empresarial marca un número de emergencia, el modo en que se dirige la llamada al punto de respuesta de seguridad pública (PSAP) variará según el país o la región. En algunos países, como los Estados Unidos y el Reino Unido, las llamadas se filtrarán primero para determinar la ubicación actual del usuario antes de conectar la llamada al centro de distribución correspondiente. En otros países o regiones, las llamadas se dirigirán directamente al centro de distribución que atiende el número de teléfono asociado a la persona que llama.
  
## <a name="create-add-and-assign-emergency-locations-and-addresses-to-your-users"></a>Crear, agregar y asignar ubicaciones y direcciones de emergencia a los usuarios

1. **Planear las ubicaciones de emergencia**. El primer paso es planear las ubicaciones de emergencia. Necesitas enumerar todas tus direcciones físicas. A continuación, en función de eso, determine si es necesario tener ubicaciones para las direcciones de emergencia y, si es así, qué son. Por ejemplo, si una empresa tiene 3 edificios de oficina cada uno con 4 pisos, es posible que tenga que haber 3 direcciones de emergencia, con el suelo 1-4 en la lista para cada una de ellas.
    
2. **Cree y valide sus ubicaciones de emergencia**. El siguiente paso es crear y validar las direcciones de emergencia. Al crear una dirección de emergencia, puede validarla. Para crear una dirección de emergencia, consulte [Agregar o quitar una dirección de emergencia para su organización](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization).
    
    > [!IMPORTANT]
    > Para validar una dirección postal o civil es necesario comprobar que sea legítima y que tenga el formato correcto. Es posible que una dirección de emergencia parcialmente correcta, como un nombre escrito de la ciudad, pueda seguir pasando la validación. El proceso de validación usa todas las partes de una dirección específica para determinar si contiene suficiente información para redirigir la llamada al centro de emergencias apropiado. Si es así, se devolverá como validada y, a continuación, se le puede asignar a un número de teléfono. 
  
3. **Obtener números de teléfono**. El siguiente paso es obtener números de teléfono para los usuarios. Para ello, obtenga los nuevos números de teléfono de Office 365 o inicie una portabilidad o transfiera sus números de teléfono existentes a Office 365. Para ver los pasos completos, consulte [transferir números de teléfono a Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Asignar números de teléfono**. El último paso es permitir que los usuarios realicen y reciban llamadas telefónicas. Para ello, es necesario asignar un número de teléfono a cada usuario. Consulte [asignar, cambiar o quitar un número de teléfono para que un usuario](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) asigne un número de teléfono.

> [!NOTE]
> Si necesita obtener más números de teléfono, [póngase en contacto con el soporte de productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

    
## <a name="related-topics"></a>Temas relacionados
[¿Qué es la validación de direcciones?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Diferentes tipos de números de teléfono que se usan para planes de llamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

