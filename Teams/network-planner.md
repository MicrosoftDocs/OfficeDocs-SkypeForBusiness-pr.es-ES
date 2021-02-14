---
title: Usar el organizador de red para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: El administrador puede obtener información sobre cómo usar el planificador de red para determinar los requisitos de red para Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9351c37c96e4bc11f0e5f93041f7e024158d7564
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611804"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Usar el organizador de red para Microsoft Teams

Network Planner es una nueva herramienta que está disponible en el Centro de administración de Teams. Puede encontrarla yendo al Planificador **de red de**  >  **planificación.** En solo unos pasos, el organizador de red puede ayudarle a determinar y organizar los requisitos de red para conectar los usuarios de Microsoft Teams en toda su organización. Cuando proporciona los detalles de la red y el uso de Teams, el planificador de red calcula los requisitos de red para implementar Teams y la voz en la nube en las ubicaciones físicas de su organización.

![Captura de pantalla del organizador de red](media/network-planner.png)

El planificador de red le permite:

- Cree representaciones de su organización con sitios y personas recomendadas por Microsoft (trabajadores de oficina, trabajadores remotos y sistema de sala de Teams).

    > [!NOTE]
    > Los roles recomendados se desarrollaron basándose en los datos de los escenarios de mejor uso de Teams y en los patrones de uso típicos. Sin embargo, puede crear hasta tres personas personalizadas además de las tres personas recomendadas.

- Genere informes y calcule requisitos de ancho de banda para el uso de Teams.

Para usar el planificador de red, debe ser administrador global, administrador de servicios de Teams o administrador de comunicaciones de Teams.

## <a name="create-a-custom-persona"></a>Crear un rol personalizado

Siga estos pasos para crear un rol personalizado:

1. Vaya al Organizador de red en el Centro de administración de Microsoft Teams.

2. En la **pestaña Personas,** haga clic **en + Rol personalizado.** 

3. En el **panel Nuevo rol personalizado,** agregue un nombre y una descripción para el nuevo rol.

4. Seleccione los permisos que usará esta persona dentro de la organización.

5. Haga clic en **Guardar**.

## <a name="build-your-plan"></a>Cree su plan

Siga estos pasos para comenzar a crear su plan de red:

1. Vaya al Organizador de red en el Centro de administración de Microsoft Teams.

2. En la pestaña **Plan de** red, haga clic en Agregar un plan **de red.**

3. Escriba un nombre y una descripción para su plan de red. El plan de red aparecerá en la lista de planes disponibles.

4. Haga clic en el nombre del plan para seleccionar el nuevo plan.

5. Agregue sitios para crear una representación de la configuración de red de su organización.

    Según la red de su organización, es posible que desee usar sitios para representar un edificio, una ubicación de oficina o cualquier otra cosa. Es posible que los sitios estén conectados mediante una WAN para permitir el uso compartido de conexiones de Internet o RTC. Para obtener los mejores resultados, cree sitios con conexiones locales antes de crear sitios que se conecten de forma remota a Internet o RTC.

    Para crear un sitio:

    1. Agregue un nombre y una descripción para el sitio.

    2. En **Configuración de** red, agregue el número de usuarios de red en ese sitio (obligatorio).

    3. Agregue detalles de red: habilitada para WAN, capacidad de WAN, salida de Internet **(local** o **remota)** y salida RTC (ninguna, local o remota).

      > [!NOTE]
      > Debe agregar wan y números de capacidad de Internet para ver recomendaciones específicas de ancho de banda al generar un informe.

    4. Haga clic en **Guardar**.

## <a name="create-a-report"></a>Crear un informe

Después de agregar todos los sitios, puede crear un informe del modo siguiente.

1. En la **pestaña Informes,** haga clic **en Iniciar un informe.**

2. Para cada sitio que cree, distribuya el número de usuarios entre las personas disponibles. Si usa los roles recomendados por Microsoft, el número se distribuirá automáticamente (el 80 % de trabajador de oficina y el 20 % de trabajador remoto).

3. Después de completar la distribución, haga clic **en Generar informe.**

    El informe generado mostrará los requisitos de ancho de banda en varias vistas diferentes para que pueda comprender claramente el resultado:
    - Una tabla con cálculos individuales mostrará los requisitos de ancho de banda para cada actividad permitida.
    - Una vista adicional mostrará las necesidades generales de ancho de banda con recomendaciones.

4. Haga clic en **Guardar**. El informe estará disponible en la lista de informes para verlo más adelante.

## <a name="example-scenario"></a>Escenario de ejemplo

Para obtener un ejemplo de cómo usar el planificador de red para configurar un plan de red y generar un informe con estos pasos, descargue el planificador de red How-To conjunto de diapositivas de [PowerPoint](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (solo en inglés).
