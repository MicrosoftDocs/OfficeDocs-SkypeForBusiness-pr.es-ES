---
title: Registro de entrada y liberación de la habitación en paneles Microsoft Teams
ms.author: dstrome
author: dstrome
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
description: Este artículo proporciona instrucciones sobre cómo habilitar el registro de entrada y la liberación de la sala Teams dispositivos de paneles.
ms.openlocfilehash: a1fc01b349a2189ab2f5ca09ff6b856338fbcdbb
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761282"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Registro de entrada y liberación de la habitación en paneles Microsoft Teams

Cuando el registro y la liberación de la sala están habilitados, los usuarios comprueban Teams paneles en la sala que reservaron al comienzo de la reunión. Si un usuario no realiza la protección dentro de un período determinado de tiempo después de la hora de inicio de la reunión, la sala de reunión rechaza la invitación a la reunión, envía un mensaje de cancelación al organizador de la reunión y la sala queda disponible para que otros usuarios puedan reservarla.  

## <a name="requirements"></a>Requirements 

Esta característica se puede usar en una implementación de Panel de Teams independiente. También puede emparejar paneles Teams con Salas de Teams en Android con la versión de la aplicación 1449/1.0.96.2022011305 o posterior para funcionalidades adicionales, como las notificaciones de registro.  

## <a name="enable-check-in-and-room-release"></a>Habilitar el registro de entrada y la liberación de la sala 

El registro de entrada y la liberación de la sala están desactivadas de forma predeterminada. Para activarla,  

1. En la Panel de Teams, inicie sesión con sus credenciales de administrador.  

2. Vaya a **Configuración > Configuración del dispositivo > Administración la configuración > Teams la configuración de administrador > Reuniones**.

3. Active Sala de liberación si nadie se registra.

4. Para ajustar la cantidad de tiempo que los usuarios tienen que protegerse antes de liberar el salón, vaya a **Liberar después de:** y seleccione una opción en la lista desplegable.  

Cuando Teams paneles están emparejados con una sala de Teams en Android, un usuario puede registrarse para unirse a la reunión en la sala de Teams.  

## <a name="turn-on-check-in-notifications"></a>Activar las notificaciones de registro

> [!NOTE]
> Esta característica solo está disponible actualmente en Teams paneles que están emparejados con una sala de Teams en Android. El Panel de Teams y la sala de Teams deben iniciar sesión en la misma cuenta de recursos. Consulta [Emparejar una Panel de Teams con una sala de Microsoft Teams en Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android) para obtener más información.  

Las notificaciones de registro se envían cuando una reunión continúa pasando su intervalo de tiempo reservado. Una vez que un usuario de la siguiente reunión se registra, la notificación aparecerá en la pantalla frontal de la sala en la hora de inicio de la reunión programada para permitir que los participantes de la reunión anterior sepan que su reserva ha terminado y que la gente está esperando el espacio.  

Para activar las notificaciones de registro,  

1. En la Panel de Teams, inicie sesión con sus credenciales de administrador. 

2. Vaya a **Configuración > Configuración del dispositivo > Administración la configuración > Teams la configuración de administrador > Reuniones**.

3. Vaya a **Registro** y active **Enviar notificación de registro**.

## <a name="related-topics"></a>Temas relacionados

- [Cómo usar paneles Microsoft Teams](use-teams-panels.md)

- [paneles Microsoft Teams](teams-panels.md)
