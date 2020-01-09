---
title: Caducidad y renovación de equipos en Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre la expiración y la renovación de equipo y cómo usar la Directiva de expiración de grupo de Office 365 para limpiar automáticamente los equipos que no se usan en Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2baf466b28874794c4e9b7191be155de7187754e
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992817"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a>Caducidad y renovación de equipos en Microsoft Teams

Las organizaciones con una gran cantidad de equipos suelen tener equipos que nunca se usan realmente. Esto puede suceder por varias razones, entre las que se incluyen la experimentación de productos, la colaboración de equipos a corto plazo o los propietarios de equipos que salen de la organización. Con el tiempo, esos equipos pueden acumular y crear una carga para los recursos de inquilino.  

Para frenar el número de equipos sin usar, como administrador, puede usar la [Directiva de expiración de grupo de Office 365](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy) para limpiar automáticamente los equipos que no se usan. Debido a que los equipos están respaldados por grupos, las directivas de expiración de grupos también se aplican automáticamente a los equipos.

Al aplicar una directiva de expiración a un equipo, el propietario de un equipo recibe una notificación para la renovación de equipo 30 días, 15 días y 1 día antes de la fecha de expiración del equipo. Cuando el propietario del equipo recibe la notificación, puede hacer clic en **renovar ahora** en configuración del equipo para renovar el equipo.

![Captura de pantalla del botón renovar ahora para renovar un equipo en la configuración del equipo](media/team-expiration.png "Captura de pantalla del botón renovar ahora para renovar un equipo en la configuración del equipo")

Si el propietario del equipo no renueva el equipo, el equipo se coloca en un estado "eliminado temporalmente", lo que significa que se puede restaurar en los próximos 30 días.

## <a name="team-auto-renewal"></a>Renovación automática de equipo

Puede haber ocasiones en las que el propietario de un equipo no pueda renovar el equipo, tal vez porque se hayan olvidado de renovar o se hayan ausentado cuando venza la renovación. En estos escenarios, un equipo en uso activo puede ser eliminado a causa de las directivas de expiración que se aplican al equipo.  

Para evitar la eliminación accidental, la renovación automática se habilita automáticamente para un equipo en la Directiva de expiración del grupo. Cuando la Directiva de expiración del grupo está configurada, cualquier equipo que tenga al menos una visita de canal desde cualquier miembro del equipo antes de la fecha de expiración se renueva automáticamente sin intervención manual del propietario del equipo.

## <a name="known-issues"></a>Problemas conocidos

**La fecha de expiración del equipo y el grupo subyacente no coinciden**

Antes de renovar un equipo, primero se renueva el grupo que respalda al equipo. Como parte de la renovación, se establece una nueva fecha de caducidad en el grupo para una fecha futura. Es posible que esta nueva fecha no esté visible de forma inmediata en Teams. La sincronización puede demorar hasta 24 horas. Si ve una discrepancia entre la fecha de caducidad de un equipo y su grupo subyacente, espere 24 horas antes de buscar asistencia.
