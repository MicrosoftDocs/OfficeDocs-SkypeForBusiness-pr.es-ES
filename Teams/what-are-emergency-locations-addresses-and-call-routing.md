---
title: ¿Cuáles son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?
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
- Adm_Skype4B_Online
- Strat_SB_PSTN
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: d552fe5599a9c1189b20a3efa69f659333d80166
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "30352845"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>¿Cuáles son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?

Al configurar planes de llamada en Office 365, se debe asignar una dirección de emergencia a cada número de teléfono al obtener el número de teléfono o asignar a un usuario para admitir llamadas de emergencia. Y antes de que puede asignar una dirección de emergencia a un número de teléfono, debe crear y validar la dirección de emergencia. La validación garantiza que se reconoce la dirección de emergencia y que se encuentra en un formato correcto que se puede usar servicios de respuesta de emergencia. Opcionalmente, puede agregar una ubicación dentro de la dirección de emergencia para proporcionar una ubicación más específica para el usuario. Por ejemplo, la ubicación de emergencia podría ser un floor, dibujo o la oficina que está vinculada a una dirección específica de emergencia. Aunque se validan la dirección de emergencia, no son ubicaciones.
  
## <a name="what-are-emergency-addresses"></a>¿Qué son las direcciones de emergencia?

Una dirección de emergencia se requiere para números de teléfono activa, pero cuando es necesario depende del país o la región. En los Estados Unidos, se requiere una dirección de emergencia cuando se asigna un número a un usuario. Para otros países, como en Europa, Oriente medio y África (EMEA), emergencia se requiere una dirección cuando se obtiene el número de teléfono de Office 365, o cuando se transfiere desde otro proveedor de servicios o un operador.
  
Una dirección de emergencia es posible que se conoce como una dirección postal, dirección postal o una dirección física. Es la dirección postal o civil del domicilio social de su organización. Por ejemplo, la dirección *que 12345 Norte Main Street, Redmond, WA 98052* se usa para enrutar las llamadas de emergencia a las autoridades de distribución apropiado y para ayudar en la ubicación del autor de llamada de emergencia. Es probable que necesite más de una dirección de emergencia si su empresa tiene más de una ubicación física empresarial.
  
Validar una dirección de emergencia implica asegurarse de que es legítimo y con el formato correcto para los servicios de respuesta de emergencia. Es posible crear y guardar una dirección de emergencia que no se valida, pero sólo validadas direcciones se pueden asociadas a un usuario. Después de validar y guardar una dirección de emergencia, se puede asignar a un usuario. Si necesita cambiar una dirección de emergencia validada y guardada, tendrá que crear una.
  
## <a name="what-are-emergency-locations"></a>¿Qué son las ubicaciones de emergencia?

Una ubicación de emergencia está asociada con una dirección de emergencia para dar a una ubicación dentro de un edificio más exacta. Una ubicación de emergencia es normalmente un piso, el pabellón de un edificio o un número de oficina donde se encuentra el usuario. Puede tener un número ilimitado de ubicaciones asociadas con una dirección de emergencia. 
  
Cuando se asigna una dirección de emergencia a un usuario, es realmente un ID de ubicación que se hace referencia al asignar la dirección. El identificador de ubicación incluye la dirección de emergencia que se hace referencia (la dirección postal o ciudad). Una ubicación de emergencia predeterminada se incluye con una dirección de emergencia para casos en los que no son necesarios en la creación de ubicaciones. 
  
## <a name="what-is-emergency-call-routing"></a>¿Qué es un enrutamiento de llamadas SOS?

Las ubicaciones y las direcciones de emergencias se usan durante el proceso de enrutamiento las llamadas de emergencia al centro de distribución apropiado al distribuir a Respondedores primera emergencias. Cuando un equipos o Skype para usuarios de empresa marca un número de emergencia, cómo se enruta la llamada a la porción punto de respuesta de seguridad pública (PSAP) variará según el país o región. En algunos países, como los Estados Unidos y el Reino Unido, en primer lugar se analizarán las llamadas para determinar la ubicación actual del usuario antes de conectar la llamada al centro de distribución apropiado. En otros países o regiones, las llamadas se enrutarán directamente en el centro de distribución atender el número de teléfono asociado con el autor de llamada de emergencia.
  
## <a name="create-add-and-assign-emergency-locations-and-addresses-to-your-users"></a>Crear, agregar y asignar las ubicaciones de emergencia y direcciones a los usuarios

1. **Planear las ubicaciones de emergencia**. Es el primer paso planear las ubicaciones de emergencias. Necesita obtener una lista de todas las direcciones físicas. A continuación, en función de ello, determine si se necesitan las ubicaciones de las direcciones de emergencias y, si es así, ¿qué son. Por ejemplo, si una empresa tiene 3 edificios de oficinas por cada con 4 plantas, es probable que es necesario que haya 3 direcciones de emergencias, con plantas 1-4 aparece como una ubicación para cada uno.
    
2. **Crear y validar las ubicaciones de emergencias**. El siguiente paso es crear y validar las direcciones de emergencias. Al crear una dirección de emergencia, puede validarla. Para crear una dirección de emergencia, vea [Agregar o quitar una emergencia de direcciones para su organización](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization).
    
    > [!IMPORTANT]
    > Para validar una dirección postal o civil es necesario comprobar que sea legítima y que tenga el formato correcto. Es posible que una dirección de emergencia parcialmente correcta, como un nombre de la ciudad, mal aún es posible que pasan la validación. El proceso de validación usa todas las partes de una dirección específica para determinar si contiene suficiente información para redirigir la llamada al centro de emergencias apropiado. Si es así, se devolverán como validado y, a continuación, se pueden asignar a un número de teléfono. 
  
3. **Obtener los números de teléfono**. El siguiente paso es obtener los números de teléfono para los usuarios. Para ello, obtenga los nuevos números de teléfono de Office 365 o inicie una portabilidad o transfiera sus números de teléfono existentes a Office 365. Para ver los pasos completos, vea [transferir los números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Asignar números de teléfono**. El último paso es permitir a los usuarios realizar y recibir llamadas telefónicas. Para ello, es necesario asignar un número de teléfono a cada usuario. Vea [asignar, cambiar o quitar un número de teléfono de un usuario](/SkypeForBusiness/what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user) para asignar a un número de teléfono.

> [!NOTE]
> Si necesita obtener más números de teléfono, [póngase en contacto con el soporte de productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

    
## <a name="related-topics"></a>Temas relacionados
[¿Qué es la validación de direcciones?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Términos y condiciones de las llamadas de emergencia](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

