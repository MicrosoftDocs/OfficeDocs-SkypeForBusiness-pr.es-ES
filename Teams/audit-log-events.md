---
title: Buscar eventos en el registro de auditoría en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: Obtenga información sobre cómo recuperar datos de Microsoft Teams del registro de auditoría.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b1235dcd1a33800185eb005f5e309204790c5b1
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778896"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Buscar eventos en el registro de auditoría en Microsoft Teams

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

El registro de auditoría puede ayudarle a investigar actividades específicas en los servicios de Office 365. Estas son algunas de las actividades que se auditan en Microsoft Teams:

- Creación de equipos

- Eliminación de equipos

- Agregación de canales

- Cambios en la configuración

> [!NOTE]
> Los eventos de auditoría de canales privados también se registran como si se trataran de equipos y canales estándar.

Para ver la lista completa de actividades que se auditan en Microsoft 365, lea [Buscar el registro de auditoría en el centro de cumplimiento de microsoft 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="turn-on-auditing-in-teams"></a>Activar la auditoría en Microsoft Teams

Para poder consultar los datos de auditoría, primero debe activar la auditoría en el [centro de cumplimiento de & de seguridad](https://protection.office.com). Para obtener ayuda para activar la auditoría, lea [activar o desactivar la búsqueda de registros de auditoría](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).

> [!IMPORTANT]
> Los datos de auditoría solo están disponibles desde el momento en que se habilitó la auditoría.

## <a name="retrieve-teams-data-from-the-audit-log"></a>Recuperar datos de Microsoft Teams del registro de auditoría

1. Para recuperar los registros de auditoría, vaya al [Centro de seguridad y cumplimiento](https://go.microsoft.com/fwlink/?linkid=855775). En **Buscar**, seleccione **búsqueda de registros de auditoría**.
1. Use **Buscar** para filtrar por las actividades, las fechas y los usuarios que desee auditar.
1. Exporte los resultados a Excel para continuar el análisis.

> [!IMPORTANT]
> Los datos de auditoría solo están visibles en el registro de auditoría si está activada la auditoría.

## <a name="external-user-scenario"></a>Escenario de usuario externo

Un escenario que quizás desee mantener a la vista desde una perspectiva empresarial es la adición de usuarios externos a su entorno de equipos. Si los usuarios externos están habilitados, la supervisión de su presencia es una buena idea.

![Captura de pantalla de una lista de eventos desencadenada por eliminaciones masivas](media/TeamsExternalUserAddPolicy.png)

La captura de pantalla de esta directiva para supervisar adiciones de usuarios externos le permite asignar un nombre a la Directiva, establecer la gravedad según las necesidades de su empresa, establecerla como (en este caso) una sola actividad y, a continuación, establecer los parámetros que solo supervisarán específicamente la adición de usuarios no internos y limitarán esta actividad a Microsoft Teams.

Entonces, los resultados de esta directiva podrán verse en el registro de actividades:

![Captura de pantalla de una lista de eventos desencadenada por eliminaciones masivas](media/TeamsExternalUserList.png)

Aquí puede revisar las coincidencias con la Directiva que ha establecido, realizar los ajustes necesarios, o exportar los resultados para usarlos en otro lugar.

## <a name="mass-delete-scenario"></a>Escenario de eliminación masiva

Como se mencionó anteriormente, puede supervisar los escenarios de eliminación. Es posible crear una directiva que supervisará la eliminación masiva de sitios de Teams:

![Captura de pantalla de la página creación de directiva que muestra la configuración de una directiva para la detección masiva de la eliminación de equipos](media/TeamsMassDeletePolicy.png)

Como se muestra en la captura de pantalla, puede establecer muchos parámetros diferentes para que esta directiva supervise las eliminaciones de Teams, incluyendo la gravedad, una acción única o repetida, y los parámetros que limitan esta posibilidad a los equipos y la eliminación de sitios. Esto puede hacerse independientemente de una plantilla o puede tener una plantilla creada para basar esta directiva en función de las necesidades de la organización.

Una vez que haya establecido una directiva que funcione para su empresa, podrá revisar los resultados en el registro de actividades a medida que se activen los eventos:

![Captura de pantalla de una lista de eventos desencadenada por eliminaciones masivas](media/TeamsMassDeleteList.png)

Puede filtrar hasta la Directiva que haya establecido para ver los resultados de esa Directiva. Si los resultados que está recibiendo en el registro de actividades no son satisfactorios (quizá esté viendo un gran número de resultados o nada), esto puede ayudarle a ajustar la consulta para hacerla más relevante para lo que necesita.

## <a name="video-techtip-using-audit-log-search-in-teams"></a>Vídeo: TechTip: Usar la búsqueda en el registro de auditoría en Microsoft Teams

Observe cómo Ansuman Acharya, un director de proyectos de Microsoft Teams, realiza una búsqueda en el registro de auditoría para Microsoft Teams en el Centro de seguridad y cumplimiento de Office 365.

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
