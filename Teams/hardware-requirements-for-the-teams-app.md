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
- m365initiative-deployteams
localization_priority: Priority
search.appverid: MET150
description: En este artículo, obtendrá más información sobre los requisitos de hardware necesarios para instalar y ejecutar Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fbc1e3c26cfa6afa4835fc2da1a0aae55a21b17
ms.sourcegitcommit: e60547de6e33ad73ba02c9aa9b5d831100940fbe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/19/2021
ms.locfileid: "53482343"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Requisitos de hardware para Microsoft Teams

Todos los requisitos de las siguientes secciones se aplican tanto a la aplicación de escritorio de Microsoft Teams como a la aplicación web de Teams.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Requisitos de hardware para Teams en un PC Windows

| Componente | Requisito |
|---------|---------|
|Ordenador y procesador    | Mínimo 1.1 GHz o más rápido, 2 núcleos<br><br>Nota: en el caso de los procesadores Intel, es necesario tener en cuenta la velocidad máxima alcanzada con la tecnología Intel Turbo Boost (frecuencia máxima de turbo).         |
|Memoria     |    4,0 GB de RAM (Teams requiere 4 GB de RAM dedicados además de los otros requisitos del sistema)    |
|Disco duro    | 3.0 GB de espacio en disco disponible        |
|Pantalla    |   Resolución de pantalla de 1024 x 768 |
|Hardware de gráficos |  Windows OS: La aceleración del hardware de gráficos requiere DirectX 9 o posterior con WDDM 2.0 o superior para Windows 10 (o WDDM 1.3 o superior para Windows 10 Fall Creators Update)
|Sistema operativo  |    Windows 10 (excepto Windows 10 LTSC), Windows 10 en ARM, Windows 8.1, Windows Server 2019, Windows Server 2016 y Windows Server 2012 R2. Nota: Le recomendamos que use la última versión de Windows y las revisiones de seguridad disponibles.|
|Versión .NET    |  Requiere .NET 4.5 CLR o superior       |
|Vídeo    |  Cámara de vídeo USB 2.0       |
|Dispositivos    |   Cámara, micrófono y altavoces estándar de portátil     |
|Reuniones y llamadas de vídeo|<ul><li>Requiere un procesador de 2 núcleos. Para una mayor resolución de vídeo o de pantalla compartida y tasa de encuadre, se recomienda un procesador de 4 núcleos o mejor.</li> <li>Los efectos de vídeo de fondo requieren Windows 10 o un procesador configurados con instrucción AVX2.</li> <li>Consulte [Recomendaciones de los controladores de decodificadores y codificadores de hardware](hardware-decoders-and-encoders.md) para obtener una lista de los decodificadores y codificadores no admitidos.</li><li>Unirse a una reunión utilizando la detección de proximidad en una Sala de Microsoft Teams requiere Bluetooth LE, que requiere que el Bluetooth esté habilitado en el dispositivo cliente, y para los clientes de Windows también requiere el cliente de Teams de 64 bits. Esta característica no está disponible para clientes de Teams de 32 bits.</li></ul> |
|Eventos en directo en Teams | Si está produciendo un evento en vivo de Teams, recomendamos usar un ordenador que tenga un procesador Core i5 Kaby Lake, 4,0 GB de RAM (o superior) y un codificador de hardware. Consulte [Recomendaciones de los controladores de decodificadores y codificadores de hardware](hardware-decoders-and-encoders.md) para obtener una lista de los decodificadores y codificadores **no admitidos**. |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Requisitos de hardware para Teams en Mac

| Componente | Requisito |
|---------|---------|
|Ordenador y procesador    | Procesador Intel Core Duo |
|Memoria     |   4,0 GB de RAM (Teams requiere 4 GB de RAM dedicados además de los otros requisitos del sistema)     |
|Disco duro    |   1.5 GB de espacio en disco disponible      |
|Pantalla    | resolución de 1280 × 800 o superior    |
|Sistema operativo  |    Una de las tres últimas versiones de macOS. Puede obtener más ifnormación sobre las últimas versiones de macOS y cómo actualizar su versión de macOS [aquí](https://support.apple.com/es-ES/HT201260). Por ejemplo, si se publica una nueva versión de macOS, la nueva versión y las dos que inmediatamente anteriores serán las versiones admitidas.      |
|Vídeo  |    Cámara web compatible     |
|Voz    |  Micrófono y altavoces compatibles, auriculares con micrófono o dispositivo equivalente       |
|Reuniones y llamadas de vídeo | <ul><li>Requiere un procesador de 2 núcleos. Para una mayor resolución de vídeo o de pantalla compartida y tasa de encuadre, se recomienda un procesador de 4 núcleos o mejor. </li><li>Unirse a una reunión usando la detección de proximidad en una Sala de Microsoft Teams no está disponible en macOS.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Requisitos de hardware de la aplicación de Teams en Linux

| Componente | Requisito |
|---------|---------|
|Ordenador y procesador    | 1,6 GHz (o superior) (32 bits o 64 bits), 2 núcleos        |
|Memoria     |    4,0 GB de RAM (Teams requiere 4 GB de RAM dedicados además de los otros requisitos del sistema)   |
|Disco duro    | 3.0 GB de espacio en disco disponible        |
|Pantalla    |   Resolución de pantalla de 1024 x 768 |
|Hardware de gráficos |  128 MB de memoria gráfica
|Sistema operativo  | Distribución de Linux que pueda instalar DEB o RPM. |
|Vídeo    |  Cámara de vídeo USB 2.0       |
|Dispositivos    |   Cámara, micrófono y altavoces estándar de portátil     |
|Voz    |  Micrófono y altavoces compatibles, auriculares con micrófono o dispositivo equivalente       |
|Reuniones y llamadas de vídeo | <ul><li>Requiere un procesador de 2 núcleos. Para una mayor resolución de vídeo o de pantalla compartida y tasa de encuadre, se recomienda un procesador de 4 núcleos o mejor.</li><li>Unirse a una reunión usando la detección de proximidad en una Sala de Microsoft Teams no está disponible en Linux.</li></ul>
|Distribuciones de Linux compatibles | Ubuntu 18.04 LTS, 20.04 LTS, Estación de trabajo Fedora 30, Estación de trabajo RHEL 8, CentOS 8       |
|Entorno de escritorio compatible | GNOME, KDE       |
|Servidor de pantalla compatible | X11       |

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Requisitos de hardware para Teams en dispositivos móviles

Puede usar los equipos en estas plataformas móviles:

- Android: compatible con los teléfonos y tabletas Android.

  La compatibilidad se limita a las **últimas cuatro** versiones principales de Android. Por ejemplo, si se publica una nueva versión principal de Android, el requisito de Android es esta nueva versión y las tres más recientes que la preceden.

- iOS: compatible con iPhone, iPad y iPod Touch.

  La compatibilidad se limita a las **dos** versiones principales más recientes de iOS. Por ejemplo, si se publica una nueva versión principal de iOS, el requisito de iOS es esta nueva versión y la más reciente que la precede. El efecto de vídeo opcional **Difuminar mi fondo** de iOS requiere un sistema operativo de iOS 12 o posterior compatible con los siguientes dispositivos: iPhone 7 o posterior, iPad 2018 (6.ª generación) o posterior y el iPod touch 2019 (7.ª generación).

> [!Note]
> Para la mejor experiencia con Teams, usa la última versión de iOS y Android.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Requisitos de hardware para Teams en un entorno de Infraestructura de Escritorio Virtual (VDI)

Consulte [Teams para la Infraestructura de Escritorio Virtualizado](teams-for-vdi.md) para los requisitos de funcionamiento de Teams en un entorno virtualizado.

### <a name="related-topics"></a>Temas relacionados

- [Consiga aplicaciones para Teams](get-clients.md)
- [Microsoft Teams en dispositivos móviles](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [Instalar la aplicación de Microsoft Teams mediante un MSI](msi-deployment.md)
- [Límites y especificaciones para Microsoft Teams](limits-specifications-teams.md)
