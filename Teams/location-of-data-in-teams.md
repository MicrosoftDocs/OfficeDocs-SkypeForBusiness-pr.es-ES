---
title: Ubicación de los datos en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: Obtenga información sobre dónde se almacenan los datos en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3908100a0270f9e72835e189a220ece6e54a27bd
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836540"
---
# <a name="location-of-data-in-microsoft-teams"></a>Ubicación de los datos en Microsoft Teams

Los datos de Teams residen en la región geográfica asociada con su inquilino de Office 365. En la actualidad, Teams es compatible con Australia, Canadá, Francia, Alemania, India, Japón, Sudáfrica, Corea del sur, Suiza (que incluye a Liechtenstein), las regiones de los Emiratos Árabes Unidos, América del sur, América, APAC y EMEA. 

> [!IMPORTANT]
> Actualmente, Teams ofrece residencia de datos en Australia, Canadá, Francia, Alemania, India, Japón, los Emiratos Árabes Unidos, el Reino Unido, Corea del sur, Sudáfrica y Suiza (que incluye Liechtenstein) solo para los nuevos inquilinos.
> Un inquilino nuevo se define como cualquier inquilino que no ha tenido ningún usuario desde el inicio de sesión del inquilino en Teams. Los inquilinos existentes de Australia, India, Japón y Corea del sur seguirán teniendo los datos de sus equipos almacenados en la región de APAC. Los inquilinos existentes de Canadá seguirán teniendo sus datos almacenados en América. Los inquilinos existentes en Francia, Alemania, Liechtenstein, los Emiratos Árabes Unidos, el Reino Unido, Sudáfrica y Suiza tendrán sus datos almacenados en la región de EMEA.

## <a name="where-your-teams-data-is-stored"></a>Dónde se almacenan los datos de su equipo

Para ver qué región hospeda los datos de su inquilino, vaya al**perfil**de la organización**configuración** > del [Centro](https://portal.office.com/adminportal/home) > de administración de 365 de Microsoft. Desplácese hasta **Data location** (Ubicación de datos).

![Captura de pantalla de la tabla de ubicación de datos que incluye equipos en el centro de administración](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a>Ubicación de datos de Teams en reposo

Los datos de Teams se almacenan de forma diferente según el tipo de contenido. 

![Diagrama que muestra los tipos de contenido de Teams y dónde se almacenan en el resto](media/location-of-data-storage-at-rest.png)

Consulte la sesión de la [sección de encendido en la arquitectura de Microsoft Teams](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) para obtener información detallada.

### <a name="core-teams-customer-data"></a>Datos de los clientes principales de Teams

Si tu espacio empresarial está aprovisionado en Australia, Canadá, la Unión Europea, Francia, Alemania, India, Japón, Sudáfrica, Corea del sur, Suiza (que incluye Liechtenstein), los Emiratos Árabes Unidos, el Reino Unido o los Estados Unidos, las tiendas Microsoft los siguientes datos del cliente en reposo solo dentro de esa ubicación:

- Chats de Teams, conversaciones de equipos y canales, imágenes, mensajes de voz y contactos
- Contenido del sitio de SharePoint Online y los archivos almacenados en ese sitio
- Archivos cargados en OneDrive para la empresa

#### <a name="chat-channel-messages-team-structure"></a>Chat, mensajes de canal, estructura del equipo

Cada equipo de Teams está respaldado por un grupo de Office 365 y su sitio de SharePoint y buzón de Exchange. Los chats privados (incluidos los chats grupales), los mensajes enviados como parte de una conversación en un canal, y la estructura de los equipos y canales se almacenan en un servicio de chat que se ejecuta en Azure. Los datos también se almacenan en una carpeta oculta en los buzones de usuario y de grupo para habilitar las características de protección de la información.

#### <a name="voicemail-and-contacts"></a>Buzón de voz y contactos

Los mensajes de voz se almacenan en Exchange. Los contactos se almacenan en el almacén de datos en la nube basado en Exchange. Exchange y la tienda en nube basada en Exchange ya proporcionan residencia de datos en cada uno de los GEOS del centro de datos de todo el mundo. Para todos los equipos, el buzón de voz y los contactos se almacenan en país para Australia, Canadá, Francia, Alemania, India, Japón, los Emiratos Árabes Unidos, el Reino Unido, Sudáfrica, Corea del sur, Suiza (incluye Liechtenstein) y Estados Unidos. Para todos los demás países, los archivos se almacenan en la ubicación de los Estados Unidos, Europa o Asia-Pacífico según la afinidad de los inquilinos.

#### <a name="images-and-media"></a>Imágenes y elementos multimedia

Los medios que se usan en los chats (excepto los archivos GIF de Giphy que no se almacenan pero que son un vínculo de referencia a la dirección URL del servicio de Giphy original, Giphy es un servicio que no es de Microsoft) se almacenan en un servicio multimedia basado en Azure que se implementa en las mismas ubicaciones que el servicio de chat.

#### <a name="files"></a>Archivos

Archivos (incluidos OneNote y wiki) que alguien comparte en un canal se almacena en el sitio de SharePoint del equipo. Los archivos compartidos en una conversación privada o una conversación durante una reunión o una llamada se cargan y almacenan en la cuenta empresarial de OneDrive para la empresa del usuario que comparte el archivo. Exchange, SharePoint y OneDrive ya proporcionan residencia de datos en cada uno de los GEOS del centro de datos de todo el mundo. Por lo tanto, para los clientes existentes, todos los archivos, blocs de notas de OneNote, contenido wiki de equipos y buzones que forman parte de la experiencia de Teams ya están almacenados en la ubicación en función de su afinidad de inquilino. Los archivos se almacenan en el país de Australia, Canadá, Francia, Alemania, India, Japón, los Emiratos Árabes Unidos, el Reino Unido, Sudáfrica y Suiza (que incluye a Liechtenstein). Para todos los demás países, los archivos se almacenan en la ubicación de los Estados Unidos, Europa o Asia Pacífico según la afinidad de los inquilinos.

### <a name="datacenter-locations"></a>Ubicaciones de centro de recursos

Los servicios de Teams descritos en esta sección almacenan datos en reposo en las siguientes ubicaciones:

|País o región  |Ubicación del centro de recursos |
|---------|---------|
|Australia   |Nueva Gales del sur y Victoria         |
|Canadá    |Quebec City y Toronto         |
|Francia    |Marseille y París         |
|Alemania    |Berlín y Frankfurt      |
|India   |Chennai y Pune        |
|Japón    |Tokio (Saitama) y Osaka         |
|Liechtenstein   |Ginebra y Zurich       |
|Sudáfrica     |Johannesburgo y ciudad del cabo         |
|Corea del Sur     |Seúl y Busan         |
|Suiza    |Ginebra y Zurich       |
|Emiratos Árabes Unidos     |Abu Dhabi y Dubai         |
|Reino Unido     | Cardiff y Londres        |
|América: Norte y Sur (AMER) |Bahía, CA y Boydton, VA       |
|Asia Pacífico (APAC)  |Singapur y Hong Kong        |
|Europa, Oriente Medio y Asia (EMEA)   |Dublín y Amsterdam        |

> [!NOTE]
> Para Liechtenstein, los datos se almacenan en reposo en los centros de datos de Suiza en Ginebra y Zurich.

### <a name="data-stored-with-a-third-party-storage-provider"></a>Datos almacenados en un proveedor de almacenamiento de terceros

Las organizaciones que permiten a los usuarios almacenar archivos con un proveedor de almacenamiento de terceros dependen de la ubicación de almacenamiento de esos servicios y, por lo tanto, deben revisar la ubicación de los datos en reposo para esos servicios por separado.

- **Pestañas**: las pestañas permiten a los usuarios anclar información de aplicaciones y servicios en un canal. Por lo tanto, varía según el tipo de la pestaña en la que se almacenan los datos. La propia pestaña no almacena ningún dato. Por ejemplo, una pestaña de SharePoint almacenará datos en función de dónde se aprovisionó la colección de sitios de SharePoint. Una pestaña que incluya información de un asociado almacenará los datos directamente en el sistema que usa el socio y solo presentará una vista de la misma.
- **Otras aplicaciones de Partners**: Microsoft no ofrece ninguna compatibilidad de residencia de datos para las aplicaciones y los servicios de socios que puede estar usando dentro de la experiencia de Teams. Revise la información de esas soluciones directamente para saber dónde se almacenan sus datos.

## <a name="see-also"></a>Vea también

- [Microsoft Teams lanza la residencia de datos de Emiratos Árabes Unidos](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [Microsoft Teams inicia la residencia de datos Corea del sur](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [Microsoft Teams lanza la residencia de datos de Sudáfrica](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [Microsoft Teams lanza la residencia de datos de Francia](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [Microsoft Teams lanza la residencia de datos de India, otras GEOS pronto](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [Microsoft Teams lanza la residencia de datos de Australia y Japón](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [Microsoft Teams lanza la residencia de datos de Canadá, Australia y Japón próximamente](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
