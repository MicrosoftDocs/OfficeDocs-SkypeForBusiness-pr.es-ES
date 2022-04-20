---
title: Barreras de información y canales compartidos (versión preliminar)
description: En este artículo se explica cómo las barreras de la información en Microsoft Teams admiten los canales compartidos
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: information-barriers
ms.openlocfilehash: 6ee178252c00ec4c73dfaa036f17377cef401d30
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922841"
---
# <a name="information-barriers-and-shared-channels-preview"></a>Barreras de información y canales compartidos (versión preliminar)

[Los canales compartidos](shared-channels.md) en Microsoft Teams crear espacios de colaboración donde puede invitar a personas que no forman parte del equipo. [Microsoft Purview Information Barriers son directivas](/microsoft-365/compliance/information-barriers) que se pueden implementar para restringir e impedir que los usuarios y grupos se comuniquen entre sí dentro y fuera de su organización.

Los canales compartidos están habilitados de forma predeterminada en Teams. Puede elegir darle a los usuarios permiso para crear canales compartidos, si pueden compartirlos con personas de fuera de la organización y si pueden participar en canales compartidos externos creando una directiva de canal. Cuando se configuran directivas de barreras de información en su organización, se comprueban al configurar canales compartidos para comprobar que ninguno de los miembros del canal existentes ni los nuevos usuarios agregados al canal compartido infrinjan las condiciones de la directiva de barreras de información.

Use la tabla siguiente para comprender cómo pueden afectar las directivas de barreras de información a las comunicaciones y producir comportamientos específicos al configurar canales compartidos:

|**Escenario**|**Comportamiento de las barreras de la información**|
|:-----------|:--------------------------------|
| **Compartir un canal con un usuario de su organización** | Si el usuario no tiene permiso para comunicarse con los miembros del canal compartido por una directiva de barreras de información, el usuario no se muestra en la búsqueda de usuarios y el canal no se comparte con el equipo. <br><br> Si no se puede agregar al usuario por una directiva de barreras de información, verá el siguiente mensaje: *No hemos encontrado ninguna coincidencia. Hable con su administrador de TI para ampliar el ámbito de la búsqueda.* |
| **Compartir un canal de la organización con otro equipo del que es propietario** | Si el otro equipo tiene usuarios a los que no se les permite comunicarse con los miembros del canal compartido por una directiva de barreras de información, el canal no se comparte con el equipo. <br><br> Si las comunicaciones no están permitidas por una directiva de barreras de información, verá el siguiente mensaje: *El canal no se puede compartir con este equipo. Seleccione otro equipo o póngase en contacto con su administrador para obtener más información.* |
| **Compartir un canal de su organización con otro equipo del que no es propietario** | Si el propietario del equipo o cualquier usuario del otro equipo no tiene permiso para comunicarse con los miembros del canal compartido por una directiva de barreras de información, el canal no se puede compartir con el equipo. <br><br> Si las comunicaciones no están permitidas por una directiva de barreras de información, verá el siguiente mensaje: *El canal no se puede compartir con este equipo. Seleccione otro equipo o póngase en contacto con su administrador para obtener más información.* |
| **Agregar un nuevo usuario al equipo cuando el equipo ha compartido canales con otros equipos** | Si el nuevo usuario no tiene permiso para comunicarse con los miembros del equipo de canal compartido por una directiva de barreras de información, el usuario no se puede agregar al equipo. Cuando agrega un usuario a un equipo con seis o más canales compartidos, el usuario se agrega inmediatamente al canal y se admite el uso compartido. El uso compartido para el equipo y los canales compartidos anteriormente se puede detener si se descubre que el nuevo usuario no es compatible con una directiva de barreras de la información.<br><br> Si no se puede agregar al usuario por una directiva de barreras de información, verá el siguiente mensaje: *No se puede agregar usuario debido a una directiva de barreras de información.* |
| **Compartir un canal con un equipo externo** | Las directivas de barreras de información en los inquilinos internos y externos no restringen las comunicaciones entre los usuarios de los diferentes inquilinos. Los canales compartidos están disponibles para compartir con usuarios externos. |
