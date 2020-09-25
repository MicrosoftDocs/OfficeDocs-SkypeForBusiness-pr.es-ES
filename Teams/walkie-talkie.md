---
title: Aplicación de walkie talkie en Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Cómo configurar la aplicación de talkie de walkie en Microsoft Teams, desde una perspectiva de ITAdmin.
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
ms.openlocfilehash: 605ba58582210c71561cd60442aa66f97be0be0d
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262508"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Aplicación talkie de walkie en Microsoft Teams

La aplicación walkie talkie de Teams ofrece una comunicación instantánea (PTT) instantánea para su equipo y ahora está disponible en Android. Walkie talkie permite que los usuarios se conecten con su equipo usando los mismos canales subyacentes de los que son miembros. Solo los usuarios que se conectan a walkie talkie de un canal se convierten en participantes y pueden comunicarse entre sí usando Push para hablar, de uno en uno.

Con walkie talkie en Teams, los Firstline los trabajadores pueden comunicarse con seguridad con una experiencia de PTT que les resulte familiar sin necesidad de transportar radios de gran volumen y walkie talkie funciona en cualquier lugar con conectividad WiFi o de Internet de telefonía móvil.

## <a name="getting-started"></a>Introducción

### <a name="deploying-walkie-talkie"></a>Implementación de walkie talkie

Por el momento, walkie talkie no está preinstalado. Para habilitar esta característica para los usuarios de su organización, debe agregar walkie talkie a la Directiva de configuración de la [aplicación](teams-app-setup-policies.md)   asignada a los usuarios desde el [centro de administración de Teams](https://admin.teams.microsoft.com/).

Una vez habilitado, walkie talkie estará disponible en la aplicación de Android en 48 horas.

### <a name="adding-walkie-talkie-to-your-app-list"></a>Agregar walkie talkie a la lista de aplicaciones

En el centro de administración de Microsoft Teams, en directivas de configuración de la **aplicación de Teams**  >  **Setup policies**, debe **permitir el anclaje de usuario** establecido en **activado**. Después, en la sección aplicaciones ancladas, haga clic en **+ agregar aplicaciones**.

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Muestra la sección aplicaciones ancladas y el botón agregar aplicaciones para que se seleccionen.":::

En el panel **agregar aplicaciones ancladas** que aparece a la derecha, use el cuadro de texto de **búsqueda** para buscar walkie talkie. Cuando la haya obtenido como resultado de la búsqueda, haga clic en el botón **Agregar** a la derecha del nombre para agregarlo a la lista.

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Muestra la barra lateral agregar aplicaciones ancladas con walkie introducido en el panel de búsqueda y la aplicación de walkie talkie en los resultados de la búsqueda, con el botón Agregar junto a él.":::

Ahora, la aplicación walkie talkie debería aparecer en la lista de aplicaciones ancladas y estará disponible para su uso una vez que haga clic en el botón **Guardar** .

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Muestra la lista de aplicaciones ancladas con la aplicación walkie talkie agregada y el botón Guardar situado debajo de la lista.":::

### <a name="network-documentation"></a>Documentación de red

Walkie talkie en Teams requiere conexión a Internet y, por lo más, las condiciones de la red son necesarias para una experiencia óptima.

|Métrica | Obligatorio |
|---|---|
|Latencia (RTT) | < 300ms |
|Vibración |< 30ms |
|Pérdida de paquetes |< 1% |

Como se mencionó anteriormente, la calidad de los medios en tiempo real a través de una red IP se ve afectada en gran medida por la calidad de la conectividad de la red, pero especialmente por la cantidad de:

- **Latencia** : es el tiempo que se tarda en obtener un paquete IP del punto a al punto B de la red. Este retraso de propagación de red está esencialmente unido a la distancia física entre los dos puntos y la velocidad de luz, incluida la sobrecarga adicional que realizan los distintos enrutadores entre. La latencia se mide como un tiempo de ida y vuelta (RTT).
- **Pérdida de paquetes** : suele definirse como un porcentaje de paquetes que se pierden en una ventana determinada de tiempo. La pérdida de paquetes afecta directamente a la calidad del audio, desde pequeños paquetes perdidos individuales, casi sin impacto, hasta pérdidas de ráfagas en el fondo que causan un recorte completo del audio.
- **Vibración** : este es el cambio medio en el retraso entre paquetes sucesivos.

El uso de datos esperado de walkie talkie está cerca de 20KB/s al enviar o recibir audio. Cuando está inactivo, el uso de datos esperado de walkie talkie es insignificante.

### <a name="walkie-talkie-devices"></a>Walkie talkie dispositivos

Los trabajadores de los Firstline a menudo necesitan hablar y recibir llamadas de talkie walkie incluso cuando sus teléfonos están bloqueados. Esta experiencia es posible mediante dispositivos especializados con un botón de PTT dedicado.

- Auriculares con micrófono
  - Auriculares con cable ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))
  - Auriculares con micrófono inalámbricos ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))
- Teléfonos resistentes
  - Samsung Galaxy XCover Pro
    - [Más información](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).
    - [Guía de configuración](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).

> [!NOTE]
> Estos dispositivos no tienen la certificación de equipos. Se han validado para trabajar con Teams walkie talkie.

### <a name="license-requirements"></a>Requisitos de licencia

Walkie talkie aplicación está incluida en todas las licencias de pagos de Teams en [Office 365 suscripciones](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing). Para obtener más información sobre la obtención de equipos, consulte [¿Cómo puedo obtener acceso a Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?

> [!NOTE]
> Ciertas características avanzadas pueden requerir licencias adicionales. Por ejemplo, la integración con Samsung Galaxy XCover Pro requiere una licencia de Knox.

## <a name="further-information"></a>Más información

- ITAdmins puede mantener el control sobre quién está usando walkie talkie a través de las directivas de la aplicación.
- Si su trabajador de los Firstline usa datos móviles para comunicarse a través de Teams, walkie talkie usará el mismo método.
- Walkie talkie debería funcionar bien en situaciones de bajo ancho de banda o en situaciones en las que el smartphone está conectado y funcionando. Walkie talkie no funcionará cuando no haya conectividad.

Para obtener más lecturas sobre la experiencia del usuario final, vea:

- [Introducción a teams walkie talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Comuníquese con su equipo con walkie talkie](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
