---
title: Entrada y publicación de la sala en Microsoft Teams paneles
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: gary.lai
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
ms.topic: reference
search.appverid: MET150
description: En este artículo se proporcionan instrucciones sobre cómo habilitar la protección y la versión de la sala Teams dispositivos de paneles.
ms.openlocfilehash: 9e90916c5db4d5ec32a40f0e021f9bf7b294d09f
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2022
ms.locfileid: "63689165"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Entrada y publicación de la sala en Microsoft Teams paneles

Cuando el check-in y la versión de sala están habilitados, los usuarios se Teams en los paneles de la sala que reservaron al principio de la reunión. Si un usuario no hace el check-in dentro de una cantidad de tiempo establecida después de la hora de inicio de la reunión, la sala de reunión declina la invitación a la reunión, envía un mensaje de cancelación al organizador de la reunión y la sala está disponible para que otras personas puedan reservar.  

## <a name="requirements"></a>Requirements 

Esta característica se puede usar en una implementación independiente Teams panel. También puede emparejar paneles Teams con Salas de Teams en Android con la versión 1449/1.0.96.2022011305 o posterior para funcionalidades adicionales como notificaciones de protección.  

## <a name="enable-check-in-and-room-release"></a>Habilitar la protección y la versión de sala 

La entrada y la versión de sala están desactivadas de forma predeterminada. Para activarlo,  

1. En el panel Teams, inicie sesión con sus credenciales de administrador.  

2. Vaya a **Configuración > dispositivo Configuración > de Configuración > aplicaciones paneles Configuración > reuniones**.

3. Active la sala de versiones si nadie lo comprueba.

4. Para ajustar la cantidad de tiempo que los usuarios tienen que hacer el check-in antes de que se libere la sala, vaya a **Liberar después de:** y seleccione una opción en la lista desplegable.  

Cuando Teams paneles se emparejan con una sala de Teams en Android, un usuario puede realizar el check-in uniéndose a la reunión en la sala de Teams.  

## <a name="turn-on-check-in-notifications"></a>Activar las notificaciones de check-in

> [!NOTE]
> Esta característica solo está disponible actualmente en Teams paneles que están emparejados con una sala de Teams en Android. El Teams y el Teams deben haber iniciado sesión en la misma cuenta de recursos. Vea [Emparejar un panel Teams con una sala Microsoft Teams en Android para](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android) obtener más información.  

Las notificaciones de check-in se envían cuando una reunión continúa más allá de su intervalo de tiempo reservado. Una vez que un usuario de la siguiente reunión se haya registrado, la notificación aparecerá en la pantalla frontal de la sala en la hora de inicio de la reunión programada para que los participantes de la reunión anterior sepan que su reserva ha terminado y que los usuarios esperan el espacio.  

Para activar las notificaciones de check-in,  

1. En el panel Teams, inicie sesión con sus credenciales de administrador. 

2. Vaya a **Configuración > dispositivo Configuración > de Configuración > aplicaciones paneles Configuración > reuniones**.

3. Vaya a **Check-in** y active **Enviar notificación de check-in**.

## <a name="related-topics"></a>Temas relacionados

- [Cómo usar Microsoft Teams paneles](use-teams-panels.md)

- [Microsoft Teams paneles](teams-panels.md)