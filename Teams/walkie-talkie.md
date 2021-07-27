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
ms.openlocfilehash: c1e7391163ec41d385b99cab4ae6d135892284e2
ms.sourcegitcommit: 330b5c3e299ddad5168958e4722d1e0b987372e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "53536736"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Aplicación Walkie Talkie en Microsoft Teams

La aplicación Walkie Talkie de Teams proporciona una comunicación instantánea push-to-talk (PTT) para su equipo y ahora está disponible en Android. Walkie Talkie permite a los usuarios conectarse con su equipo con los mismos canales subyacentes de los que son miembros. Solo los usuarios que se conectan a Walkie Talkie en un canal se convierten en participantes y pueden comunicarse entre sí mediante push-to-talk, de uno en uno.

Con Walkie Talkie en Teams, los trabajadores de primera línea ahora pueden comunicarse de forma segura con una experiencia de PTT familiar sin necesidad de llevar radios abultantes, y Walkie Talkie funciona en cualquier lugar con conexión a Internet WiFi o telefonía móvil.

## <a name="getting-started"></a>Introducción

### <a name="deploying-walkie-talkie"></a>Implementar Walkie Talkie

Actualmente, Walkie Talkie está disponible para dispositivos Android con Google Mobile Services (GMS) y no está preinstalado. Para habilitar esta característica para los usuarios de su organización, [](teams-app-setup-policies.md)debe agregar Walkie Talkie a la directiva de configuración de aplicaciones asignada a los usuarios desde el Centro de administración de   [Teams.](https://admin.teams.microsoft.com/) Una vez habilitado, Walkie Talkie estará disponible en la aplicación Android en un plazo de 48 horas.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Agregar Walkie Talkie a la lista de aplicaciones

En el Microsoft Teams de administración, en Teams directivas de configuración de la aplicación, debería tener permitir la anclación de  >  usuario establecida en  **On**. A continuación, en la sección Aplicaciones ancladas, haga clic **en +Agregar aplicaciones.**

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Muestra la sección Aplicaciones ancladas y el botón Agregar aplicaciones que se va a seleccionar.":::

En el **panel** Agregar aplicaciones ancladas que aparece  a la derecha, use el cuadro de texto Buscar para buscar Walkie Talkie. Cuando lo tenga como resultado de  búsqueda, seleccione el botón Agregar a la derecha del nombre para agregarlo a la lista.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Muestra la barra lateral Agregar aplicaciones ancladas con Walkie escrito en el panel de búsqueda y la aplicación Walkie Talkie en los resultados de búsqueda, con el botón Agregar junto a ella.":::

La aplicación Walkie Talkie ahora debería aparecer en la lista Aplicaciones ancladas y estar disponible para su uso una vez que haga clic en **el botón** Guardar.

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Muestra la lista de aplicaciones ancladas con la aplicación Walkie Talkie agregada y el botón Guardar debajo de la lista.":::

### <a name="network-documentation"></a>Documentación de red

Walkie Talkie en Teams requiere conectividad a Internet y por debajo de las condiciones de red se requieren para una experiencia óptima.

|Métrica | Obligatorio |
|---|---|
|Latencia (RTT) | < 300 ms |
|Vibración |< 30 ms |
|Pérdida de paquetes |< 1% |

Como se ha indicado anteriormente, la calidad de los medios en tiempo real a través de una red IP se encuentra muy afectada por la calidad de la conectividad de red, pero especialmente por la cantidad de:

- **Latencia:** este es el tiempo que se tarda en obtener un paquete IP desde el punto A hasta el punto B de la red. Este retraso de propagación de red está esencialmente vinculado a la distancia física entre los dos puntos y la velocidad de la luz, incluida una mayor sobrecarga de los distintos enrutadores entre sí. La latencia se mide como Tiempo de ida y vuelta (RTT).
- **Vibración entre llegadas:** este es el cambio medio de retraso entre paquetes sucesivos.
- **Pérdida de paquetes:** a menudo se define como un porcentaje de paquetes que se pierden en una ventana de tiempo determinada. La pérdida de paquetes afecta directamente a la calidad de audio, desde pequeños paquetes perdidos individuales que casi no tienen impacto, hasta pérdidas de ráfagas back-to-back que provocan un corte total de audio.

El uso de datos esperado de Walkie Talkie es de unos 20 Kb/s al enviar o recibir audio. Cuando está inactivo, el uso de datos esperados de Walkie Talkie es insignificante.

### <a name="walkie-talkie-devices"></a>Dispositivos Walkie Talkie

Los trabajadores de primera línea a menudo necesitan hablar y recibir llamadas de Walkie Talkie incluso cuando sus teléfonos están bloqueados. Esta experiencia es posible a través de dispositivos especializados con un botón PTT dedicado.

- **Auriculares**
  - Auriculares inalámbricos 
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - Auriculares con cable 
    - [Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **Teléfonos resistentes**
  - Samsung [Galaxy XCover Pro,](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/) [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    -  Configuración manual: con Teams instalado, vaya a Configuración > características avanzadas > XCover/Active key. Activa "Tecla Control XCover con la aplicación" y selecciona "Teams"
    -  [Configuración de MDM](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> Estos dispositivos no están Teams certificado. Se han validado para trabajar con Teams Walkie Talkie.

### <a name="license-requirements"></a>Requisitos de licencia

La aplicación Walkie Talkie se incluye en todas las licencias de pago de Teams en [Office 365 suscripciones.](/office365/servicedescriptions/teams-service-description) Para obtener más información sobre cómo obtener Teams, consulte [¿Cómo puedo obtener acceso](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)a Microsoft Teams?

> [!NOTE]
> Algunas características avanzadas pueden requerir licencias adicionales. Por ejemplo, la integración con Samsung Galaxy XCover Pro requiere una licencia knox.

## <a name="further-information"></a>Más información

- Los administradores de IT pueden mantener el control sobre quién usa Walkie Talkie a través de directivas de aplicaciones.
- Si el trabajador de primera línea usa datos móviles para comunicarse Teams, Walkie Talkie usará el mismo método.
- Walkie Talkie debe funcionar bien en situaciones de ancho de banda bajos o situaciones en las que el smartphone está conectado y funcionando. Walkie Talkie no funcionará cuando no haya ninguna conectividad.

Para obtener más información sobre la experiencia del usuario final, vea:

- [Introducción a Teams Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Comunicarse con su equipo con Walkie Talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
