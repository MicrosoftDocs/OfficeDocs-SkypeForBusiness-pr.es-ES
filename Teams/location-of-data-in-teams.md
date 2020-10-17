---
title: Ubicación de los datos en Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: En este artículo, obtendrá información sobre dónde residen los datos geográficamente en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c16065a864ac82cdf5f11c0d2c8254b648731cac
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121690"
---
# <a name="location-of-data-in-microsoft-teams"></a>Ubicación de los datos en Microsoft Teams

Los datos de Teams residen en la región geográfica asociada con su organización de Microsoft 365 u Office 365. Actualmente, Teams es compatible con las regiones de Australia, Canadá, Francia, Alemania, India, Japón, Sudáfrica, Corea del sur, Suiza (incluido Liechtenstein), los Emiratos Árabes Unidos, Reino Unido, América, APAC y EMEA. 

> [!IMPORTANT]
> Actualmente, Teams ofrece residencia de datos en Australia, Canadá, Francia, Alemania, India, Japón, Emiratos Árabes Unidos, Reino Unido, Corea del Sur, Sudáfrica y Suiza (incluido Liechtenstein) solo para nuevos espacios empresariales.
> Un nuevo espacio empresarial se define como un espacio empresarial que no ha tenido un solo usuario que haya iniciado sesión en Teams. Los espacios empresariales existentes de Australia, India, Japón y Corea del sur seguirán teniendo sus datos de Teams almacenados en la región de APAC. Los espacios empresariales de Canadá existentes seguirán teniendo los datos almacenados en América. Los espacios empresariales existentes en Francia, Alemania, Liechtenstein, los Emiratos Árabes Unidos, el Reino Unido, Sudáfrica y Suiza tendrán los datos almacenados en la región EMEA.

## <a name="where-your-teams-data-is-stored"></a>Dónde se almacenan sus datos de Teams

Para ver qué región aloja los datos de su espacio empresarial, vaya al [Centro de administración de Microsoft 365](https://portal.office.com/adminportal/home) > **Configuración** > **Perfil de organización**. Desplácese hacia abajo hasta **Ubicación de datos**.

![Captura de pantalla de tabla de ubicación de datos, incluido Teams, en el centro de administración](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>Ubicación de los datos de Teams en reposo

Los datos de Teams se almacenan de forma diferente en función del tipo de contenido. 

![Diagrama que muestra los tipos de contenido de Teams y dónde se almacenan en reposo](media/location-of-data-storage-at-rest.png)

Consulte la [Sesión de subgrupo de Ignite sobre la arquitectura de Microsoft Teams](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) para ver una discusión en profundidad.

### <a name="core-teams-customer-data"></a>Datos principales de clientes de Teams

Si su espacio empresarial está aprovisionado en Australia, Canadá, la Unión Europea, Francia, Alemania, India, Japón, Sudáfrica, Corea del Sur, Suiza (incluido Liechtenstein), los Emiratos Árabes Unidos, el Reino Unido o Estados Unidos, Microsoft almacena únicamente los datos de clientes siguientes en esa ubicación:

- Chats de Teams, conversaciones de canal y equipo, imágenes, mensajes de correo de voz y contactos
- Contenido del sitio de SharePoint Online y los archivos almacenados en ese sitio
- Archivos cargados en OneDrive para la Empresa

#### <a name="chat-channel-messages-team-structure"></a>Chat, mensajes del canal, estructura del equipo

Cada equipo de Teams está respaldado por un grupo de Microsoft 365 y su sitio de SharePoint y buzón de Exchange. Los chats privados (incluyendo chats grupales), mensajes enviados como parte de una conversación en un canal, y la estructura de los equipos y canales se almacenan en un servicio de chat que se ejecuta en Azure. Los datos también se almacenan en una carpeta oculta en los buzones de usuario y de grupo para habilitar las características de protección de la información.

#### <a name="voicemail-and-contacts"></a>Correo de voz y contactos

El correo de voz se almacena en Exchange. Los contactos se almacenan en un almacén de datos en la nube basado en Exchange. Exchange y la tienda en la nube basada en Exchange ya proporcionan residencia de datos en cada uno de los centros de datos de áreas geográficas de todo el mundo. Para todos los equipos, el correo de voz y los contactos se almacenan en el país para Australia, Canadá, Francia, Alemania, India, Japón, los Emiratos Árabes Unidos, el Reino Unido, Sudáfrica, Corea del sur, Suiza (incluido Liechtenstein) y los Estados Unidos. Para todos los demás países o regiones, los archivos se almacenan en la ubicación de Estados Unidos, Europa o Asia-Pacífico basándose en la afinidad de espacio empresarial.

#### <a name="images-and-media"></a>Imágenes y elementos multimedia

Los elementos multimedia utilizados en chats (excepto los GIF de Giphy que no se almacenan pero que son un vínculo de referencia a la dirección URL del servicio Giphy original, Giphy es un servicio que no es de Microsoft) se almacenan en un servicio multimedia basado en Azure que se implementa en las mismas ubicaciones que el servicio de chat.

#### <a name="files"></a>Archivos

Los archivos (incluyendo OneNote y Wiki) que alguien comparte en un canal se almacenan en el sitio de SharePoint del equipo. Los archivos compartidos en un chat privado o un chat durante una reunión o llamada se cargan y se almacenan en la cuenta de OneDrive para la Empresa del usuario que comparte el archivo. Exchange, SharePoint y OneDrive ya proporcionan residencia de datos en cada uno de los centros de datos de áreas geográficas de todo el mundo. Por lo tanto, para los clientes existentes, todos los archivos, los blocs de notas de OneNote, el contenido wiki de Teams y los buzones de correo que forman parte de la experiencia de Teams ya se almacenan en la ubicación según su afinidad de espacio empresarial. Los archivos se almacenan en el país para Australia, Canadá, Francia, Alemania, India, Japón, los Emiratos Árabes Unidos, el Reino Unido, Sudáfrica, Corea del sur y Suiza (incluido Liechtenstein). Para todos los demás países o regiones, los archivos se almacenan en la ubicación de Estados Unidos, Europa o Asia Pacífico basándose en la afinidad de espacio empresarial.

### <a name="datacenter-locations"></a>Ubicaciones de centros de datos

Los servicios de Teams descritos en esta sección almacenan datos en reposo en las siguientes ubicaciones:

|País o región  |Ubicación del centro de datos |
|---------|---------|
|Australia   |Nueva Gales del Sur y Victoria         |
|Canadá    |Quebec City y Toronto         |
|Francia    |Marsella y Paris         |
|Alemania    |Berlín y Frankfurt      |
|India   |Chennai y Pune        |
|Japón    |Tokio (Saitama) y Osaka         |
|Liechtenstein   |Ginebra y Zurich       |
|Sudáfrica     |Johannesburgo y Ciudad del Cabo         |
|Corea del Sur     |Seúl y Busan         |
|Suiza    |Ginebra y Zurich       |
|Emiratos Árabes Unidos     |Abu Dhabi y Dubai         |
|Reino Unido     | Cardiff y Londres        |
|América: Norte y Sur (AMER) |Bay, CA y Boydton, VA       |
|Asia Pacífico (APAC)  |Singapur y RAE de Hong Kong        |
|Europa, Oriente Medio y Asia (EMEA)   |Dublín y Amsterdam        |

> [!NOTE]
> Para Liechtenstein, los datos se almacenan en reposo en los centros de datos de Suiza en Ginebra y Zurich.

### <a name="data-stored-with-a-third-party-storage-provider"></a>Datos almacenados con un proveedor de almacenamiento de terceros

Las organizaciones que permiten a los usuarios almacenar archivos con un proveedor de almacenamiento externo dependen de la ubicación de almacenamiento de esos servicios y, por lo tanto, deben revisar la ubicación de los datos en reposo para esos servicios por separado.

- **Pestañas**: las pestañas permiten a los usuarios fijar información de aplicaciones y servicios en un canal. Por lo tanto, varía según el tipo de la pestaña en la que se almacenan los datos. La pestaña en sí no almacena ningún dato. Por ejemplo, en una pestaña de SharePoint se almacenan datos en función de dónde se aprovisionó la colección de sitios de SharePoint. Una pestaña que incluya información de un asociado almacenará los datos directamente en el sistema que use el asociado y solo se mostrará una vista de la misma.
- **Otras aplicaciones de asociados**: Microsoft no proporciona ningún soporte de residencia de datos para aplicaciones y servicios de asociados que pueda estar usando dentro de la experiencia de Teams. Revise la información de esas soluciones directamente para obtener información sobre dónde se almacenan los datos.

## <a name="see-also"></a>Consulte también

- [Microsoft Teams lanza la residencia de datos de los Emiratos Árabes Unidos](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft Teams inicia la residencia de datos de Corea del sur](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft Teams lanza la residencia de datos de Sudáfrica](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft Teams lanza la residencia de datos de Francia](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft Teams lanza la residencia de datos de India; próximamente otras áreas geográficas](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083) 

- [Microsoft Teams lanza la residencia de datos de Australia y Japón](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft Teams lanza la residencia de datos de Canada; próximamente Australia y Japón](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
