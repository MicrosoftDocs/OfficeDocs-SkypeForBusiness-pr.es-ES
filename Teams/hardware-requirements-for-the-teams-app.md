---
title: Requisitos de hardware para Microsoft Teams
ms.reviewer: microthk, sthurlow
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: En este artículo, obtendrá más información sobre los requisitos de hardware necesarios para instalar y ejecutar Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 55d683c25ec0a5d83bbcf87a2e6df5031ec822f9
ms.sourcegitcommit: 762e303509940f830c304e00a98b05796bf5537f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333260"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Requisitos de hardware para Microsoft Teams

Todos los requisitos de las siguientes secciones se aplican tanto a la aplicación de escritorio de Microsoft Teams como a la aplicación web de Teams.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Requisitos de hardware para Teams en un PC Windows

| Componente | Requisito |
|---------|---------|
|Ordenador y procesador    | Mínimo 1,6 GHz (o superior), 2 núcleos        |
|Memoria     |    4,0 GB DE RAM     |
|Disco duro    | 3.0 GB de espacio en disco disponible        |
|Pantalla    |   Resolución de pantalla de 1024 x 768 |
|Hardware de gráficos |  Sistema operativo Windows: la aceleración de hardware de gráficos requiere DirectX 9 o posterior, con WDDM 2,0 o superior para Windows 10 (o WDDM 1,3 o posterior para Windows 10 Fall Creators Update)
|Sistema operativo  |    Windows 10, Windows 8,1, Windows Server 2019, Windows Server 2016|
|Versión .NET    |  Requiere .NET 4.5 CLR o superior       |
|Vídeo    |  Cámara de vídeo USB 2.0       |
|Dispositivos    |   Cámara, micrófono y altavoces estándar de portátil     |
|Reuniones y llamadas de vídeo|<ul><li>Requiere 2 procesadores básicos. Se recomienda un procesador de 4 núcleos o superior para una mayor resolución de video y pantalla compartida.</li> <li>Consulte [Recomendaciones de los controladores de decodificadores y codificadores de hardware](hardware-decoders-and-encoders.md) para obtener una lista de los decodificadores y codificadores no admitidos..</li><li>Unirse a una reunión mediante la detección de proximidad en una sala de Microsoft Teams requiere Bluetooth LE, que requiere que el Bluetooth esté habilitado en el dispositivo cliente, y para los clientes de Windows también necesita el cliente de equipo de 64 bits. Esta característica no está disponible en los clientes de equipos de 32 bits.</li></ul> |
|Eventos en directo en Teams | Si está generando un evento de Teams Live, le recomendamos que use un equipo con un procesador Core i5 Kaby Lake, 4,0 GB de RAM (o superior) y codificador de hardware. Consulte las [recomendaciones de controlador descodificador y de hardware](hardware-decoders-and-encoders.md) para obtener una lista de descodificadores y codificadores **no admitidos** . |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Requisitos de hardware para Teams en una Mac

| Componente | Requisito |
|---------|---------|
|Ordenador y procesador    | Procesador Intel Core Duo |
|Memoria     |   4,0 GB DE RAM      |
|Disco duro    |   1.5 GB de espacio en disco disponible      |
|Pantalla    | resolución de 1280 × 800 o superior    |
|Sistema operativo  |    Una de las tres versiones más recientes de macOS. Puede encontrar las versiones más recientes de macOS [aquí](https://support.apple.com/en-us/HT201260). Por ejemplo, cuando se publica una nueva versión de macOS, la nueva versión y las dos inmediatamente anteriores se convierten en las versiones admitidas.      |
|Vídeo  |    Cámara web compatible     |
|Voz    |  Micrófono y altavoces compatibles, auriculares con micrófono o dispositivo equivalente       |
|Reuniones y llamadas de vídeo | <ul><li>Requiere 2 procesadores básicos. Se recomienda un procesador de 4 núcleos o superior para una mayor resolución de video y pantalla compartida. </li><li>Unirse a una reunión mediante la detección de proximidad en un salón de Microsoft Teams no está disponible en macOS.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Requisitos de hardware de la aplicación de Teams en Linux

| Componente | Requisito |
|---------|---------|
|Ordenador y procesador    | 1,6 GHz (o superior) (32 bits o 64 bits), 2 núcleos        |
|Memoria     |    4,0 GB DE RAM     |
|Disco duro    | 3.0 GB de espacio en disco disponible        |
|Pantalla    |   Resolución de pantalla de 1024 x 768 |
|Hardware de gráficos |  128 MB de memoria gráfica
|Sistema operativo  | Distribución de Linux que pueda instalar DEB o RPM. |
|Vídeo    |  Cámara de vídeo USB 2.0       |
|Dispositivos    |   Cámara, micrófono y altavoces estándar de portátil     |
|Voz    |  Micrófono y altavoces compatibles, auriculares con micrófono o dispositivo equivalente       |
|Reuniones y llamadas de vídeo | <ul><li>Requiere 2 procesadores básicos. Se recomienda un procesador de 4 núcleos o superior para una mayor resolución de video y pantalla compartida.</li><li>Unirse a una reunión usando la detección de proximidad en una Sala de Microsoft Teams no está disponible en Linux.</li></ul>
|Distribuciones de Linux compatibles | Ubuntu 16.04 LTS, 18.04 LTS, Estación de trabajo Fedora 30, Estación de trabajo RHEL 8, CentOS 8

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Requisitos de hardware para Teams en dispositivos móviles

Puede usar los equipos en estas plataformas móviles:

- Android: compatible con los teléfonos y tabletas Android.

  El soporte técnico está limitado a las **últimas cuatro** versiones principales de Android. Por ejemplo, cuando se publica una nueva versión principal de Android, el requisito de Android es la nueva versión y las tres versiones más recientes que lo preceden.

- iOS: compatible con iPhone, iPad y iPod Touch.

  El soporte técnico está limitado a las **dos** versiones principales más recientes de iOS. Por ejemplo, cuando se publica una nueva versión principal de iOS, el requisito de iOS es la nueva versión y las versiones más recientes que le precedían. El efecto de **desenfoque** de vídeo de fondo opcional en iOS requiere un sistema operativo de iOS 12 o posterior, compatible con los siguientes dispositivos: iPhone 7 o posterior, iPad 2018 (sexta generación) o posterior, y el iPod Touch 2019 (séptima generación).

> [!Note]
> Para la mejor experiencia con Teams, usa la última versión de iOS y Android.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Requisitos de hardware para Teams en un entorno de Infraestructura de Escritorio Virtual (VDI)

Consulte [Teams para la Infraestructura de Escritorio Virtualizado](teams-for-vdi.md) para los requisitos de funcionamiento de Teams en un entorno virtualizado.

### <a name="related-topics"></a>Temas relacionados

- [Consiga aplicaciones para Teams](get-clients.md)
- [Microsoft Teams en dispositivos móviles](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [Instalar la aplicación de Microsoft Teams mediante un MSI](msi-deployment.md)
- [Límites y especificaciones para Microsoft Teams](limits-specifications-teams.md)
