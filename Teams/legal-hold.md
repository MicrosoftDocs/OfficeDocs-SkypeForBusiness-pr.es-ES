---
title: Poner a un usuario o un equipo de Microsoft Teams en retención legal
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: Aprenda a poner a un usuario o un equipo de Microsoft Teams en retención legal mediante el Centro de seguridad y cumplimiento, y conozca qué debe poner en retención legal en función de los requisitos de datos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63d862cbdf8d31fc00a48849c85994bd878f0bbc
ms.sourcegitcommit: b6aeaa3d98c29bdc120db8ccfcb7ff2c11d246af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "49570839"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Poner a un usuario o un equipo de Microsoft Teams en retención legal
==================================================

Cuando existe una expectativa razonable de litigio, las organizaciones deben conservar la información almacenada electrónicamente (ESI), incluidos los mensajes de chat de los equipos relacionados con el caso. Es posible que las organizaciones necesiten conservar todos los mensajes relacionados con un tema específico o para determinadas personas. En este artículo se tratarán las retenciones legales en Microsoft Teams (para obtener una implementación de retención en el espacio de M365, consulte [Manage eDiscovery cases: colocar ubicaciones de contenido en espera](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)).

> [!NOTE]
> En febrero de 2020, activamos la retención legal o la retención de casos en canales privados (los chats de canal privado se almacenan en buzones de usuario, los chats de canal normal se almacenan en los buzones de grupo de ese equipo). Si ya hay una retención legal para un buzón de usuario, la Directiva de retención se aplicará ahora automáticamente a los mensajes de canal privado almacenados en ese buzón. No se necesita ninguna otra acción para que un administrador pueda activar esta opción. También se admite la retención legal de los archivos compartidos en canales privados.

En Microsoft Teams, todo un equipo o un grupo de usuarios puede estar en espera o en retención legal. Al hacerlo, se asegurará de que todos los mensajes que se intercambiaron en esos equipos (incluidos los canales privados) o los mensajes intercambiados por dichas personas puedan ser detectados por los administradores de cumplimiento de la organización o por los administradores de Teams.

> [!NOTE]
> Si pone a un usuario en retención, el grupo no se pondrá en retención y viceversa.

Para poner un usuario o un equipo en espera legal:

1. Vaya al [centro de cumplimiento de & de seguridad](https://go.microsoft.com/fwlink/?linkid=854628). Al crear un nuevo caso, se le presenta la opción de poner buzones o sitios en espera.

2. Vaya a eDiscovery o a eDiscovery avanzado y cree un caso haciendo clic en "crear un caso". Una vez que se crea el caso, ábralo.

   > [!div class="mx-imgBorder"]
   > ![La pestaña eDiscovery de Microsoft Teams está seleccionada y muestra el botón crear un caso.](media/LegalHold1.png)

3. Ve a la sección "suspensiones" del menú superior y haz clic en "+ crear" para crear una suspensión. Poner a un usuario o equipo en espera guarda todos los mensajes intercambiados por esos usuarios o mensajes. Al crear un nuevo caso, se le presenta la opción de poner buzones o sitios en espera.

   > [!div class="mx-imgBorder"]
   > ![Una imagen que muestra la pestaña suspensiones seleccionada y el botón crear que está debajo.](media/LegalHold2.png)

   1. **Nombre de la espera**. Seleccione un nombre descriptivo y único para la suspensión que va a crear.

      > [!div class="mx-imgBorder"]
      > ![Esta captura de pantalla muestra la pestaña Nombre de la retención, donde puede escribir un nombre y una descripción para la suspensión que está creando.](media/LegalHold3.png)

    2. **Elija ubicación**. Elija si desea que la espera se aplique a un usuario o en un equipo completo (no se puede aplicar suspender en este momento en canales individuales). Nota: Si un usuario está en espera, todos sus mensajes quedarán en espera, incluidos los que hayan enviado en un chat de 1:1, 1: muchos o un chat grupal, o una conversación de canal (incluidos los canales privados).
  
       > [!div class="mx-imgBorder"]
       > ![Aquí tenemos la sección elegir ubicaciones de crear una nueva retención, donde puede tomar decisiones sobre qué opciones de M365, incluido Microsoft Teams, desea que la espera se aplique a.](media/LegalHold4.png)

    3. **Crear consulta**. Puede personalizar la retención Si desea más granularidad en la Directiva de retención. Por ejemplo, puede especificar las palabras clave que desea buscar o puede agregar más condiciones, que deberán cumplirse para que la retención surta efecto.
    
    4. **Revise la configuración** antes de publicarla en la organización.

Una vez que se haya establecido la retención legal, puede descubrir todo el contenido que retiene la Directiva de espera siguiendo el artículo de [eDiscovery de Teams](eDiscovery-investigation.md) .

> [!IMPORTANT]
> Cuando un usuario o un grupo se pongan en espera, todas las copias de los mensajes se conservarán. Por ejemplo, si un usuario ha publicado un mensaje en un canal y después ha modificado el mensaje, en un escenario de espera, se conservarán ambas copias del mensaje. Sin la retención legal, solo se conserva el último mensaje.

Como guía útil, puede usar la tabla siguiente para comprender qué se debe colocar en retención legal según los requisitos de datos:

|Escenario  |Qué poner en retención legal  |
|---------|---------|
|**Contenido de chat de Microsoft Teams de un usuario (en chats de 1:1, 1: muchos o conversaciones grupales, conversaciones de canales privadas, etc.)**     |Buzón del usuario         |
|**Chats de canal de Microsoft Teams (excepto los canales privados)**    |Buzón de grupo usado para el equipo         |
|**Contenido de Microsoft Teams (por ejemplo, wiki, archivos)**     |Sitio de SharePoint usado por el equipo         |
|**Archivos de canal privado de Microsoft Teams**     |Sitio dedicado de SharePoint para privado     |
|**Contenido privado del usuario**     |Sitio de OneDrive para la Empresa del usuario         |
||||

> [!NOTE]
> Para conservar la comunicación en canales privados, debe poner los buzones de usuario (usuarios del canal privado) en espera y cuando use la herramienta eDiscovery para la búsqueda, debe buscar en el buzón de ese usuario. Como se mencionó anteriormente, las conversaciones de canales privadas se almacenan en buzones de usuario, no en el buzón de grupo de un equipo.

Si desea más información sobre este tema para las áreas que no son de Teams en M365, debe revisar [administrar casos de eDiscovery: colocar ubicaciones de contenido en espera](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold).
