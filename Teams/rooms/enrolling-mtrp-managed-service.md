---
title: Inscribir un dispositivo Salas de Teams en el servicio administrado Salas de Microsoft Teams Premium
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo inscribir cuentas de Salas de Microsoft Teams en Salas de Microsoft Teams Premium servicio administrado.
f1keywords: ''
ms.openlocfilehash: f721406381e1eb99584563473196893bc21cf39b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271005"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Inscribir un dispositivo en el servicio administrado Salas de Microsoft Teams Premium

Para inscribir un dispositivo Salas de Microsoft Teams en el servicio administrado Salas de Teams Premium, debe asignar uno o varios usuarios al administrador del servicio administrado y, después, completar los pasos de inscripción con ese usuario.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Asignar usuarios al rol administrador de servicios administrados

Complete los pasos siguientes para asignar usuarios al rol administrador de servicios administrados:

1. Inicia sesión en el [portal de Salas de Teams Premium](https://portal.rooms.microsoft.com/) con los mismos privilegios de administrador que usaste para iniciar sesión en el Centro de administración de Microsoft 365.
2. Vaya a **Roles** **de configuración de configuración** >  >  y, a continuación, seleccione **Administrador de servicios administrados**.
3. En **Administrador de servicios administrados**, seleccione la pestaña **Tareas** y, a continuación, seleccione **Agregar**.
4. Siga el asistente para asignar un nombre a la tarea y seleccionar los usuarios que deben agregarse a ella. La tarea se aplicará a todos los grupos de salas y salas.
5. Al final del asistente para la tarea, seleccione **Agregar tarea**.

Los usuarios que tienen asignado el rol de administrador de servicios administrados son responsables de la administración y supervisión cotidianas del portal de servicios administrados de Salas de Teams Premium.

Después de asignar usuarios al rol Administrador de servicios administrados, vaya a [Inscribir un dispositivo Salas de Teams](enroll-a-device.md) para agregar un dispositivo Salas de Teams al portal de servicios administrados.

<!-- ## Enroll a Teams Rooms device

 To enroll a device in the Teams Rooms Premium managed service, see [Monitoring device software installation](monitor-software-installation-guide.md).

2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

    1. Review the **Pre-requisites** section in the Installation guide. Confirm that the URLs listed in the **URLs Required for Communication** list are added to your firewall's traffic allow list.
    2. Follow the instructions in the **Enabling TPM Settings** section to enable the Trusted Platform Module (TPM) functionality on your device.
    3. Follow the instructions in the **Adding Proxy Settings** section to configure your device to use your proxy gateway, if you have one.
    4. Follow the instructions in the **Process** section to install the monitoring agent software and configure the self enrollment key on your device.

3. After the monitoring agent and unique XML key are configured on your device, navigate to **Rooms** > room name > **Status**, and then select **Enroll**.

    > [!NOTE]
    > The Teams Rooms device will remain in the **Onboarding** state until a Managed Service Administrator enrolls the device using the portal.

    See [Monitoring device software installation](monitoring-software-installation-guide.md).

<!--## Link to Installation guide

The **Help** menu provides a link to the [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) which in turn provides the following information:

- Instructions on URLs that need to be allow-listed to serve to enable room telemetry to be sent to the managed service.
- Instructions for applying the Microsoft Teams Rooms Premium monitoring agent and unique XML key as part of enrolling a device in the managed service.
- Troubleshooting instructions.-->
