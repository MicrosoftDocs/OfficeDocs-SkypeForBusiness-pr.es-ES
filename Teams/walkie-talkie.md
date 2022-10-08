---
title: Aplicación Walkie Talkie en Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Cómo configurar la aplicación Walkie Talkie en Microsoft Teams desde la perspectiva del administrador de TI.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: cbce17ad584fdd4910f11129d2b246e4644e1583
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377308"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Aplicación Walkie Talkie en Microsoft Teams

La aplicación Walkie Talkie de Teams proporciona una comunicación instantánea de inserción para hablar (PTT) para su equipo y está disponible en Android e iOS. Walkie Talkie permite a los usuarios conectarse con su equipo mediante los mismos canales subyacentes de los que son miembros. Solo los usuarios que se conectan a Walkie Talkie en un canal se convierten en participantes y pueden comunicarse entre sí mediante el uso de push-to-talk, de uno en uno.

Con Walkie Talkie en Teams, los trabajadores de primera línea pueden comunicarse de forma segura con una experiencia de PTT familiar sin tener que transportar radios voluminosas, y Walkie Talkie funciona en cualquier lugar con conectividad a Internet móvil o WiFi.

> [!NOTE]
> Walkie Talkie no está disponible actualmente en China.

## <a name="license-requirements"></a>Requisitos de licencia

Walkie Talkie se incluye en todas las licencias de pago de Teams en [Las suscripciones de Microsoft 365 y Office 365](/office365/servicedescriptions/teams-service-description). Para obtener más información sobre cómo obtener Teams, consulte [Cómo obtener acceso a Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?

## <a name="deploying-walkie-talkie"></a>Implementar Walkie Talkie

Walkie Talkie es compatible con dispositivos Android con Google Mobile Services (GMS) y dispositivos iOS.

> [!NOTE]
> Si los usuarios usan accesorios Bluetooth, asegúrate de que la solución de administración de dispositivos móviles (MDM) no bloquee los dispositivos Bluetooth.

### <a name="enable-or-disable-walkie-talkie-in-your-organization"></a>Habilitar o deshabilitar Walkie Talkie en su organización

Walkie-talkie está habilitado de forma predeterminada para todos los usuarios de Teams de su organización. Puede desactivar o activar la aplicación en el nivel de organización en la página [Administrar aplicaciones](manage-apps.md) del Centro de administración de Microsoft Teams.

1. En el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. En la lista de aplicaciones, busca la aplicación Walkie Talkie, selecciónala y cambia el botón de alternancia **Estado** a **Bloqueada** o **Permitida**.

### <a name="enable-or-disable-walkie-talkie-for-specific-users-in-your-organization"></a>Habilitar o deshabilitar Walkie Talkie para usuarios específicos de su organización

Para permitir o impedir que usuarios específicos de su organización usen Walkie Talkie, asegúrese de que Walkie Talkie está activado para su organización en la página [Administrar aplicaciones](manage-apps.md) . A continuación, cree una directiva de permisos de aplicación personalizada, agréguela a una directiva de configuración de la aplicación y asígnela a esos usuarios. Para obtener más información, consulte [Administrar directivas de permisos de aplicaciones en Teams](teams-app-permission-policies.md) y [Administrar directivas de configuración de aplicaciones en Microsoft Teams](teams-app-setup-policies.md).

### <a name="pin-walkie-talkie-to-teams"></a>Anclar Walkie Talkie a Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>Usar la experiencia de aplicación frontline adaptada para anclar Walkie Talkie y otras aplicaciones a Teams

La experiencia de aplicación de primera línea adaptada en Teams ancla las aplicaciones más relevantes en Teams para los usuarios que tienen una [licencia F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Entre las aplicaciones ancladas se incluyen Walkie Talkie, Turnos, Tareas y Aprobaciones. De forma predeterminada, esta característica está activada, lo que ofrece a sus trabajadores de primera línea una experiencia predefinida que se adapta a sus necesidades.

Las aplicaciones se anclan en la barra de aplicaciones (la barra situada en el lateral del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams), donde los usuarios pueden acceder a ellas de forma rápida y sencilla.

Para obtener más información, incluido cómo funciona la experiencia con las directivas de aplicaciones que establezca, consulte [Personalizar las aplicaciones de Teams para los trabajadores de primera línea](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>Usar una directiva de configuración de aplicación para anclar Walkie Talkie a Teams

Las directivas de configuración de aplicaciones le permiten personalizar Teams para anclar las aplicaciones que son más importantes para los usuarios de sus usuarios.

Para anclar la aplicación Walkie Talkie a los usuarios, puede editar la directiva global (predeterminada para toda la organización) o crear y asignar una directiva de configuración de aplicación personalizada. Para obtener más información, consulte [Administrar las directivas de configuración de aplicaciones en Teams](teams-app-setup-policies.md).

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Captura de pantalla que muestra cómo agregar Walkie Talkie a la lista de aplicaciones ancladas en el panel Agregar aplicaciones ancladas." lightbox="media/deploy-walkie-talkie-2.png":::

## <a name="network-documentation"></a>Documentación de red

Walkie Talkie en Teams requiere conectividad a Internet. Las siguientes condiciones de red son necesarias para una experiencia óptima.

|Métrica | Obligatorio |
|---|---|
|Latencia (RTT) | < 300 ms |
|Vibración |< 30 ms |
|Pérdida de paquetes |< 1 % |

Como se mencionó anteriormente, la calidad de los medios en tiempo real a través de una red IP se ve muy afectada por la calidad de la conectividad de red, pero especialmente por la cantidad de:

- **Latencia** : el tiempo que se tarda en obtener un paquete IP desde el punto A hasta el punto B en la red. Este retraso de propagación de red está esencialmente vinculado a la distancia física entre los dos puntos y la velocidad de la luz, incluida una mayor sobrecarga tomada por los diversos routers en medio. La latencia se mide como tiempo de ida y vuelta (RTT).
- **Vibración entre llegadas** : el cambio medio en el retraso entre paquetes sucesivos.
- **Pérdida de** paquetes: la pérdida de paquetes se define a menudo como un porcentaje de paquetes perdidos en un período de tiempo determinado. La pérdida de paquetes afecta directamente a la calidad del audio, desde pequeños paquetes perdidos individualmente que casi no tienen impacto, hasta pérdidas de ráfagas posteriores que provocan un corte de audio completo.

El uso de datos esperado de Walkie Talkie es de unos 20 Kb/s al enviar o recibir audio. Cuando está inactivo, el uso de datos esperado del Walkie Talkie es insignificante.

## <a name="walkie-talkie-devices"></a>Dispositivos Walkie Talkie

Los trabajadores de primera línea a menudo necesitan hablar y recibir llamadas walkie talkie incluso cuando sus teléfonos están bloqueados. Esta experiencia es posible a través de dispositivos especializados con un botón PTT dedicado.

#### <a name="headsets"></a>Auriculares

- Auriculares inalámbricos (iOS y Android)
  - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- Auriculares con cable (solo Android)
  - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)

#### <a name="rugged-android-phones"></a>Teléfonos Android resistentes

- Crosscall [Core-X4](https://www.crosscall.com/en_FR/core-s4-1004010501053.html), [Core-M5](https://www.crosscall.com/en_FR/core-m5-1001011101114.html), [Action-X5](https://www.crosscall.com/en_FR/action-x5-1001020701220.html), [Core-X5](https://www.crosscall.com/en_FR/core-x5-1001010701695.html) y [Core-T5](https://www.crosscall.com/en_FR/core-t5-1003011401749.html)
  - Configuración manual: Con Teams instalado, vaya a **Botones** **de configuración** > . En el botón Dedicado (1 o 2), seleccione **Prensa larga** y, a continuación, elija **Aplicación PTT**. Seleccione la rueda azul junto a **Personalizado** y seleccione **Teams**.
- Kyocera [DuraForce Ultra 5G](https://kyoceramobile.com/duraforce-ultra-5g/) y [DuraSport 5G](https://kyoceramobile.com/durasport-5g/)
  - Configuración manual: Con Teams instalado, vaya a **Configuración** >  de **teclas programables**. Elija la **tecla PTT** o **mantenga presionado** (en función del dispositivo) y seleccione **Teams**.
- Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
  - Configuración manual: Con Teams instalado, vaya a **Configuración** >  Características  > **avanzadas****XCover/Tecla activa**. Active **la tecla Control XCover con la aplicación** y seleccione **Teams**.
  - [Configuración de MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
- Sonim [XP8](https://www.sonimtech.com/products/devices/xp8/)
  - Configuración manual: Con Teams instalado, vaya a **Configuración** >  de **claves programables**. Elija **Seleccionar aplicación clave de PTT** y seleccione **Teams**.
- Cebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html), [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html), [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html), [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html), [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html), [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html), [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
  - Configuración manual: con Teams instalado, el botón de PTT dedicado (LEFT_TRIGGER_2) funciona con Walkie Talkie de forma predeterminada.

> [!NOTE]
> Estos dispositivos no están certificados para Teams. Se han validado para trabajar con Walkie Talkie de Teams.

## <a name="more-information"></a>Más información

- Si el trabajador de primera línea usa datos móviles para comunicarse a través de Teams, Walkie Talkie usará el mismo método.
- Walkie Talkie debería funcionar bien en situaciones de poco ancho de banda o en situaciones en las que el smartphone esté conectado y funcionando. Walkie-talkie no funcionará cuando no haya conectividad en absoluto.

Para obtener más información sobre la experiencia del usuario final, vea:

- [Introducción a Walkie Talkie de Teams](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Comuníquese con su equipo con Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
