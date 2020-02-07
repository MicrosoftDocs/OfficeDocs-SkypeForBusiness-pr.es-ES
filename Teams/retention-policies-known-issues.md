---
title: Problemas conocidos para directivas de retención en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Lista actual de problemas conocidos para las directivas de retención de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: d070180505081971eca6c4075bd5bc4563bcd184
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838210"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Problemas conocidos para directivas de retención en Microsoft Teams

> [!NOTE]
> Aún no se admite la configuración de retención de mensajes de canal privado. La retención de archivos compartidos en canales privados es compatible.

A continuación se muestran algunos problemas conocidos relacionados con las directivas de retención en Teams en los que se realiza el seguimiento e investigación.

- En elegir equipos en la fila ubicaciones de los mensajes del canal de Teams, es posible que vea Office 365 grupos que no son también equipos. Esto se corregirá en el futuro.

- En elegir usuarios en la fila de ubicación de chats de equipos, es posible que vea invitados y usuarios que no son buzones de correo. Las directivas de retención no se deben configurar para los invitados y estamos trabajando para eliminarlas de la lista.

- El Asistente de ciclo de vida de Exchange (ELC) se ejecuta diariamente, pero tiene un SLA de 7 días. Como resultado, es posible que, si tiene una directiva de retención de equipos para eliminar elementos anteriores a 60 días, estos elementos podrían persistir durante un máximo de 67 días. Esta no es una nueva situación: sigue el modelo de Exchange. Por supuesto, en la mayoría de los casos, no hay demora.


| | | |
|---------|---------|---------|
|![Un icono que representa un punto de decisión](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Puntos de decisión         |¿Qué características de seguridad y cumplimiento requiere su organización? ¿Su organización tiene las licencias necesarias para cumplir con los requisitos empresariales de seguridad y cumplimiento?         |
|![Un icono que representa los pasos siguientes](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Pasos siguientes         |Documente las características de seguridad y cumplimiento necesarias.         |
