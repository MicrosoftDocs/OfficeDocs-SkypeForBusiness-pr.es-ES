---
title: ¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: 8a437920f1ba901addbdc626e2d5a6bfad5779a4
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>¿Qué son las ubicaciones de emergencia, las direcciones y el enrutamiento de llamadas?

Al configurar planes de llamada Office 365, se requiere que se asigne una dirección de emergencia para cada número de teléfono cuando se obtiene el número de teléfono o su asignado a un usuario para admitir llamadas de emergencia. Antes de asignar una dirección de emergencia a un número de teléfono, una dirección de emergencia debe ser creada y validada. La validación asegura que se reconoce la dirección de emergencia y que está en el formato correcto que se puede utilizar los servicios de respuesta de emergencia. Opcionalmente, puede agregarse a una ubicación dentro de la dirección de emergencia para proporcionar una ubicación más específica para el usuario. Por ejemplo, la ubicación de emergencia podría ser un piso, ala o la oficina que está vinculada a una dirección específica de emergencia. Aunque se validan la dirección de emergencia, no son ubicaciones.
  
## <a name="what-are-emergency-addresses"></a>¿Qué son las direcciones de emergencia?

Una dirección de emergencia es necesaria para los números de teléfono activa, pero cuando se requiere depende del país o región. En los Estados Unidos, una dirección de emergencia es **necesaria** cuando se asigna un número a un usuario. Para otros países, como en Europa, Oriente medio y África (EMEA), una dirección de emergencia es **necesario** cuando se obtiene el número de teléfono de Office 365, o cuando se transfiere desde otro proveedor de servicios o la portadora.
  
Una dirección de emergencia puede denominarse como una dirección cívica, dirección postal o una dirección física. Es la dirección postal o civil del domicilio social de su organización. Por ejemplo, la dirección *que 12345 North Main Street, Redmond, WA 98052* se utiliza para enrutar las llamadas de emergencia a las autoridades de expedición adecuado y ayudar a localizar el llamador de emergencia. Es probable que necesite más de una dirección de emergencia si su empresa tiene más de una ubicación física del negocio.
  
Validar una dirección de emergencia implica asegurarse de que es legítimo y con el formato correcto para los servicios de respuesta de emergencia. Es posible crear y guardar una dirección de emergencia no está validada, pero se pueden asociadas a un usuario sólo direcciones validadas. Después de validar y guardar una dirección de emergencia, se puede asignar a un usuario. Si necesita cambiar una dirección de emergencia validada y guardada, tendrá que crear una.
  
## <a name="what-are-emergency-locations"></a>¿Qué son las ubicaciones de emergencia?

Ubicaciones de emergencia están asociados a una dirección de emergencia para dar una ubicación más exacta dentro de un edificio. Una ubicación de emergencia es normalmente un piso, el pabellón de un edificio o un número de oficina donde se encuentra el usuario. Puede tener un número ilimitado de ubicaciones asociadas con una dirección de emergencia. 
  
Cuando se asigna a un usuario una dirección de emergencia, es realmente un ID de ubicación que se hace referencia cuando se asigna la dirección. El ID de ubicación incluye la dirección de emergencia que se hace referencia (la dirección postal o ciudad). Una ubicación predeterminada de emergencia se incluye con una dirección para el caso de emergencia cuando no son necesarios en la creación de ubicaciones. 
  
## <a name="what-is-emergency-call-routing"></a>¿Qué es un enrutamiento de llamadas SOS?

Ubicaciones y direcciones de emergencia se utilizan durante el proceso de enrutamiento llamadas de emergencia al centro de distribución apropiado al distribuir equipos de primera respuesta. Cuando un Skype para usuarios de empresa marca un número de emergencia, cómo se enruta la llamada a la porción pública seguridad contestando punto (PSAP) varían según el país o región. En algunos países, como Estados Unidos y el Reino Unido, en primer lugar se analizarán las llamadas para determinar la ubicación actual del usuario antes de conectar la llamada al centro de distribución apropiado. En otros países o regiones, las llamadas se enrutarán directamente al centro de expedición que sirve el número de teléfono asociado con el llamador de emergencia.
  
## <a name="creating-adding-and-assigning-emergency-locations-and-addresses-to-your-users"></a>Crear, agregar y asignar ubicaciones de emergencia y direcciones de los usuarios

1. **Plan de emergencia ubicaciones** Es el primer paso planear las ubicaciones de emergencia. Debe enumerar todas las direcciones físicas. A continuación, en función de ello, determine si son necesarias las ubicaciones para las direcciones de emergencia y si es así, cuáles son. Por ejemplo, si una empresa tiene 3 edificios cada uno con 4 pisos, es probable que necesite ser 3 direcciones de emergencia, con pisos de 1-4 aparece como una ubicación para cada uno.
    
2. **Crear y validar las ubicaciones de emergencia**: el paso siguiente es crear y validar las direcciones de emergencia. Al crear una dirección de emergencia, puede validarla. Para crear una dirección de emergencia, vea [Agregar o quitar una emergencia la dirección de su organización](add-or-remove-an-emergency-address-for-your-organization.md).
    
    > [!IMPORTANT]
    > Para validar una dirección postal o civil es necesario comprobar que sea legítima y que tenga el formato correcto. Es posible que una dirección de emergencia que sea correcta parcialmente (como un nombre de ciudad mal escrito) pase la validación. El proceso de validación usa todas las partes de una dirección específica para determinar si contiene suficiente información para redirigir la llamada al centro de emergencias apropiado. Si es así, se devolverá como validado y, a continuación, puede asignarse a un número de teléfono. 
  
3. **Obtener números de teléfono** El siguiente paso es obtener los números de teléfono de los usuarios. Para ello, obtenga los nuevos números de teléfono de Office 365 o inicie una portabilidad o transfiera sus números de teléfono existentes a Office 365. Para ver los pasos completos, vea [transferir números de teléfono para Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Asignar números de teléfono**: el último paso es habilitar a los usuarios para que puedan realizar y recibir llamadas de teléfono. Para ello, es necesario asignar un número de teléfono a cada usuario. Vea [asignar, cambiar o quitar un número de teléfono de un usuario](assign-change-or-remove-a-phone-number-for-a-user.md) para asignar a un número de teléfono.

> [!NOTE]
> Si necesita obtener más números de teléfono, [póngase en contacto con el soporte de productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

    
## <a name="related-topics"></a>Temas relacionados
[¿Qué es la validación de direcciones?](what-is-address-validation.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Términos y condiciones de las llamadas de emergencia](../what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions.md)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 