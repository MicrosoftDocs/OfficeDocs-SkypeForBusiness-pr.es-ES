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
ms.openlocfilehash: c04f3584aa7207d9d9ee1126df992657f84aa213
ms.sourcegitcommit: 0b584d40e95cbde33cee3691edadb12156d72fb5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980454"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Poner a un usuario o un equipo de Microsoft Teams en retención legal
==================================================

Cuando existe unas expectativas razonables de litigios, las organizaciones deben conservar la información almacenada electrónicamente (ESI), incluidos los mensajes de chat de Teams que sean relevantes para el caso. Es posible que las organizaciones necesiten conservar todos los mensajes relacionados con un tema específico o con determinados individuos. En este artículo se trata la retención legal en Microsoft Teams (para abordar la implementación de la retención en todo el espacio de M365, revise Administrar casos de exhibición de documentos electrónicos: Poner ubicaciones de contenido en [espera).](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)

> [!NOTE]
> En febrero de 2020, habilitamos la retención legal o la retención de casos en canales privados (los chats de canal privado se almacenan en buzones de usuario, los chats de canal normales se almacenan en un buzón de grupo del equipo). Si ya hay una retención legal para un buzón de usuario, la directiva de retención se aplicará automáticamente a los mensajes de canal privado almacenados en ese buzón. No es necesaria ninguna acción adicional para que un administrador active esta opción. También se admite la retención legal de archivos compartidos en canales privados.

En Microsoft Teams, todo un equipo o usuarios seleccionados pueden ponerse en espera o en retención legal. De este modo, se asegura de que todos los mensajes que se intercambiaron en esos equipos (incluidos los canales privados) o los mensajes intercambiados por esos individuos sean detectables por los administradores de cumplimiento de la organización o por los administradores de equipos.

> [!NOTE]
> Si pone a un usuario en retención, el grupo no se pondrá en retención y viceversa.

Para poner a un usuario o un equipo en retención legal:

1. Vaya al Centro [de & seguridad.](https://go.microsoft.com/fwlink/?linkid=854628) Al crear un nuevo caso, se le presenta la opción de poner buzones o sitios en espera.

2. Vaya a Exhibición de documentos electrónicos o eDiscovery avanzado y cree un caso haciendo clic en "Crear un caso". Una vez creado el caso, ábralo.

   > [!div class="mx-imgBorder"]
   > ![La pestaña eDiscovery de Microsoft Teams está seleccionada y muestra el botón Crear un caso.](media/LegalHold1.png)

3. Vaya a la sección "Retenciones" del menú superior y haga clic en "+ Crear" para crear una retención. Al poner un usuario o un equipo en espera se guardarán todos los mensajes intercambiados por esos usuarios o mensajes. Al crear un nuevo caso, se le presenta la opción de poner buzones o sitios en espera.

   > [!div class="mx-imgBorder"]
   > ![Imagen que muestra la pestaña Retenciones seleccionada y el botón Crear debajo.](media/LegalHold2.png)

   1. **Asigne un nombre a su retención.** Seleccione un nombre descriptivo y único para la retención que va a crear.

      > [!div class="mx-imgBorder"]
      > ![Esta captura de pantalla muestra la pestaña Nombrar la retención, donde puede escribir un nombre y una descripción para la retención que está creando.](media/LegalHold3.png)

    2. **Elija la ubicación.** Elija si quiere que la retención se aplique a un usuario o a todo un equipo (por ahora no se puede aplicar la retención en canales individuales). Nota: si un usuario está en espera, todos sus mensajes estarán en espera, incluido lo que enviaron en un chat 1:1, uno a varios o un chat grupal, o una conversación de canal (incluidos los canales privados).
  
       > [!div class="mx-imgBorder"]
       > ![Aquí tenemos la sección Elegir ubicaciones de Crear una nueva retención, donde puede tomar decisiones sobre las opciones de M365, incluido Microsoft Teams, a las que quiere aplicar la retención.](media/LegalHold4.png)

    3. **Crear consulta.** Puede personalizar la retención si quiere tener más granularidad en la directiva de retención. Por ejemplo, puede especificar palabras clave que desea buscar o puede agregar más condiciones que tendrían que satisfacer para que la retención suba a efecto.
    
    4. **Revise la configuración** antes de publicarla en su organización.

Una vez establecida la retención legal, puede descubrir todo el contenido que conserva cualquier directiva de retención después del artículo [de exhibición de documentos electrónicos de Teams.](eDiscovery-investigation.md)

> [!IMPORTANT]
> Cuando un usuario o grupo está en espera, se conservarán todas las copias de los mensajes. Por ejemplo, si un usuario publicó un mensaje en un canal y luego modificó el mensaje, en un escenario de retención, se retendrá ambas copias del mensaje. Sin la retención legal en su lugar, solo se conserva el mensaje más reciente.

## <a name="content-locations-to-place-on-legal-hold-to-preserve-teams-content"></a>Ubicaciones de contenido que se colocarán en retención legal para conservar el contenido de Teams

Como guía útil, puede usar la tabla siguiente para comprender qué ubicación de contenido (como un buzón o sitio) colocar en retención legal para conservar los distintos tipos de contenido de Teams.

|Escenario  |Ubicación del contenido  |
|---------|---------|
|Chats de Teams para un usuario (por ejemplo, chats uno a uno, chats grupales 1:N y conversaciones de canal privado)     |Buzón de usuario.         |
|Chats de los canales de Teams (excepto los canales privados)    |Buzón de grupo que se ha usado para el equipo.         |
|Contenido de archivos de Teams (por ejemplo, contenido de wiki y archivos)     |Sitio de SharePoint que ha usado el equipo.         |
|Archivos de canal privado de Teams     |Sitio de SharePoint dedicado para canales privados.     |
|Contenido privado del usuario     |La cuenta de usuario de OneDrive para la Empresa.         |
|Contenido de la tarjeta en chats|Buzón de usuario para chats uno a uno, chats grupales 1:N y conversaciones de canal privado o buzón de grupo para el contenido de la tarjeta en los mensajes del canal. Para obtener más información, vea la sección "Conservar el contenido de la tarjeta" [en Crear una conservación de eDiscovery.](https://docs.microsoft.com/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content)
||||

> [!NOTE]
> Para conservar la comunicación en canales privados, debe poner los buzones de usuario (usuarios de canal privado) en espera y, al usar la herramienta eDiscovery para realizar búsquedas, debe buscar en el buzón de ese usuario. Como se mencionó anteriormente, los chats de canal privado se almacenan en buzones de usuario, no en el buzón de grupo de un equipo.

Si desea obtener más información sobre este tema para áreas que no son de Teams en Microsoft 365, debe revisar Administrar casos de exhibición de documentos electrónicos: Poner ubicaciones de contenido [en espera.](https://docs.microsoft.com/microsoft-365/compliance/ediscovery-cases#step-4-place-content-locations-on-hold)
