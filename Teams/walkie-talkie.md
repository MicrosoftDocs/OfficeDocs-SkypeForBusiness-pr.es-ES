---
title: Aplicación Walkie-talkie en Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Cómo configurar la aplicación Walkie-talkie en Microsoft Teams desde una perspectiva de ITAdmin.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63cd853b8a068e7acfc5752e3cd94b5d0102bc2f
ms.sourcegitcommit: 04eba352d9e203aa9cd1282c4f4c7158a0469678
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2021
ms.locfileid: "49944595"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Aplicación Walkie-talkie en Microsoft Teams

La aplicación Walkie-talkie de Teams proporciona comunicación instantánea de pulsar y hablar (PTT) para su equipo y ahora está disponible en Android. Walkie-talkie permite a los usuarios conectarse con su equipo usando los mismos canales subyacentes a los que son miembros. Solo los usuarios que se conectan a Walkie-talkie en un canal se convierten en participantes y pueden comunicarse entre sí mediante pulsar para hablar, de uno en uno.

Con Walkie-talkie en Teams, los trabajadores de la línea frontal ahora se pueden comunicar de forma segura con una conocida experiencia PTT sin tener que transportar radios masivos, y Walkie-talkie funciona en cualquier lugar con conectividad a Internet wiFi o móvil.

## <a name="getting-started"></a>Introducción

### <a name="deploying-walkie-talkie"></a>Implementar Walkie-talkie

Actualmente, Walkie-talkie no está preinstalado. Para habilitar esta característica para los usuarios de su organización, [](teams-app-setup-policies.md)debe agregar Walkie-talkie a la directiva de configuración de aplicaciones asignada a los usuarios desde el   Centro de administración de [Teams.](https://admin.teams.microsoft.com/)

Una vez habilitada, Walkie-talkie estará disponible en la aplicación para Android en 48 horas.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Agregar Walkie-talkie a la lista de aplicaciones

En el Centro de administración de Microsoft Teams, en las directivas de configuración de la aplicación **Teams,** debería tener La opción Permitir anclación  >   **de** usuario establecida en **En.** A continuación, en la sección Aplicaciones ancladas, haga clic **en +Agregar aplicaciones.**

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Muestra la sección de aplicaciones ancladas y el botón Agregar aplicaciones que se va a seleccionar.":::

En el **panel Agregar aplicaciones ancladas** que aparece  a la derecha, use el cuadro de texto buscar Walkie-talkie. Cuando lo tenga como resultado de  una búsqueda, haga clic en el botón Agregar situado a la derecha del nombre para agregarlo a la lista.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Muestra la barra lateral Agregar aplicaciones ancladas con Walkie introducido en el panel de búsqueda y la aplicación Walkie-talkie en los resultados de búsqueda, con el botón Agregar junto a él.":::

La aplicación Walkie-talkie debería aparecer ahora en la lista de aplicaciones ancladas y estar disponible para su uso cuando hagas clic en **el botón** Guardar.

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Muestra la lista de aplicaciones ancladas con la aplicación Walkie-talkie agregada y el botón Guardar debajo de la lista.":::

### <a name="network-documentation"></a>Documentación de red

Walkie-talkie en Teams requiere conectividad a Internet y por debajo de las condiciones de red son necesarias para una experiencia óptima.

|Métrica | Obligatorio |
|---|---|
|Latencia (RTT) | < 300 ms |
|Vibración |< 30 ms |
|Pérdida de paquetes |< 1 % |

Como se indicó anteriormente, la calidad de los medios en tiempo real sobre una red IP se encuentra muy afectada por la calidad de la conectividad de la red, pero especialmente por la cantidad de:

- **Latencia:** este es el tiempo que se tarda en obtener un paquete IP desde el punto A al punto B en la red. Este retraso en la propagación por la red básicamente está vinculado a la distancia física entre los dos puntos y a la velocidad de luz, incluidas las sobrecargas adicionales tomadas por los diversos enrutadores entre ellos. La latencia se mide como tiempo de ida y vuelta (RTT).
- **Pérdida de paquetes:** esto se suele definir como un porcentaje de paquetes que se pierden en un determinado período de tiempo. La pérdida de paquetes afecta directamente a la calidad del audio: desde pérdidas pequeñas e individuales de paquetes que apenas afecten al audio, hasta pérdidas de ráfagas completas que causen cortes completos de audio.
- **Vibración:** este es el cambio medio de retraso entre paquetes sucesivos.

El uso de datos esperado de Walkie-talkie es de aproximadamente 20 KB/s al enviar o recibir audio. Cuando está inactivo, el uso de datos esperado de Walkie-talkie es negligible.

### <a name="walkie-talkie-devices"></a>Dispositivos Walkie-talkie

Los trabajadores de primera línea a menudo necesitan hablar y recibir llamadas de Walkie-talkie, incluso cuando sus teléfonos están bloqueados. Esta experiencia es posible a través de dispositivos especializados con un botón PTT dedicado.

- Auriculares
  - Auriculares cableados[(Usb Electronics)](https://www.kleinelectronics.com/poc-accessories/mtwt/)
  - Auriculares inalámbricos[(Jabra BlueParrott)](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- Teléfonos escarpados
  - Samsung Galaxy XCover Pro
    - [Más información.](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)
    - [Guía de configuración.](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> Estos dispositivos no están certificados para Teams. Se han validado para trabajar con Walkie-talkie de Teams.

### <a name="license-requirements"></a>Requisitos de licencia

La aplicación Walkie-talkie se incluye en todas las licencias pagadas de Teams en [las suscripciones de Office 365.](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing) Para obtener más información sobre cómo obtener Teams, consulte [¿Cómo obtendría acceso a Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

> [!NOTE]
> Algunas características avanzadas pueden requerir licencias adicionales. Por ejemplo, la integración con Samsung Galaxy XCover Pro requiere una licencia Knox.

## <a name="further-information"></a>Más información

- Los administradores de IT pueden mantener el control sobre quién usa Walkie-talkie a través de las directivas de aplicaciones.
- Si su trabajador de la línea frontal usa datos móviles para comunicarse a través de Teams, Walkie-talkie usará el mismo método.
- Walkie-talkie debe funcionar bien en situaciones de ancho de banda bajo o en situaciones en las que tu smartphone esté conectado y funcionando. Walkie-talkie no funcionará cuando no haya conectividad.

Para obtener más información sobre la experiencia del usuario final, vea:

- [Introducción a Walkie-talkie de Teams](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Comunicarse con su equipo con Walkie-talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
