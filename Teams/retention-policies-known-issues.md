---
title: Problemas conocidos para directivas de retención en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
description: Lista actual de problemas conocidos de las directivas de retención de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dca7decd2c3c051c0d56a14e2a2d1485b777f92e
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517066"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Problemas conocidos para directivas de retención en Microsoft Teams

Los siguientes son problemas conocidos que para las directivas de retención en los equipos que se va a realizar un seguimiento e investigarse.

- Bajo Elija los equipos en la fila de ubicación de los mensajes de canal de los equipos, es posible que vea Office 365 grupos que están no también los equipos. Esto se solucionará en el futuro.

- En Elegir usuarios en la fila de la ubicación de los equipos de Chat, es posible que vea invitados y los usuarios de buzones que no sean. Las directivas de retención no están pensadas para establecerse para invitados, y estamos trabajando para quitar estos elementos de la lista.

- Asistente de ciclo de vida de Exchange (ELC) se ejecuta a diario, pero tiene un SLA de 7 días. Como resultado, es posible que, si tiene una directiva de retención de los equipos para eliminar los elementos de más de 60 días, pueden conservar estos elementos de 67 días. Esto no es una situación nueva - sigue el modelo de Exchange. Por supuesto, en la mayoría de los casos, no hay ningún retraso.


| | | |
|---------|---------|---------|
|![Icono de Punto de decisión.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Puntos de decisión         |¿Qué características de seguridad y cumplimiento requiere su organización? ¿Su organización tiene las licencias necesarias para cumplir con los requisitos empresariales de seguridad y cumplimiento?         |
|![Icono de Siguientes pasos.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Pasos siguientes         |Documentar las características de seguridad y cumplimiento de normas necesarias.         |
