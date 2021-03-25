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
ms.openlocfilehash: 9f2f269d75a7bf8bd97165329d2ae6b006b940f4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112306"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Poner a un usuario o un equipo de Microsoft Teams en retención legal
==================================================

Cuando existe una expectativa razonable de litigio, se requiere que las organizaciones conserven la información almacenada electrónicamente (ESI), incluidos los mensajes de chat de Teams que son relevantes para el caso. Es posible que las organizaciones necesiten conservar todos los mensajes relacionados con un tema específico o con determinados individuos. En este artículo se tratará la retención legal en Microsoft Teams (Para abordar la implementación de retención en todo el espacio M365, revise Administrar casos de exhibición de documentos [electrónicos:](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)Poner ubicaciones de contenido en espera ).).

> [!NOTE]
> En febrero de 2020, habilitamos la retención legal o la retención de mayúsculas y minúsculas en canales privados (los chats de canal privado se almacenan en buzones de usuario, los chats de canal normales se almacenan en el buzón de grupo de un equipo). Si ya hay una retención legal en su lugar para un buzón de usuario, la directiva de retención se aplicará automáticamente a los mensajes de canal privado almacenados en ese buzón. No es necesaria ninguna acción adicional para que un administrador active esta opción. También se admite la retención legal de archivos compartidos en canales privados.

En Microsoft Teams, todo un equipo o usuarios seleccionados se pueden poner en espera o en espera legal. Al hacerlo, se garantizará que todos los mensajes que se intercambiaron en esos equipos (incluidos los canales privados) o los mensajes intercambiados por esas personas sean reconocibles por los administradores de cumplimiento de la organización o los administradores de Teams.

> [!NOTE]
> Si pone a un usuario en retención, el grupo no se pondrá en retención y viceversa.

Para poner a un usuario o un equipo en retención legal:

1. Vaya al [Centro de cumplimiento & seguridad.](https://go.microsoft.com/fwlink/?linkid=854628) Al crear un nuevo caso, se le presenta la opción de poner buzones o sitios en espera.

2. Vaya a eDiscovery o eDiscovery avanzado y cree un caso haciendo clic en "Crear un caso". Una vez creado el caso, ábralo.

   > [!div class="mx-imgBorder"]
   > ![Se selecciona la pestaña Exhibición de documentos electrónicos de Microsoft Teams, que muestra el botón Crear un caso.](media/LegalHold1.png)

3. Vaya a la sección "Retenciones" del menú superior y haga clic en "+ Crear" para crear una retención. Poner un usuario o un equipo en espera guarda todos los mensajes intercambiados por esos usuarios o mensajes. Al crear un nuevo caso, se le presenta la opción de poner buzones o sitios en espera.

   > [!div class="mx-imgBorder"]
   > ![Imagen que muestra la pestaña Retenciones seleccionada y el botón Crear debajo.](media/LegalHold2.png)

   1. **Asigne un nombre a la retención**. Seleccione un nombre descriptivo y único para la retención que va a crear.

      > [!div class="mx-imgBorder"]
      > ![Esta captura de pantalla muestra la pestaña Nombre de la retención, donde puede escribir un nombre y una descripción para la retención que está creando.](media/LegalHold3.png)

    2. **Elija la ubicación**. Elija si desea que la retención se aplique a un usuario o a todo un equipo (la retención no se puede aplicar en canales individuales por ahora). Nota: si un usuario está en espera, todos sus mensajes estarían en espera, incluidos los que enviaron en un chat de 1:1, un chat grupal o varios, o una conversación de canal (incluidos los canales privados).
  
       > [!div class="mx-imgBorder"]
       > ![Aquí tenemos la sección Elegir ubicaciones de Crear una nueva retención, donde puede tomar decisiones sobre qué opciones de M365, incluido Microsoft Teams, desea que se aplique la retención.](media/LegalHold4.png)

    3. **Crear consulta**. Puede personalizar la retención si desea obtener más granularidad en la directiva de retención. Por ejemplo, puede especificar palabras clave para buscar, o puede agregar más condiciones, que tendrían que estar satisfechos para que la retención suba a efecto.
    
    4. **Revise la configuración antes** de publicarla en su organización.

Una vez establecida la retención legal, puede descubrir todo el contenido retenido por cualquier directiva de retención siguiendo el artículo Exhibición [de documentos electrónicos de Teams.](eDiscovery-investigation.md)

> [!IMPORTANT]
> Cuando un usuario o grupo se coloca en espera, se conservarán todas las copias de mensajes. Por ejemplo, si un usuario publicó un mensaje en un canal y, después, modificó el mensaje, en un escenario de retención, se conservan ambas copias del mensaje. Sin la retención legal en su lugar, solo se conserva el mensaje más reciente.

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>Ubicaciones de contenido que se colocarán en retención legal para conservar el contenido de Teams

Como guía útil, puede usar la tabla siguiente para comprender qué ubicación de contenido (como un buzón o un sitio) debe colocar en retención legal para conservar diferentes tipos de contenido de Teams.

|Escenario  |Ubicación de contenido  |
|---------|---------|
|Chats de Teams para un usuario (por ejemplo, chats de 1:1, chats grupales 1:N y conversaciones de canal privado)     |Buzón de usuario.         |
|Chats de canal de Teams (excepto canales privados)    |Buzón de grupo usado para el equipo.         |
|Contenido de archivos de Teams (por ejemplo, contenido wiki y archivos)     |Sitio de SharePoint usado por el equipo.         |
|Archivos de canal privado de Teams     |Sitio de SharePoint dedicado para canales privados.     |
|Contenido privado del usuario     |Cuenta de OneDrive para la Empresa del usuario.         |
|Contenido de tarjeta en chats|Buzón de usuario para chats de 1:1, chats grupales 1:N y conversaciones de canal privado o buzón de grupo para contenido de tarjeta en mensajes de canal. Para obtener más información, vea la sección "Conservar contenido de tarjeta" en [Crear una retención de exhibición de documentos electrónicos.](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)
||||

> [!NOTE]
> Para conservar la comunicación en canales privados, debe poner los buzones de usuario (usuarios del canal privado) en espera y, al usar la herramienta eDiscovery para buscar, debe buscar en el buzón de ese usuario. Como se indicó anteriormente, los chats de canal privado se almacenan en buzones de usuario, no en el buzón de grupo de un equipo.

Si desea leer más sobre este tema para áreas que no son de Teams en Microsoft 365, debe revisar Administrar casos de exhibición de documentos electrónicos: Poner las ubicaciones de contenido [en espera.](/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)