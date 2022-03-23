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
description: Aprenda a poner a un Microsoft Teams o equipo en retención legal con el Centro de cumplimiento de Microsoft 365 y obtenga información sobre qué necesita una retención legal en función de los requisitos de datos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06b3ea009e538b8796a9e55b277dc4ec12f5a3a4
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711564"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Poner a un usuario o un equipo de Microsoft Teams en retención legal

Cuando existe una expectativa razonable de litigio, se requiere que las organizaciones conserven la información almacenada electrónicamente (ESI), incluidos Teams mensajes de chat relevantes para el caso. Es posible que las organizaciones necesiten conservar todos los mensajes relacionados con una investigación específica o con una persona específica. En este artículo se explica cómo usar una retención legal para conservar el contenido en Microsoft Teams. Para conservar contenido en otros servicios de Microsoft 365, vea [Crear una retención de exhibición de documentos electrónicos](/microsoft-365/compliance/create-ediscovery-holds).

> [!NOTE]
> En febrero de 2020, se ha activado la retención legal para los canales privados. Los chats de canal privado se almacenan en buzones de usuario, mientras que los chats de canal estándar se almacenan en el buzón asociado con el equipo principal. Si ya hay una retención legal en su lugar para un buzón de usuario, la directiva de retención se aplicará automáticamente a los mensajes de canal privado almacenados en ese buzón. No es necesaria ninguna acción adicional para que un administrador active esta opción. También se admite la retención legal de archivos compartidos en canales privados.

En Microsoft Teams, todo un equipo o usuarios seleccionados se pueden poner en retención legal. Al hacerlo, se garantizará que todos los mensajes que se intercambiaron en esos equipos (incluidos los canales privados y compartidos) o los mensajes intercambiados por esas personas sean reconocibles por los administradores de cumplimiento de la organización o Teams administradores.

> [!NOTE]
> Si pone a un usuario en retención, el grupo no se pondrá en retención y viceversa.
> Las notificaciones enviadas en fuentes de actividad no se pueden colocar en espera.

Para poner a un usuario o un equipo en retención legal en un caso de eDiscovery principal:

1. Vaya a la [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com). Al crear un nuevo caso, se le presenta la opción de poner buzones o sitios en espera.

2. Vaya a **eDiscoveryCore** >  y cree un caso haciendo clic **en Crear un caso**. Después de crear el caso, ábralo.
  
   ![Microsoft Teams pestaña eDiscovery está seleccionada, que muestra el botón Crear un caso.](media/LegalHold1.png)

   > [!NOTE]
   > También puede colocar a un usuario en una retención asociada con un Advanced eDiscovery mayúsculas y minúsculas. Para obtener más información, vea [Administrar retenciones en Advanced eDiscovery](/microsoft-365/compliance/managing-holds).

3. Vaya a la **pestaña Retenciones** del menú superior y haga clic **en Crear** para crear una retención. La colocación de un usuario o un equipo en espera conserva todos los mensajes intercambiados por esos usuarios. Al crear un nuevo caso, se le presenta la opción de poner buzones o sitios en espera.

   ![Imagen que muestra la pestaña Retenciones seleccionada y el botón Crear debajo.](media/LegalHold2.png)

   1. **Asigne un nombre a la retención**. Seleccione un nombre descriptivo y único para la retención que va a crear.
  
       ![Esta captura de pantalla muestra la pestaña Nombre de la retención, donde puede escribir un nombre y una descripción para la retención que está creando.](media/LegalHold3.png)

   2. **Elija la ubicación**. Elija si desea que la retención se aplique a un usuario o a todo un equipo (una retención no se puede aplicar en canales individuales por ahora). Si un usuario está en espera, se conservan todos sus mensajes, incluidos los mensajes en chats de 1:1, chats grupales y canales privados. Los mensajes en canales estándar y compartidos se conservan cuando el equipo principal está en espera.

      ![Elija las ubicaciones de datos que desea poner en espera.](media/LegalHold4.png)

   3. **Crear consulta**. Puede personalizar la retención si desea obtener más granularidad en la directiva de retención. Por ejemplo, puede especificar palabras clave para buscar, o puede agregar más condiciones, que tendrían que estar satisfechos para que la retención suba a efecto.

   4. **Revise la configuración antes** de crear la retención.

Después de crear la retención, puede buscar en el contenido retenido por la directiva de retención. Para obtener más información, vea [Realizar una investigación de exhibición de documentos electrónicos en Teams](eDiscovery-investigation.md).

> [!IMPORTANT]
> Cuando un usuario o grupo está en espera, se conservan todas las copias de cumplimiento de los mensajes. Por ejemplo, si un usuario publica un mensaje en un canal y luego modifica el mensaje, se conservan ambas copias del mensaje. Sin la retención, solo se conserva el mensaje más reciente.

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>Ubicaciones de contenido que se colocarán en espera para conservar Teams contenido

Como guía útil, use la tabla siguiente para comprender qué ubicaciones de contenido (como un buzón o un sitio) deben colocarse en espera para conservar diferentes tipos de Teams contenido.

|Escenario  |Ubicación de contenido  |
|---------|---------|
|Mensajes de chat para un usuario (por ejemplo, chats 1:1, chats grupales 1:N y conversaciones de canal privado)     |Buzón del usuario         |
|Mensajes de chat en canales estándar y compartidos    |Buzón asociado con el equipo primario         |
|Archivos en canales estándar (por ejemplo, contenido wiki y archivos)     |SharePoint sitio asociado con el equipo primario        |
|Archivos en canales privados y compartidos     |Sitio SharePoint dedicado asociado al canal
|Contenido privado del usuario     |Cuenta de OneDrive para la Empresa usuario       |
|Contenido de tarjeta en chats|Buzón de usuario para chats de 1:1, chats grupales 1:N y conversaciones de canal privado; el buzón del equipo principal para el contenido de la tarjeta en los mensajes de canal estándar y compartido. Para obtener más información, vea la sección "Conservar contenido de tarjeta" en [Crear una retención de exhibición de documentos electrónicos](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).|
|||

> [!NOTE]
> Para conservar el contenido del mensaje en canales privados, debe poner en espera los buzones de usuario (de los miembros de un canal privado). y al usar la herramienta eDiscovery para buscar mensajes de canal privado, debe buscar en el buzón del usuario. Como se indicó anteriormente, los chats de canal privado se almacenan en buzones de usuario, no en el buzón de grupo asociado con el equipo principal.
