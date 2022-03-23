---
title: Barreras de información y canales compartidos (vista previa)
description: En este artículo se explica cómo las barreras de información Microsoft Teams admiten canales compartidos
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
ms.openlocfilehash: c65da8b9b04296a7377f29aead811e1efcfb4048
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "63712143"
---
# <a name="information-barriers-and-shared-channels-preview"></a>Barreras de información y canales compartidos (vista previa)

[Los canales](shared-channels.md) compartidos Microsoft Teams crear espacios de colaboración donde puede invitar a personas que no están en el equipo. [Las barreras de información](/microsoft-365/compliance/information-barriers) son directivas que se pueden implementar para restringir e impedir que los usuarios y grupos se comuniquen entre sí dentro y fuera de su organización.

Los canales compartidos están habilitados de forma predeterminada Teams. Puede elegir si los usuarios pueden crear canales compartidos, si pueden compartirlos con personas de fuera de su organización y si pueden participar en canales compartidos externos creando una directiva de canal. Cuando las directivas de barreras de información están configuradas en su organización, se realizan comprobaciones al configurar canales compartidos para comprobar que ninguno de los miembros del canal existentes ni los nuevos usuarios agregados al canal compartido infringen las condiciones de directiva de barreras de información.

Use la tabla siguiente para comprender cómo las directivas de barreras de información pueden afectar a las comunicaciones y provocar comportamientos específicos al configurar canales compartidos:

|**Escenario**|**Comportamiento de barreras de información**|
|:-----------|:--------------------------------|
| **Compartir un canal con un usuario de su organización** | Si el usuario no puede comunicarse con los miembros del canal compartido por una directiva de barreras de información, el usuario no se muestra en la búsqueda de usuario y el canal no se comparte con el equipo. <br><br> Si no se puede agregar al usuario por una directiva de barreras de información, verá el siguiente mensaje: No hemos *encontrado ninguna coincidencia. Hable con el administrador de TI sobre cómo expandir el ámbito de la búsqueda.* |
| **Compartir un canal de su organización con otro equipo de su propiedad** | Si el otro equipo tiene usuarios a los que no se les permite comunicarse con los miembros del canal compartido por una directiva de barreras de información, el canal no se comparte con el equipo. <br><br> Si las comunicaciones no están permitidas por una directiva de barreras de información, verá el siguiente mensaje: El canal *no se puede compartir con este equipo. Elige otro equipo o ponte en contacto con tu administrador para obtener más información.* |
| **Compartir un canal de su organización con otro equipo que no es de su propiedad** | Si el propietario del equipo o los usuarios del otro equipo no pueden comunicarse con los miembros del canal compartido por una directiva de barreras de información, el canal no se puede compartir con el equipo. <br><br> Si las comunicaciones no están permitidas por una directiva de barreras de información, verá el siguiente mensaje: El canal *no se puede compartir con este equipo. Elige otro equipo o ponte en contacto con tu administrador para obtener más información.* |
| **Agregar un nuevo usuario al equipo cuando el equipo haya compartido canales con otros equipos** | Si el nuevo usuario no puede comunicarse con los miembros del equipo del canal compartido por una directiva de barreras de información, el usuario no se puede agregar al equipo. Cuando agrega un usuario a un equipo con seis o más canales compartidos, el usuario se agrega inmediatamente al canal y se admite el uso compartido. El uso compartido para el equipo y los canales compartidos previamente puede detenerse si se encuentra que el nuevo usuario no cumple con una directiva de barreras de información.<br><br> Si no se puede agregar al usuario por una directiva de barreras de información, verá el siguiente mensaje: No se puede agregar usuario debido a una directiva de *barreras de información.* |
| **Compartir un canal con un equipo externo** | Las directivas de barreras de información en inquilinos internos y externos no restringen las comunicaciones entre usuarios de los distintos inquilinos. Los canales compartidos están disponibles para compartirse con usuarios externos. |
