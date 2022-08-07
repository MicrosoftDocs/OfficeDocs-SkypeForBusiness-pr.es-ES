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
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo Microsoft admite la información de ubicación despachable para admitir las llamadas de emergencia.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9efa5f6e9ad5b5f2434efb95265f58c9a603fdd5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272075"
---
# <a name="emergency-addresses-for-remote-locations"></a>Direcciones de emergencia para ubicaciones remotas

En este artículo se describe la información de ubicación del soporte técnico de Microsoft para llamadas de emergencia del 911 en el Estados Unidos. Este soporte técnico garantiza que se proporcione la información de ubicación más precisa posible para los usuarios de Teams que realicen llamadas de emergencia. Independientemente de la ubicación del autor de la llamada (in situ o trabajando desde casa), la información de ubicación del autor de la llamada enviada al Punto de respuesta de seguridad pública (PSAP) debe ser precisa.

Este artículo incluye información sobre el cumplimiento por parte de Microsoft de la Ley de ray BAUM para sistemas telefónicos de varias líneas (MLTS). La Ley ray BAUM extiende los requisitos de la Ley de Kari, que entró en vigor a principios de 2021. Para obtener más información sobre la Ley de RAY BAUM y la Ley de Kari, consulte [Ubicación despachable para llamadas 911](https://www.fcc.gov/911-dispatchable-location) y [Sistemas telefónicos de varias líneas– Ley de Kari y Ley 911 de RAY BAUM, Requisitos de Marcado Directo, Notificación y Ubicación Despachable](https://www.fcc.gov/mlts-911-requirements). 

Los usuarios que trabajan en casa ahora pueden establecer sus propias direcciones de emergencia si procede. En este artículo se describe cómo configurar directivas de usuario para que los usuarios finales puedan establecer sus direcciones de emergencia.

Aunque esta información se aplica a las llamadas de emergencia del 911 en el Estados Unidos, las ubicaciones introducidas por el usuario también se transmitirán al centro de detección de Canadá.

Este artículo contiene las siguientes secciones:

- [Soporte técnico para la información de ubicación de llamadas de emergencia](#support-for-emergency-calling-location-information)
- [Prioridad de ubicación](#location-precedence)
- [Clasificación y enrutamiento de las direcciones de emergencia](#emergency-address-classification-and-routing)
- [Permitir que los usuarios finales configuren su dirección de emergencia](#enable-end-users-to-configure-their-emergency-address)
- [Notas y restricciones](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>Soporte técnico para la información de ubicación de llamadas de emergencia

Para admitir estos requisitos, Teams usa los servicios de ubicación proporcionados por el sistema operativo correspondiente para sugerir una dirección si el administrador o el usuario le concede permiso. El usuario final puede confirmar la ubicación de una dirección sugerida, editarla o escribir manualmente una nueva. Una dirección confirmada, editada o especificada manualmente se guarda en el cliente de Teams para que la dirección confirmada por el usuario se use automáticamente cuando el cliente esté conectado a esa red. Las direcciones guardadas por el usuario se borran automáticamente cuando se ha cerrado la sesión del cliente de Teams.


## <a name="location-precedence"></a>Prioridad de ubicación

Las direcciones de emergencia de Teams se pueden clasificar por diferentes tipos. La siguiente lista muestra la prioridad de ubicación que se usa cuando se marca un número de emergencia:

1. Una dirección adquirida dinámicamente definida por el inquilino administrado en el servicio de información de ubicación.

2. Una dirección que el usuario final confirmó, editó o escribió manualmente y que está asociada a la red local a la que está conectado el cliente de Teams.

3. Una dirección sugerida automáticamente por el sistema operativo.

4. Una dirección que el administrador asigna estáticamente al usuario.


## <a name="emergency-address-classification-and-routing"></a>Clasificación y enrutamiento de las direcciones de emergencia

En la tabla siguiente se muestran los tipos de direcciones de emergencia y métodos de enrutamiento asociados para cada tipo: si la llamada se enruta automáticamente al PSAP de servicio o si se comprueba la precisión antes de transferirla al PSAP de servicio. Este comportamiento de enrutamiento es compatible con el Estados Unidos para todos los usuarios del plan de llamadas, los asociados de conexión de operadores y los proveedores de servicios de llamadas de emergencia certificados para Direct Routing.


| Tipo de dirección de emergencia | Método de enrutamiento de emergencia |
| :------------| :-------|
| Dirección de emergencia adquirida dinámicamente definida por el administrador. | Directo a PSAP. |
| Dirección de emergencia obtenida del sistema operativo **sin confirmación de precisión** por parte del usuario. | En pantalla y transferida a PSAP. |
| Dirección de emergencia obtenida del sistema operativo **con confirmación de precisión** por parte del usuario.| Directo a PSAP. |
| Dirección de emergencia obtenida del sistema operativo y editada y confirmada por el usuario. | En pantalla y transferida a PSAP. |
| Dirección de emergencia especificada y confirmada por el usuario. | En pantalla y transferida a PSAP. |
| Dirección de emergencia asignada estáticamente al usuario o número. | En pantalla y transferida a PSAP. |
| Null | En pantalla y transferida a PSAP. |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>Permitir que los usuarios finales configuren su dirección de emergencia

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Directivas de emergencia** de **voz** > .
2. Seleccione **Agregar**.
3. Escriba un nombre para la directiva de llamadas de emergencia, por ejemplo, "E911WFH".
4. Activar el **modo de búsqueda ubicación externa**.
5. Seleccione **Aplicar**.

#### <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Asignar una directiva de llamadas de emergencia personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="using-powershell"></a>Con PowerShell

Para habilitar esta característica para los usuarios finales, use el cmdlet de New-CsTeamsEmergencyCallingPolicy PowerShell y establezca el parámetro ExternalLocationLookupMode en Enabled. Vea el siguiente ejemplo: 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

Después de habilitar esta característica para los usuarios finales, en la pestaña Llamadas, el usuario puede agregar, editar o confirmar una dirección de emergencia y mostrar la dirección una vez establecida. Para obtener más información sobre cómo los usuarios finales pueden establecer los servicios de ubicación, consulte [Trabajo desde el hogar Emergencia 911: habilitar los servicios de ubicación](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live).

En Windows, puede administrar el servicio de ubicación de Windows, y si las aplicaciones tienen acceso a la ubicación, mediante una directiva de grupo o mediante la [administración de dispositivos móviles (MDM)](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation).

Para obtener más información sobre el servicio de ubicación de Windows, consulta [Servicio de ubicación de Windows y privacidad](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).



## <a name="notes-and-restrictions"></a>Notas y restricciones

Tenga en cuenta lo siguiente:

- La experiencia profesional desde el hogar descrita es para equipos de escritorio de Teams en Windows y Mac.

- Los teléfonos de Teams no admiten la experiencia del trabajo desde el hogar.

- Teams Mobile admite la detección automática de ubicación, pero no la experiencia especificada por el usuario descrita.

- La configuración de privacidad puede entrar en conflicto con la detección automática de ubicación: se pueden usar sistemas de Administración de dispositivos móviles.


## <a name="related-topics"></a>Temas relacionados

- [Administrar las llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)

- [Trabajo desde El servicio de emergencia doméstica 911: habilitar los servicios de ubicación](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)

