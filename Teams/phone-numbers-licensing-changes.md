---
title: Números de teléfono y cambios en las licencias
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ''
description: Obtenga información sobre cómo los cambios en las licencias pueden afectar a la administración de números de teléfono.
ms.openlocfilehash: 58821f950baf68474a637a8d76acaab9a088f31e
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005485"
---
# <a name="how-licensing-affects-phone-number-management"></a>Cómo afecta la licencia a la administración de números de teléfono

La forma de quitar y asignar licencias a los usuarios puede afectar a la capacidad de un usuario para realizar y recibir llamadas de red telefónica conmutada (RTC) en Microsoft Teams. En este artículo se describe cómo administrar los cambios en las licencias para asegurarse de que la capacidad de los usuarios para realizar y recibir llamadas RTC no se ve afectada.

Para obtener información general sobre la administración de números de teléfono, vea [Administrar números de teléfono para su organización](manage-phone-numbers-landing-page.md). Para obtener información general sobre las licencias de complementos de Teams, consulte [Licencias de complementos de Microsoft Teams](/teams-add-on-licensing/microsoft-teams-add-on-licensing.md).



## <a name="remove-a-license"></a>Quitar una licencia

Si tiene un usuario con un número de teléfono asignado y quita una o varias de las licencias de requisitos previos, quitar la licencia también quitará la asignación del número de teléfono del usuario. Sin un número de teléfono asignado, la capacidad del usuario para realizar y recibir llamadas RTC en Microsoft Teams se ve afectada.

Según la [opción de conectividad con RTC](pstn-connectivity.md) del usuario, quitar una licencia tiene el siguiente impacto en los parámetros de telefonía:

- **Quitar una licencia del plan de llamadas de Microsoft 365 a un usuario con un número de teléfono de plan de llamadas** hará lo siguiente:
  - Copiar cualquier valor de OnPremLineUri a LineUri
  - Establecer EnterpriseVoiceEnabled en False
  - Establecer el estado de asignación de número de teléfono en No asignado en la base de datos de números de teléfono


- **Quitar una licencia de Microsoft 365 Phone System a un usuario con un número de teléfono Operator Connect** hará lo siguiente:
  - Borrar LineUri
  - Establecer EnterpriseVoiceEnabled en False
  - Establecer el estado de la asignación del número de teléfono en No asignado en la base de datos de números de teléfono


- **Al quitar una licencia de Microsoft 365 Phone System a un usuario con un número de teléfono de Enrutamiento directo** :
  - Borrar LineUri
  - Establecer EnterpriseVoiceEnabled en False
  - Quitar el número de teléfono de la base de datos de números de teléfono


## <a name="change-a-license"></a>Cambiar una licencia

Si necesita cambiar una licencia para un usuario que implica una de las licencias de requisitos previos, debe asegurarse de que los cambios de licencia se realizan y se guardan al mismo tiempo. Este método garantiza que el usuario mantiene su número de teléfono asignado y puede seguir realizando y recibiendo llamadas RTC en Microsoft Teams. 

Por ejemplo, supongamos que desea asignar una licencia de Microsoft 365 E5 a un usuario que actualmente tiene una licencia de Microsoft 365 E3. 

- Si usa el Centro de administración de Teams, en la pestaña **Licencias y aplicaciones** de los detalles del usuario, asegúrese de que se quita la licencia anterior y se agrega la nueva licencia antes de hacer clic en **Guardar cambios**. 

- Si usa los cmdlets de PowerShell, [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) o [Set-MgUserLicense](/powershell/module/microsoft.graph.users.actions/set-mguserlicense), ejecute el cmdlet una vez y use los parámetros -AddLicenses y -RemoveLicenses.

(Si quita la licencia anterior y guarda el cambio y, a continuación, agrega la nueva licencia y guarda el cambio, el número de teléfono se desasignará y el usuario podría perder la capacidad de realizar y recibir llamadas RTC en Microsoft Teams. Después de asignar la nueva licencia, tendrá que volver a asignar el número de teléfono al usuario).










