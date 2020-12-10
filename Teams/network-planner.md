---
title: Usar el planificador de red para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: Administrador puede aprender a usar el planificador de redes para determinar los requisitos de red de Microsoft Teams.
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
# <a name="use-the-network-planner-for-microsoft-teams"></a>Usar el planificador de red para Microsoft Teams

Planificador de redes es una herramienta nueva que está disponible en el centro de administración de Teams. Para encontrarla, vaya a **Planning**  >  **Network Planner**. En pocos pasos, el planificador de redes puede ayudarle a determinar y organizar los requisitos de red para conectar los usuarios de Microsoft Teams en toda la organización. Cuando proporciona los detalles de red y el uso de Teams, Network Planner calcula los requisitos de red para implementar equipos y voz en la nube en las ubicaciones físicas de la organización.

![Captura de pantalla de Network Planner](media/network-planner.png)

Planificador de redes le permite:

- Cree representaciones de su organización con sitios y personas recomendadas de Microsoft (trabajadores de oficina, trabajadores remotos y sistema de sala de equipos).

    > [!NOTE]
    > Las personas recomendadas se desarrollaron en función de los datos de los escenarios de mejor uso de Teams y los patrones de uso típicos. Sin embargo, puede crear hasta tres roles personalizados además de los tres roles recomendados.

- Generar informes y calcular los requisitos de ancho de banda para el uso de equipos.

Para usar el planificador de redes, debe ser administrador global, administrador de servicios de equipo o administrador de comunicaciones de Teams.

## <a name="create-a-custom-persona"></a>Crear un rol personalizado

Siga estos pasos para crear un rol personalizado:

1. Vaya a organizador de la red en el centro de administración de Microsoft Teams.

2. En la pestaña **personas** , haga clic en **personalizar rol**. 

3. En el **nuevo panel personal personalizado** , agregue un nombre y una descripción para el nuevo rol.

4. Seleccione los permisos que este rol usará dentro de la organización.

5. Haga clic en **Guardar**.

## <a name="build-your-plan"></a>Crear su plan

Siga estos pasos para empezar a crear su plan de red:

1. Vaya a organizador de la red en el centro de administración de Microsoft Teams.

2. En la pestaña **plan de red** , haga clic en **Agregar un plan de red**.

3. Escriba un nombre y una descripción para el plan de red. El plan de red aparecerá en la lista de planes disponibles.

4. Haga clic en el nombre del plan para seleccionar el nuevo plan.

5. Agregue sitios para crear una representación de la configuración de red de su organización.

    En función de la red de su organización, es posible que desee usar sitios para representar un edificio, una ubicación de oficina u otra cosa. Los sitios pueden estar conectados mediante una WAN para permitir el uso compartido de conexiones de Internet o RTC. Para obtener los mejores resultados, cree sitios con conexiones locales antes de crear sitios que se conecten de forma remota a Internet o a la RTC.

    Para crear un sitio:

    1. Agregue un nombre y una descripción para el sitio.

    2. En **configuración de red**, agregue el número de usuarios de red en ese sitio (obligatorio).

    3. Agregar detalles de red: habilitada para WAN, capacidad de WAN, salida de Internet (**local** o **remota**) y salida de RTC (ninguna, local o remota).

      > [!NOTE]
      > Debe agregar números de capacidad de WAN y de Internet para ver recomendaciones específicas de ancho de banda cuando genera un informe.

    4. Haga clic en **Guardar**.

## <a name="create-a-report"></a>Crear un informe

Después de agregar todos los sitios, puede crear un informe de la siguiente manera.

1. En la pestaña **informes** , haga clic en **iniciar un informe**.

2. Para cada sitio que cree, distribuya el número de usuarios en las personas disponibles. Si usa las personas recomendadas de Microsoft, el número se distribuirá automáticamente (80% de trabajo de Office y 20% de trabajo remoto).

3. Una vez completada la distribución, haga clic en **generar informe**.

    El informe generado mostrará los requisitos de ancho de banda en varias vistas diferentes para que pueda comprender claramente el resultado:
    - Una tabla con cálculos individuales mostrará los requisitos de ancho de banda para cada actividad permitida.
    - Una vista adicional mostrará las necesidades generales de ancho de banda con recomendaciones.

4. Haga clic en **Guardar**. El informe estará disponible en la lista de informes para verlo más tarde.

## <a name="example-scenario"></a>Escenario de ejemplo

Para obtener un ejemplo de cómo usar el planificador de la red para configurar un plan de red y generar un informe siguiendo estos pasos, descargue la [How-To PowerPoint Planner](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (solo en inglés).
