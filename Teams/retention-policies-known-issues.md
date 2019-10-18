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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a7dd5bac7c82814befab66247b1bfa8cf4943f6
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569967"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Problemas conocidos para directivas de retención en Microsoft Teams

A continuación se muestran algunos problemas conocidos relacionados con las directivas de retención en Teams en los que se realiza el seguimiento e investigación.

- En elegir equipos en la fila ubicaciones de los mensajes del canal de Teams, es posible que vea Office 365 grupos que no son también equipos. Esto se corregirá en el futuro.

- En elegir usuarios en la fila de ubicación de chats de equipos, es posible que vea invitados y usuarios que no son buzones de correo. Las directivas de retención no se deben configurar para los invitados y estamos trabajando para eliminarlas de la lista.

- El Asistente de ciclo de vida de Exchange (ELC) se ejecuta diariamente, pero tiene un SLA de 7 días. Como resultado, es posible que, si tiene una directiva de retención de equipos para eliminar elementos anteriores a 60 días, estos elementos podrían persistir durante un máximo de 67 días. Esta no es una nueva situación: sigue el modelo de Exchange. Por supuesto, en la mayoría de los casos, no hay demora.


| | | |
|---------|---------|---------|
|![Un icono que representa un punto de decisión](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Puntos de decisión         |¿Qué características de seguridad y cumplimiento requiere su organización? ¿Su organización tiene las licencias necesarias para cumplir con los requisitos empresariales de seguridad y cumplimiento?         |
|![Un icono que representa los pasos siguientes](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Pasos siguientes         |Documente las características de seguridad y cumplimiento necesarias.         |
