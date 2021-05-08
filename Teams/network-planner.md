---
title: Use el Planificador de red para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: El administrador puede aprender a usar Network Planner para determinar los requisitos de red para Microsoft Teams.
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
ms.openlocfilehash: 1f05be30158cf934459f26965d7cef2dafbc708f
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240483"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Use el Planificador de red para Microsoft Teams

Network Planner es una nueva herramienta que está disponible en el centro Teams administración. Puede encontrarla yendo a Planificador **de** red  >  **de planificación.** En tan solo unos pocos pasos, Network Planner puede ayudarle a determinar y organizar los requisitos de red para conectar a Microsoft Teams usuarios de toda la organización. Cuando proporciona el uso de Teams y los detalles de la red, el Planeamiento de red calcula los requisitos de red para implementar Teams y voz en la nube en las ubicaciones físicas de su organización.

![Captura de pantalla de Planificador de red](media/network-planner.png)

El planificador de red le permite:

- Cree representaciones de su organización con sitios y personas recomendadas por Microsoft (trabajadores de oficina, trabajadores remotos y Teams de sala).

    > [!NOTE]
    > Las personas recomendadas se desarrollaron basándose en datos Teams escenarios de mejor uso y patrones de uso típicos. Sin embargo, puede crear hasta tres personas personalizadas además de las tres personas recomendadas.

- Genere informes y calcule los requisitos de ancho de banda Teams uso.

Para usar El planificador de red, debe ser administrador global, Teams administrador o Teams de comunicaciones.

## <a name="create-a-custom-persona"></a>Crear una persona personalizada

Siga estos pasos para crear una persona personalizada:

1. Vaya al Planificador de red en el Microsoft Teams de administración.

2. En la **pestaña Personas,** haga clic **en + Persona personalizada.** 

3. En el **panel Nuevo carácter personalizado,** agregue un nombre y una descripción para la nueva persona.

4. Seleccione los permisos que usará esta persona dentro de la organización.

5. Haga clic en **Guardar**.

## <a name="build-your-plan"></a>Crear un plan

Siga estos pasos para empezar a crear su plan de red:

1. Vaya al Planificador de red en el Microsoft Teams de administración.

2. En la pestaña **Plan de** red, haga clic en Agregar un plan **de red.**

3. Escriba un nombre y una descripción para el plan de red. El plan de red aparecerá en la lista de planes disponibles.

4. Haga clic en el nombre del plan para seleccionar el nuevo plan.

5. Agregue sitios para crear una representación de la configuración de red de su organización.

    Según la red de su organización, es posible que desee usar sitios para representar un edificio, una ubicación de oficina u otra cosa. Es posible que los sitios estén conectados mediante una WAN para permitir el uso compartido de conexiones de Internet y/o RTC. Para obtener los mejores resultados, cree sitios con conexiones locales antes de crear sitios que se conecten de forma remota a Internet o RTC.

    Para crear un sitio:

    1. Agregue un nombre y una descripción para el sitio.

    2. En **Configuración de red,** agregue el número de usuarios de red en ese sitio (obligatorio).

    3. Agregar detalles de red: capacidad WAN habilitada, salida de Internet **(local** o **remota)** y salida RTC (ninguna, local o remota).

      > [!NOTE]
      > Debe agregar números de wan e capacidad de Internet para ver recomendaciones específicas de ancho de banda al generar un informe.

    4. Haga clic en **Guardar**.

## <a name="create-a-report"></a>Crear un informe

Después de agregar todos los sitios, puede crear un informe, como se muestra a continuación.

1. En la **pestaña Informes,** haga clic **en Iniciar un informe.**

2. Para cada sitio que cree, distribuya el número de usuarios entre las personas disponibles. Si usa las personas recomendadas por Microsoft, el número se distribuirá automáticamente (80% trabajador de oficina y 20 % trabajador remoto).

3. Después de completar la distribución, haga clic **en Generar informe.**

    El informe generado mostrará los requisitos de ancho de banda en varias vistas diferentes para que pueda comprender claramente el resultado:
    - Una tabla con cálculos individuales mostrará los requisitos de ancho de banda para cada actividad permitida.
    - Una vista adicional mostrará las necesidades generales de ancho de banda con recomendaciones.

4. Haga clic en **Guardar**. El informe estará disponible en la lista de informes para su visualización posterior.

## <a name="example-scenario"></a>Ejemplo ficticio

Para ver un ejemplo de cómo usar el planificador de red para configurar un plan de red y generar un informe con estos pasos, descargue el planificador de [red How-To PowerPoint presentación](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (solo en inglés).
