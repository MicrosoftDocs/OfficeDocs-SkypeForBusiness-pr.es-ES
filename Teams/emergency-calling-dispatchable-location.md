---
title: Direcciones de emergencia para ubicaciones remotas
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo Microsoft admite la información de ubicación de envío para admitir llamadas de emergencia.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7d241cee858d3ac19747be56b5a53e157b563f64
ms.sourcegitcommit: 05e7c8ac9d6d6f712742d08820d43118c8949bbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2021
ms.locfileid: "61323009"
---
# <a name="emergency-addresses-for-remote-locations"></a>Direcciones de emergencia para ubicaciones remotas

En este artículo se describe el soporte técnico de Microsoft para la información de ubicación de llamadas de emergencia 911 en Estados Unidos. Este soporte garantiza que se proporciona la información de ubicación de envío más precisa posible para Teams usuarios que hacen llamadas de emergencia. Independientemente de la ubicación del autor de la llamada (en el lugar o trabajando desde casa), la información de ubicación de una persona que llama enviada al Punto de respuesta de seguridad pública (PSAP) debe ser precisa.

En este artículo se incluye información sobre el cumplimiento de Microsoft con la Ley de RAY BAUM para sistemas telefónicos de varias líneas (MLTS). La Ley de RAY BAUM amplía los requisitos de la Ley de Kari, que entró en vigor a principios de 2021. Para obtener más información sobre la Ley de RAY BAUM y la Ley de Kari, vea Ubicación de envío para llamadas y sistemas telefónicos de varias líneas [de 911:](https://www.fcc.gov/911-dispatchable-location) La ley de Kari y la Ley [911](https://www.fcc.gov/mlts-911-requirements)de RAY BAUM Requisitos de marcado directo, notificación y ubicación de distribución. 

Los usuarios que trabajan en casa ahora pueden establecer sus propias direcciones de emergencia si procede. En este artículo se describe cómo puede configurar directivas de usuario para que los usuarios finales puedan establecer sus direcciones de emergencia.

Aunque esta información se aplica a las llamadas de emergencia 911 en Estados Unidos, las ubicaciones especificadas por el usuario también se transmitirán al centro de detección de Canadá.

Este artículo contiene las secciones siguientes:

- [Soporte técnico para la información de ubicación de llamadas de emergencia](#support-for-emergency-calling-location-information)
- [Prioridad de ubicación](#location-precedence)
- [Clasificación y enrutamiento de direcciones de emergencia](#emergency-address-classification-and-routing)
- [Permitir a los usuarios finales configurar su dirección de emergencia](#enable-end-users-to-configure-their-emergency-address)
- [Notas y restricciones](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>Soporte técnico para la información de ubicación de llamadas de emergencia

Para admitir estos requisitos, Teams los servicios de ubicación proporcionados por el sistema operativo correspondiente para sugerir una dirección, si el administrador o el usuario le conceden permiso. El usuario final puede confirmar la ubicación de una dirección sugerida, editarla o escribir manualmente una nueva. Después, se guarda una dirección confirmada, editada o especificada manualmente en el cliente de Teams para que la dirección confirmada por el usuario se usa automáticamente cuando el cliente está conectado a esa red. Las direcciones guardadas por el usuario se borran automáticamente cuando el Teams se ha iniciado sesión.


## <a name="location-precedence"></a>Prioridad de ubicación

Las direcciones de Teams pueden clasificarse por diferentes tipos. En la lista siguiente se muestra la prioridad de ubicación que se usa cuando se marca un número de emergencia:

1. Una dirección adquirida dinámicamente definida por el inquilino administrado en el Servicio de información de ubicación.

2. Una dirección a la que el usuario final confirmó, editó o introdujo manualmente que está asociada a la red local a la que Teams cliente está conectado.

3. Una dirección sugerida automáticamente por el sistema operativo.

4. Una dirección que el administrador asigna estáticamente al usuario.


## <a name="emergency-address-classification-and-routing"></a>Clasificación y enrutamiento de direcciones de emergencia

En la tabla siguiente se muestran los tipos de direcciones de emergencia y los métodos de enrutamiento asociados para cada tipo: si la llamada se enruta automáticamente al PSAP de servicio o se realiza una prueba de precisión antes de transferirla al PSAP de servicio. Este comportamiento de enrutamiento es compatible en Los Estados Unidos para todos los usuarios del Plan de llamadas, operadores Conectar asociados y proveedores de servicios de llamadas de emergencia certificados por Enrutamiento directo.


| Tipo de dirección de emergencia | Método de enrutamiento de emergencia |
| :------------| :-------|
| Dirección de emergencia adquirida dinámicamente definida por el administrador. | Directo a PSAP. |
| Dirección de emergencia obtenida del sistema operativo sin confirmación **de precisión** por parte del usuario. | Se han proyectado y transferido a PSAP. |
| Dirección de emergencia obtenida del sistema operativo con **confirmación de precisión** por parte del usuario.| Directo a PSAP. |
| Dirección de emergencia obtenida del sistema operativo y editada y confirmada por el usuario. | Se han proyectado y transferido a PSAP. |
| Dirección de emergencia especificada y confirmada por el usuario. | Se han proyectado y transferido a PSAP. |
| Dirección de emergencia asignada estáticamente al usuario o número. | Se han proyectado y transferido a PSAP. |
| Null | Se han proyectado y transferido a PSAP. |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>Permitir a los usuarios finales configurar su dirección de emergencia

Para habilitar esta característica para los usuarios finales, use el cmdlet New-CsTeamsEmergencyCallingPolicy PowerShell y establezca el parámetro ExternalLocationLookupMode en Habilitado. Vea el siguiente ejemplo: 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

Después de habilitar esta característica para los usuarios finales, desde la pestaña Llamadas, el usuario puede agregar, editar o confirmar una dirección de emergencia y mostrar la dirección después de establecerla. 

En Windows, puede administrar el servicio de ubicación de Windows y si las aplicaciones tienen acceso a la ubicación, mediante la directiva de grupo o mediante la administración de dispositivos móviles [(MDM).](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation)

Para obtener más información sobre Windows de ubicación, [vea Windows de ubicación y privacidad.](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)



## <a name="notes-and-restrictions"></a>Notas y restricciones

Tenga en cuenta lo siguiente:

- La experiencia de trabajo desde casa descrita es para Teams escritorio en Windows y Mac.

- Teams teléfonos no admiten la experiencia de trabajo desde casa.

- Teams móvil admite la detección automática de ubicación, pero no la experiencia especificada por el usuario.

- La configuración de privacidad puede estar en conflicto con la detección automática de la ubicación: se pueden usar sistemas de administración de dispositivos móviles.


## <a name="related-topics"></a>Temas relacionados

[Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)

