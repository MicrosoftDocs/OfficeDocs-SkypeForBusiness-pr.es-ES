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
description: Obtenga información sobre cómo poner a un usuario o equipo de Microsoft Teams en una retención legal mediante el portal de cumplimiento de Microsoft Purview y obtenga información sobre lo que necesita una retención legal en función de los requisitos de datos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d56bece07fe7342c4156abdae73508a1a149864
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922461"
---
# <a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>Poner a un usuario o un equipo de Microsoft Teams en retención legal

Cuando existe una expectativa razonable de litigios, las organizaciones deben conservar la información almacenada electrónicamente (ESI), incluidos Teams mensajes de chat que sean relevantes para el caso. Es posible que las organizaciones tengan que conservar todos los mensajes relacionados con una investigación específica o para una persona determinada. En este artículo se trata el uso de una suspensión legal para conservar el contenido de Microsoft Teams. Para conservar el contenido de otros servicios de Microsoft 365, vea [Crear una retención de exhibición de documentos electrónicos](/microsoft-365/compliance/create-ediscovery-holds).

> [!NOTE]
> En febrero de 2020, se activó la suspensión legal de los canales privados. Los chats de canales privados se almacenan en buzones de usuario, mientras que los chats de canal estándar se almacenan en el buzón asociado al equipo primario. Si ya existe una retención legal para un buzón de usuario, la directiva de retención ahora se aplicará automáticamente a los mensajes de canal privado almacenados en ese buzón. No es necesario realizar ninguna acción adicional para que un administrador active esta opción. También se admite la retención legal de archivos compartidos en canales privados.

Dentro de Microsoft Teams, se puede poner en retención legal a todo un equipo o a usuarios seleccionados. Al hacerlo, se asegurará de que todos los mensajes que se intercambiaron en esos equipos (incluidos los canales privados y compartidos) o los mensajes intercambiados por esas personas sean reconocibles por los administradores de cumplimiento de la organización o Teams administradores.

> [!NOTE]
> Si pone a un usuario en retención, el grupo no se pondrá en retención y viceversa.
> Las notificaciones enviadas en fuentes de actividades no se pueden poner en espera.

Para poner a un usuario o un equipo en retención legal en un caso de eDiscovery principal:

1. Vaya al [portal de cumplimiento de Microsoft Purview](https://compliance.microsoft.com). Al crear un nuevo caso, se le presenta la opción de poner buzones o sitios en espera.

2. Vaya a **eDiscoveryCore** >  y cree un caso haciendo clic en **Crear un caso**. Una vez creado el caso, ábralo.
  
   ![Microsoft Teams pestaña Exhibición de documentos electrónicos está seleccionada, que muestra el botón Crear un caso.](media/LegalHold1.png)

   > [!NOTE]
   > También puede colocar un usuario en una retención asociada a un caso de Advanced eDiscovery. Para obtener más información, vea [Administrar retenciones en Advanced eDiscovery](/microsoft-365/compliance/managing-holds).

3. Vaya a la pestaña **Retenciones** del menú superior y haga clic en **Crear** para crear una retención. Poner un usuario o un equipo en espera conserva todos los mensajes intercambiados por dichos usuarios. Al crear un nuevo caso, se le presenta la opción de poner buzones o sitios en espera.

   ![Imagen que muestra la pestaña Retenciones seleccionada y el botón Crear debajo.](media/LegalHold2.png)

   1. **Ponle nombre a tu retención**. Seleccione un nombre descriptivo y único para la retención que va a crear.
  
       ![Esta captura de pantalla muestra la pestaña Dar nombre a la retención, donde puede escribir un nombre y una descripción de la retención que está creando.](media/LegalHold3.png)

   2. **Elija la ubicación**. Elija si quiere que la retención se aplique a un usuario o a todo un equipo (por ahora no se puede aplicar una suspensión en canales individuales). Si un usuario está en espera, se conservan todos sus mensajes, incluidos los mensajes de chats individuales, chats grupales y canales privados. Los mensajes en canales estándar y compartidos se conservan cuando el equipo primario se pone en espera.

      ![Elija las ubicaciones de datos que desea poner en espera.](media/LegalHold4.png)

   3. **Crear consulta**. Puede personalizar la retención si quiere más granularidad en la directiva de retención. Por ejemplo, puede especificar palabras clave para buscar, o puede agregar más condiciones, que tendrían que cumplirse para que la retención surta efecto.

   4. **Revisa la configuración antes de** crear la retención.

Una vez creada la retención, puede buscar el contenido retenido por la directiva de retención. Para obtener más información, vea [Realizar una investigación de exhibición de documentos electrónicos en Teams](eDiscovery-investigation.md).

> [!IMPORTANT]
> Cuando un usuario o grupo se pone en espera, se conservan todas las copias de cumplimiento de los mensajes. Por ejemplo, si un usuario publica un mensaje en un canal y luego modifica el mensaje, se conservan ambas copias del mensaje. Sin la retención, solo se conserva el mensaje más reciente.

## <a name="content-locations-to-place-on-hold-to-preserve-teams-content"></a>Ubicaciones de contenido en espera para conservar Teams contenido

Como guía útil, use la tabla siguiente para comprender qué ubicaciones de contenido (como un buzón o un sitio) colocar en espera para conservar diferentes tipos de contenido Teams.

|Escenario  |Ubicación del contenido  |
|---------|---------|
|Mensajes de chat para un usuario (por ejemplo, chats 1:1, chats de grupo 1:N y conversaciones de canal privado)     |Buzón del usuario         |
|Mensajes de chat en canales estándar y compartidos    |Buzón asociado al equipo principal         |
|Archivos en canales estándar (por ejemplo, contenido wiki y archivos)     |SharePoint sitio asociado con el equipo principal        |
|Archivos en canales privados y compartidos     |Sitio de SharePoint dedicado asociado con el canal
|Contenido privado del usuario     |La cuenta de OneDrive para la Empresa del usuario       |
|Contenido de tarjeta en chats|Buzón de usuario para chats 1:1, chats de grupo 1:N y conversaciones de canal privado; el buzón del equipo primario para el contenido de la tarjeta en mensajes de canal estándar y compartidos. Para obtener más información, vea la sección "Conservar contenido de tarjeta" en [Crear una retención de exhibición de documentos electrónicos](/microsoft-365/compliance/create-ediscovery-holds#preserve-card-content).|
|||

> [!NOTE]
> Para conservar el contenido del mensaje en canales privados, debe poner los buzones de usuario (de los miembros de un canal privado) en espera. y al usar la herramienta eDiscovery para buscar mensajes de canal privado, tiene que buscar en el buzón del usuario. Como se indicó anteriormente, los chats de canal privado se almacenan en buzones de usuario, no en el buzón de grupo asociado con el equipo primario.
