---
title: Poner a un usuario o un equipo de Microsoft Teams en retención legal
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Aprenda a poner a un usuario o un equipo de Microsoft Teams en retención legal mediante el Centro de seguridad y cumplimiento, y conozca qué debe poner en retención legal en función de los requisitos de datos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25bd8e235be79ed805a854cbda2b4947f1c1269b
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968041"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Poner a un usuario o un equipo de Microsoft Teams en retención legal
==================================================

Para poner a un usuario o un equipo en retención legal, navegue al [Centro de seguridad y cumplimiento](https://go.microsoft.com/fwlink/?linkid=854628). Cuando crea un nuevo caso, tiene la opción de poner en retención buzones o sitios.

> [!NOTE]
> Si pone a un usuario en retención, el grupo no se pondrá en retención y viceversa.

> [!NOTE]
> Aún no se admite la configuración de la retención legal de mensajes de canal privado. Se admite la retención legal de archivos compartidos en canales privados.

> [!IMPORTANT]
> Cuando un usuario o un grupo se pongan en espera, todas las copias de los mensajes se conservarán. Ejemplo: Clay publicó un mensaje en un canal y luego lo modificó. En una situación de retención, se retienen las dos copias del mensaje. Si no hay retención legal, se retiene solo el último mensaje.

En la imagen de abajo, se está realizando una investigación en torno a Clay. Clay es miembro del equipo Brokers-Dealers (Agentes distribuidores).

Si tuviéramos que poner en retención legal todos los sitios donde Clay pudiera haber hablado sobre planes de intermediación, tendríamos que agregar el sitio de SharePoint del equipo a la lista de sitios en retención legal, además del sitio de OneDrive para la Empresa de Clay.

![Captura de pantalla de un cuadro de diálogo para crear una nueva retención.](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

En resumen, vea la tabla de abajo para conocer lo que debe ponerse en retención legal en función de los requisitos de datos:

|Escenario  |Qué poner en retención legal  |
|---------|---------|
|**Chats privados de Microsoft Teams**     |Buzón del usuario         |
|**Chats de canal de Microsoft Teams**    |Buzón de grupo usado para el equipo         |
|**Contenido de Microsoft Teams (por ejemplo, wiki y archivos)**     |Sitio de SharePoint usado por el equipo         |
|**Contenido privado**     |Sitio de OneDrive para la Empresa del usuario         |
