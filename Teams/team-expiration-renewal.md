---
title: Renovación y expiración del equipo en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre la expiración y renovación del equipo y cómo usar la directiva de expiración de grupos de Microsoft 365 para limpiar automáticamente los equipos sin usar en Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b111ddd6b874fef22a7d221f6eb932c4c14c7b70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809410"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Renovación y expiración del equipo en Microsoft Teams

Las organizaciones con un gran número de equipos a menudo tienen equipos que nunca se usan realmente. Esto puede suceder por varios motivos, como la experimentación de productos, la colaboración en equipo a corto plazo o la salida de los propietarios de equipos de la organización. Con el tiempo, estos equipos pueden acumular y generar una carga en los recursos de inquilino.  

Como administrador, puede usar la directiva de expiración del grupo de [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) para controlar el número de equipos sin usar. Dado que los grupos tienen copia de seguridad de los equipos, las directivas de expiración de grupo también se aplican automáticamente a los equipos.

Cuando aplica una directiva de expiración a un equipo, el propietario del equipo recibe una notificación de renovación del equipo 30 días, 15 días y 1 día antes de la fecha de expiración del equipo. Cuando el propietario del equipo reciba la notificación, puede hacer clic en Renovar **ahora** en la configuración del equipo para renovar el equipo.

![Captura de pantalla del botón Renovar ahora para renovar un equipo en la configuración del equipo](media/team-expiration.png "Captura de pantalla del botón Renovar ahora para renovar un equipo en la configuración del equipo")

Si el propietario del equipo no renueva el equipo y no hay ninguna actividad más en el equipo hasta el final de la directiva de expiración, el equipo se pone en el estado "eliminado temporalmente", lo que significa que se puede restaurar en los próximos 30 días.

## <a name="team-auto-renewal"></a>Renovación automática del equipo

Puede haber ocasiones en las que el propietario de un equipo no pueda renovar el equipo, quizás porque se olvidó de renovar o porque estaba fuera cuando hubo renovación. En estos escenarios, un equipo en uso activo puede eliminarse debido a las directivas de expiración que se aplican al equipo.  

Para evitar la eliminación accidental, la renovación automática se habilita automáticamente para un equipo en la directiva de expiración del grupo. Cuando se configura la directiva de expiración del grupo, cualquier equipo que tenga al menos una visita de canal de cualquier miembro del equipo antes de su fecha de expiración se renueva automáticamente sin la intervención manual del propietario del equipo.

## <a name="known-issues"></a>Problemas conocidos

**La fecha de expiración del equipo y el grupo subyacente no coinciden**

Antes de renovar un equipo, el grupo que lo hace se renueva en primer lugar. Como parte de la renovación, se establece una nueva fecha de vencimiento en el grupo para una fecha futura. Es posible que esta nueva fecha no se pueda ver inmediatamente en Teams. La sincronización puede tardar hasta 24 horas. Si ve una discrepancia entre la fecha de vencimiento de un equipo y su grupo subyacente, espere 24 horas antes de solicitar más soporte técnico.
