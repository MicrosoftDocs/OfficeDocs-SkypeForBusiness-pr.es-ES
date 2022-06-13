---
title: Usar el planificador de red para Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: El administrador puede obtener información sobre cómo usar Network Planner para determinar los requisitos de red para Microsoft Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: fba570bdd7a83c26d68d10e65f631a0d028d7408
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045559"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Usar el planificador de red para Microsoft Teams

Network Planner es una nueva herramienta que está disponible en el centro de administración de Teams. Para encontrarla, ve a Planificador de la **red** **de planificación** > . En solo unos pasos, Network Planner puede ayudarle a determinar y organizar los requisitos de red para conectar Microsoft Teams usuarios de toda la organización. Cuando proporciona el uso de Teams y los detalles de la red, el Planeamiento de red calcula los requisitos de red para implementar Teams y voz en la nube en las ubicaciones físicas de su organización.

![Captura de pantalla del planificador de red.](media/network-planner.png)

El planificador de red le permite:

- Cree representaciones de su organización mediante sitios y roles recomendados por Microsoft (trabajadores de oficina, trabajadores remotos y Teams sistema de salas).

    > [!NOTE]
    > Las personas recomendadas se desarrollaron basándose en datos de Teams mejores escenarios de uso y patrones de uso típicos. Sin embargo, puede crear hasta tres personas personalizadas además de las tres personas recomendadas.

- Genere informes y calcule los requisitos de ancho de banda para el uso de Teams.

Para usar el planificador de red, debe ser administrador global, administrador de Teams o administrador de comunicaciones de Teams.

## <a name="create-a-custom-persona"></a>Crear un rol personalizado

Siga estos pasos para crear un rol personalizado:

1. Vaya al Planificador de red en el centro de administración de Microsoft Teams.

2. En la pestaña **Personas** , haga clic en **+ Rol personalizado**. 

3. En el panel **Nuevo rol personalizado** , agregue un nombre y una descripción para el nuevo rol.

4. Seleccione los permisos que usará esta persona dentro de la organización.

5. Haga clic en **Guardar**.

## <a name="build-your-plan"></a>Crear su plan

Siga estos pasos para empezar a crear su plan de red:

1. Vaya al Planificador de red en el centro de administración de Microsoft Teams.

2. En la pestaña **Plan de** red, haga clic en **Agregar un plan de red**.

3. Escriba un nombre y una descripción para su plan de red. El plan de red aparecerá en la lista de planes disponibles.

4. Haga clic en el nombre del plan para seleccionar el nuevo plan.

5. Agregue sitios para crear una representación de la configuración de red de su organización.

    Según la red de su organización, es posible que desee usar sitios para representar un edificio, una ubicación de oficina u otra cosa. Los sitios pueden estar conectados mediante una WAN para permitir el uso compartido de conexiones a Internet o RTC. Para obtener los mejores resultados, cree sitios con conexiones locales antes de crear sitios que se conecten de forma remota a Internet o RTC.

    Para crear un sitio:

    1. Agregue un nombre y una descripción para el sitio.

    2. En **Configuración de red**, agregue el número de usuarios de red en ese sitio (necesario).

    3. Agregue detalles de red: capacidad WAN habilitada, capacidad WAN, salida de Internet (**local** o **remota**) y salida RTC (ninguna, local o remota).

      > [!NOTE]
      > Debe agregar números de capacidad WAN e Internet para ver recomendaciones específicas de ancho de banda al generar un informe.

    4. Haga clic en **Guardar**.

## <a name="create-a-report"></a>Crear un informe

Después de agregar todos los sitios, puede crear un informe, como se indica a continuación.

1. En la pestaña **Informes** , haga clic en **Iniciar un informe**.

2. Para cada sitio que cree, distribuya el número de usuarios entre las personas disponibles. Si usa los roles recomendados por Microsoft, el número se distribuirá automáticamente (80 % trabajador de oficina y 20 % trabajador remoto).

3. Después de completar la distribución, haga clic en **Generar informe**.

    El informe generado mostrará los requisitos de ancho de banda en varias vistas diferentes para que pueda comprender claramente el resultado:
    - Una tabla con cálculos individuales mostrará los requisitos de ancho de banda para cada actividad permitida.
    - Una vista adicional mostrará las necesidades generales de ancho de banda con recomendaciones.

4. Haga clic en **Guardar**. El informe estará disponible en la lista de informes para verlo más adelante.

## <a name="example-scenario"></a>Ejemplo ficticio

Para obtener un ejemplo de cómo usar el planificador de red para configurar un plan de red y generar un informe con estos pasos, descargue el [organizador de red How-To PowerPoint conjunto](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (solo en inglés).
