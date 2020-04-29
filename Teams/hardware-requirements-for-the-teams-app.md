---
title: Requisitos de hardware para Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: En este artículo, obtendrá información sobre los requisitos de hardware necesarios para instalar y ejecutar Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4eb43e79a7ad45596876a3fc932ad405271b0dda
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918508"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Requisitos de hardware para Microsoft Teams

Todos los requisitos de las siguientes secciones se aplican tanto a la aplicación de escritorio de Microsoft Teams como a la aplicación web de Teams.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Requisitos de hardware para Teams en un PC Windows

|**Componente**|**Requisito**  |
|---------|---------|
|Ordenador y procesador    | Mínimo 1,6 GHz (o superior) (32 bits o 64 bits).        |
|Memoria     |    2.0 GB de RAM     |
|Disco duro    | 3.0 GB de espacio en disco disponible        |
|Pantalla    |   Resolución de pantalla de 1024 x 768 |
|Hardware de gráficos |  128 MB de memoria gráfica como mínimo
|Sistema operativo  |    Windows Server 2012 R2 +, Windows 10 o Windows 8.1 en 32 bits y 64 bits. Para una mejor experiencia, utilice la última versión de su sistema operativo.|
|Versión .NET    |  Requiere .NET 4.5 CLR o superior       |
|Vídeo    |  Cámara de vídeo USB 2.0       |
|Dispositivos    |   Cámara, micrófono y altavoces estándar de portátil     | 
|Reuniones y llamadas de vídeo | <ul><li>Para tener una mejor experiencia con las videollamadas y las reuniones en línea, se recomienda utilizar un equipo que tenga un procesador de 2,0 GHz y 4,0 GB de RAM (o mayor). </li><li>El efecto opcional **Desenfocar mi vídeo de fondo** requiere un procesador compatible con Advanced Vector Extensions 2 (AVX2). Consulte [Recomendaciones de los controladores de decodificadores y codificadores de hardware](hardware-decoders-and-encoders.md) para obtener una lista de los decodificadores y codificadores no admitidos..</li><li>Unirse a una reunión utilizando la detección de proximidad en una Sala de Microsoft Teams requiere Bluetooth LE, que requiere que el Bluetooth esté habilitado en el dispositivo cliente, y para los clientes de Windows requiere el cliente de Teams de 64 bits. No está disponible para los clientes de Teams de 32 bits.</li></ul> |
|Eventos en directo en Teams | Si está produciendo un evento en vivo de Teams, recomendamos usar una computadora que tenga un procesador Core i5 Kaby Lake, 4.0 GB de RAM (o superior) y un codificador de hardware. Consulte [Recomendaciones de los controladores de decodificadores y codificadores de hardware](hardware-decoders-and-encoders.md) para obtener una lista de los decodificadores y codificadores no admitidos.. |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Requisitos de hardware para Teams en una Mac

|**Componente**|**Requisito**  |
|---------|---------|
|Procesador    | Procesador mínimo Intel, Core 2 Duo o superior |
|Memoria     |   2.0 GB de RAM      |
|Disco duro    |   1.5 GB de espacio en disco disponible      |
|Pantalla    | resolución de 1280 × 800 o superior    |
|Sistema operativo  |    Mac OS X 10.11 el Capitan o posterior     |
|Vídeo  |    Cámara web compatible     |
|Voz    |  Micrófono y altavoces compatibles, auriculares con micrófono o dispositivo equivalente       |
|Reuniones y llamadas de vídeo | Para tener una mejor experiencia con las llamadas de vídeo y las reuniones en línea, se recomienda utilizar un equipo que tenga un procesador de 2.0 GHz y 4.0 GB de RAM (o superior).  <ul><li>El efecto opcional de vídeo **Desenfocar mi fondo** requiere un procesador compatible con Advanced Vector Extensions 2 (AVX2), compatible con la mayoría de los dispositivos Mac de finales de 2013 y posteriores. Consulte [Recomendaciones de los controladores de decodificadores y codificadores de hardware](hardware-decoders-and-encoders.md) para obtener una lista de los decodificadores y codificadores no admitidos..</li><li>Unirse a una reunión usando la detección de proximidad en una sala de Microsoft Teams no está disponible en Mac OS.</li></ul> |

## <a name="hardware-requirements-for-teams-on-linux"></a>Requisitos de hardware de la aplicación de Teams en Linux

|**Componente**|**Requisito**  |
|---------|---------|
|Ordenador y procesador    | Mínimo 1,6 GHz (o superior) (32 bits o 64 bits).        |
|Memoria     |    2.0 GB de RAM     |
|Disco duro    | 3.0 GB de espacio en disco disponible        |
|Pantalla    |   Resolución de pantalla de 1024 x 768 |
|Hardware de gráficos |  128 MB de memoria gráfica como mínimo
|Sistema operativo  | Distribución de Linux que pueda instalar DEB o RPM. |
|Vídeo    |  Cámara de vídeo USB 2.0       |
|Dispositivos    |   Cámara, micrófono y altavoces estándar de portátil     | 
|Voz    |  Micrófono y altavoces compatibles, auriculares con micrófono o dispositivo equivalente       |
|Reuniones y llamadas de vídeo | <ul><li>Para tener una mejor experiencia con las llamadas de vídeo y las reuniones en línea, se recomienda utilizar un equipo que tenga un procesador de 2.0 GHz y 4.0 GB de RAM (o superior). </li><li>Los efectos de vídeo en segundo plano requieren un procesador con compatibilidad con Advanced vector Extensions 2 (AVX2), compatible con la mayoría de los dispositivos Mac de 2013 última versión y posterior. Consulte [Recomendaciones de los controladores de decodificadores y codificadores de hardware](hardware-decoders-and-encoders.md) para obtener una lista de los decodificadores y codificadores no admitidos..</li><li>Unirse a una reunión usando la detección de proximidad en una Sala de Microsoft Teams no está disponible en Linux.</li></ul>
|Distribuciones de Linux compatibles | Ubuntu 16.04 LTS, 18.04 LTS, Estación de trabajo Fedora 30, Estación de trabajo RHEL 8, CentOS 8

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Requisitos de hardware para Teams en dispositivos móviles

Puede usar los equipos en estas plataformas móviles:

- Android: compatible con los teléfonos y tabletas Android.

  La compatibilidad se limita a las últimas cuatro versiones principales de Android. Cuando se lanza una nueva versión principal de Android, la nueva versión y las tres anteriores serán oficialmente compatibles.

- iOS: compatible con iPhone, iPad y iPod Touch.

  La compatibilidad se limita a las dos versiones principales más recientes de iOS. Cuando se lanza una nueva versión principal de iOS, la nueva versión de iOS y la anterior están oficialmente soportadas.

Para la mejor experiencia con Teams, usa la última versión de iOS y Android.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Requisitos de hardware para Teams en un entorno de Infraestructura de Escritorio Virtual (VDI)

Consulte [Teams para la Infraestructura de Escritorio Virtualizado](teams-for-vdi.md) para los requisitos de funcionamiento de Teams en un entorno virtualizado.

### <a name="related-topics"></a>Temas relacionados
- [Consiga aplicaciones para Teams](get-clients.md)
- [Microsoft Teams en dispositivos móviles](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [Instalar la aplicación de Microsoft Teams mediante un MSI](msi-deployment.md)
- [Límites y especificaciones para Microsoft Teams](limits-specifications-teams.md)
