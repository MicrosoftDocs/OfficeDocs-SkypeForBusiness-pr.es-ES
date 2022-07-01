---
title: Renovación y expiración del equipo en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre la expiración y renovación del equipo y cómo usar la directiva de expiración de grupos de Microsoft 365 para limpiar automáticamente los equipos que no se usan en Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1a322e07df81727c75c05ebb16c4cdabc0916a4
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564178"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Renovación y expiración del equipo en Microsoft Teams

Las organizaciones con un gran número de equipos suelen tener equipos que nunca se usan realmente. Esto puede ocurrir por varios motivos, como la experimentación de productos, la colaboración a corto plazo del equipo o el abandono por parte de los propietarios de equipos de la organización. Con el tiempo, estos equipos pueden acumularse y generar una carga en los recursos del inquilino.  

Como administrador, puede usar la [directiva de expiración de grupos de Microsoft 365](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) para limpiar automáticamente los equipos sin usar. Dado que los equipos están respaldados por grupos, las directivas de expiración de grupos también se aplican automáticamente a los equipos.

Cuando aplica una directiva de expiración a un equipo, el propietario del equipo recibe una notificación para la renovación del equipo 30 días, 15 días y 1 día antes de la fecha de expiración del equipo. Cuando el propietario del equipo recibe la notificación, puede hacer clic en **Renovar ahora** en la configuración del equipo para renovar el equipo.

![Captura de pantalla del botón Renovar ahora para renovar un equipo en la configuración del equipo.](media/team-expiration.png "Captura de pantalla del botón Renovar ahora para renovar un equipo en la configuración del equipo")

Si el propietario del equipo no renueva el equipo y no hay ninguna actividad adicional en el equipo hasta el final de la directiva de expiración, el equipo se pone en un estado "eliminado temporalmente", lo que significa que se puede restaurar en los próximos 30 días.

## <a name="team-auto-renewal"></a>Renovación automática del equipo

Puede haber ocasiones en las que el propietario del equipo no puede renovar el equipo tal vez porque olvidó renovar o estaba ausente cuando venció la renovación. En estos escenarios, un equipo que esté activo puede eliminarse debido a las directivas de expiración que se aplican al equipo.  

Para evitar la eliminación accidental, la renovación automática se habilita automáticamente para un equipo en la directiva de expiración del grupo. Cuando se configura la directiva de expiración del grupo, cualquier equipo que tenga al menos una visita de canal de cualquier miembro del equipo antes de su fecha de expiración se renueva automáticamente sin la intervención manual del propietario del equipo.

## <a name="known-issues"></a>Problemas conocidos

**La fecha de expiración del equipo y el grupo subyacente no coinciden**

Antes de renovar un equipo, el grupo que respalda el equipo se renueva primero. Como parte de la renovación, se establece una nueva fecha de expiración en el grupo para una fecha futura. Es posible que esta nueva fecha no se vea inmediatamente en Teams. La sincronización puede tardar hasta 24 horas. Si ve una discrepancia entre la fecha de expiración de un equipo y su grupo subyacente, espere 24 horas antes de buscar más soporte técnico.