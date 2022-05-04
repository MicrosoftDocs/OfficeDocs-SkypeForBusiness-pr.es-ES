---
title: Aplicación Walkie Talkie en Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Cómo configurar la aplicación Walkie Talkie en Microsoft Teams, desde una perspectiva de ITAdmin.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 776f0f31d54788fbffd86bbcbedd44e30ada28a3
ms.sourcegitcommit: ad8447b683381bc07f993bf843a93a4bdb77d840
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "65186976"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Aplicación Walkie Talkie en Microsoft Teams

La aplicación Walkie Talkie de Teams proporciona una comunicación instantánea de inserción para hablar (PTT) para su equipo y ahora está disponible en Android & iOS. Walkie Talkie permite a los usuarios conectarse con su equipo mediante los mismos canales subyacentes de los que son miembros. Solo los usuarios que se conectan a Walkie Talkie en un canal se convierten en participantes y pueden comunicarse entre sí mediante pulsar para hablar, de uno en uno.

Con Walkie Talkie en Teams, los trabajadores de primera línea ahora pueden comunicarse de forma segura con una experiencia de PTT familiar sin tener que transportar radios voluminosas, y Walkie Talkie funciona en cualquier lugar con WiFi o conectividad a Internet móvil.

## <a name="getting-started"></a>Introducción

### <a name="deploying-walkie-talkie"></a>Implementar Walkie Talkie

Walkie Talkie es compatible con dispositivos Android con Google Mobile Services (GMS) y dispositivos iOS.

### <a name="pin-walkie-talkie-to-teams"></a>Anclar walkie talkie a Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>Usa la experiencia de aplicación frontline adaptada para anclar Walkie Talkie y otras aplicaciones a Teams

La experiencia de aplicación frontline adaptada en Teams ancla las aplicaciones más relevantes en Teams para los usuarios que tienen una [licencia F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Entre las aplicaciones ancladas se incluyen Walkie Talkie, Turnos, Tareas y Aprobaciones. De forma predeterminada, esta característica está activada, lo que ofrece a sus trabajadores de primera línea una experiencia predefinida que se adapta a sus necesidades.

Las aplicaciones se anclan a la barra de aplicaciones (la barra situada en el lateral de la Teams cliente de escritorio y en la parte inferior de los clientes móviles Teams), donde los usuarios pueden acceder a ellas de forma rápida y sencilla.

Para obtener más información, incluido cómo funciona la experiencia con las directivas de aplicaciones que establezca, vea [Personalizar las aplicaciones de Teams para los trabajadores de primera línea](pin-teams-apps-based-on-license.md).

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>Usa una directiva de configuración de aplicaciones para anclar walkie talkie a Teams

Las directivas de configuración de aplicaciones le permiten personalizar Teams para anclar aplicaciones que son más importantes para los usuarios de los usuarios.

Para anclar la aplicación Walkie Talkie a los usuarios, puede editar la directiva global (predeterminada para toda la organización) o crear y asignar una directiva de configuración de aplicación personalizada. Para obtener más información, consulte [Administrar las directivas de configuración de aplicaciones en Teams](teams-app-setup-policies.md).

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Captura de pantalla que muestra cómo agregar Walkie Talkie a la lista de aplicaciones ancladas en el panel Agregar aplicaciones ancladas." lightbox="media/deploy-walkie-talkie-2.png":::

### <a name="network-documentation"></a>Documentación de red

Walkie Talkie en Teams requiere conectividad a Internet y bajo las condiciones de red son necesarias para una experiencia óptima.

|Métrica | Obligatorio |
|---|---|
|Latencia (RTT) | < 300 ms |
|Vibración |< 30 ms |
|Pérdida de paquetes |< 1 % |

Como se mencionó anteriormente, la calidad de los medios en tiempo real a través de una red IP se ve muy afectada por la calidad de la conectividad de red, pero especialmente por la cantidad de:

- **Latencia** : este es el tiempo que se tarda en obtener un paquete IP desde el punto A hasta el punto B en la red. Este retraso de propagación de red está esencialmente vinculado a la distancia física entre los dos puntos y la velocidad de la luz, incluida una mayor sobrecarga tomada por los diversos routers en medio. La latencia se mide como tiempo de ida y vuelta (RTT).
- **Vibración entre llegadas** - Este es el cambio medio en el retraso entre paquetes sucesivos.
- **Pérdida de paquetes** : esto a menudo se define como un porcentaje de paquetes que se pierden en un período de tiempo determinado. La pérdida de paquetes afecta directamente a la calidad del audio, desde pequeños paquetes perdidos individuales que casi no tienen impacto, hasta pérdidas de ráfagas posteriores que provocan un corte de audio completo.

El uso de datos esperado de Walkie Talkie es de unos 20 Kb/s al enviar o recibir audio. Cuando está inactivo, el uso de datos esperado del Walkie Talkie es insignificante.

### <a name="walkie-talkie-devices"></a>Dispositivos Walkie Talkie

Los trabajadores de primera línea a menudo necesitan hablar y recibir llamadas walkie talkie incluso cuando sus teléfonos están bloqueados. Esta experiencia es posible a través de dispositivos especializados con un botón PTT dedicado.

- **Auriculares**
  - Auriculares inalámbricos (iOS & Android)
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - Auriculares con cable (solo Android)
    - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **Teléfonos Android resistentes**
  - Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - Configuración manual: con Teams instalado, ve a Configuración > funciones avanzadas > tecla XCover/Active. Activa la tecla Control XCover con la aplicación y selecciona "Teams"
    - [Configuración de MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - Cebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - Configuración manual: con Teams instalado, el botón PTT dedicado (LEFT_TRIGGER_2) funciona con walkie talkie de forma predeterminada
    
> [!NOTE]
> Estos dispositivos no están Teams certificados. Han sido validados para trabajar con Teams Walkie Talkie.

### <a name="license-requirements"></a>Requisitos de licencia

La aplicación Walkie Talkie se incluye en todas las licencias de pago de Teams en [suscripciones de Office 365](/office365/servicedescriptions/teams-service-description). Para obtener más información sobre cómo obtener Teams, echa un vistazo  [Cómo obtener acceso a Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?

## <a name="further-information"></a>Más información

- Los administradores de TI pueden mantener el control sobre quién usa Walkie Talkie a través de directivas de aplicaciones.
- Si el trabajador de primera línea usa datos móviles para comunicarse a través de Teams, Walkie Talkie usará el mismo método.
- Walkie Talkie debería funcionar bien en situaciones de poco ancho de banda o en situaciones en las que el smartphone esté conectado y funcionando. Walkie-talkie no funcionará cuando no haya conectividad en absoluto.

Para obtener más información sobre la experiencia del usuario final, consulte:

- [Comenzar con Teams Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Comuníquese con su equipo con Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
