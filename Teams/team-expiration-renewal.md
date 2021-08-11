---
title: Expiración y renovación del equipo en Microsoft Teams
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
description: Obtenga información sobre la expiración y renovación del equipo y cómo usar Microsoft 365 directiva de expiración de grupo para limpiar automáticamente los equipos sin usar en Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b2b6b346e9ffed5a9f4d3e6b03519db2f716b3ed584e0fccdfcbcfd3326d32c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339408"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Expiración y renovación del equipo en Microsoft Teams

Las organizaciones con un gran número de equipos a menudo tienen equipos que nunca se usan realmente. Esto puede ocurrir debido a varios motivos, como la experimentación de productos, la colaboración de equipo a corto plazo o la salida de los propietarios de equipos de la organización. Con el tiempo, estos equipos pueden acumular y crear una carga para los recursos del inquilino.  

Para reducir el número de equipos sin usar, [](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) como administrador, puede usar la directiva de expiración de Microsoft 365 grupo para limpiar automáticamente los equipos sin usar. Dado que los grupos tienen una copia de seguridad de los equipos, las directivas de expiración del grupo también se aplican automáticamente a los equipos.

Cuando aplica una directiva de expiración a un equipo, el propietario del equipo recibe una notificación para la renovación del equipo 30 días, 15 días y 1 día antes de la fecha de expiración del equipo. Cuando el propietario del equipo reciba la notificación, puede hacer clic en Renovar **ahora** en la configuración del equipo para renovar el equipo.

![Captura de pantalla del botón Renovar ahora para renovar un equipo en la configuración del equipo](media/team-expiration.png "Captura de pantalla del botón Renovar ahora para renovar un equipo en la configuración del equipo")

Si el propietario del equipo no renueva el equipo y no hay más actividad en el equipo hasta el final de la directiva de expiración, el equipo se pone en estado "eliminado temporalmente", lo que significa que se puede restaurar en los próximos 30 días.

## <a name="team-auto-renewal"></a>Renovación automática del equipo

Puede haber ocasiones en las que el propietario de un equipo no pueda renovar el equipo tal vez porque olvidó renovarlo o porque estaba fuera cuando vence la renovación. En estos escenarios, un equipo en uso activo puede eliminarse debido a las directivas de expiración que se aplican al equipo.  

Para evitar la eliminación accidental, la renovación automática se habilita automáticamente para un equipo de la directiva de expiración del grupo. Cuando se configura la directiva de expiración del grupo, cualquier equipo que tenga al menos una visita de canal de cualquier miembro del equipo antes de su fecha de expiración se renueva automáticamente sin la intervención manual del propietario del equipo.

## <a name="known-issues"></a>Problemas conocidos

**La fecha de expiración del equipo y el grupo subyacente no coinciden**

Antes de renovar un equipo, el grupo que lo hace se renueva primero. Como parte de la renovación, se establece una nueva fecha de expiración en el grupo para una fecha futura. Es posible que esta nueva fecha no se pueda ver inmediatamente en Teams. La sincronización puede tardar hasta 24 horas. Si ve una discrepancia entre la fecha de expiración de un equipo y su grupo subyacente, espere 24 horas antes de buscar más soporte técnico.