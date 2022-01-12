---
title: Inscribir un Salas de Teams en el Salas de Microsoft Teams Premium administrado
author: v-smandalika
ms.author: v-smandalika
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo inscribir Salas de Microsoft Teams cuentas en Salas de Microsoft Teams Premium servicio administrado.
f1keywords: ''
ms.openlocfilehash: 79dee52cc9c814338c6c5dc4c91245155ef2fd41
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766973"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>Inscribir un dispositivo en el Salas de Microsoft Teams Premium administrado

Para inscribir un dispositivo Salas de Microsoft Teams en el servicio administrado de Salas de Teams Premium, debe asignar uno más usuarios al administrador del servicio administrado y, a continuación, completar los pasos de inscripción con ese usuario.

## <a name="assign-users-to-the-managed-service-administrator-role"></a>Asignar usuarios al rol administrador del servicio administrado

Complete los pasos siguientes para asignar usuarios al rol de administrador de servicios administrados:

1. Inicie sesión en el [portal Salas de Teams Premium](https://portal.rooms.microsoft.com/) con los mismos privilegios de administrador que el que se usó para iniciar sesión en el Centro de administración de Microsoft 365.
2. Vaya a **Configuración**  >  **Configuración**  >  **y,** a continuación, seleccione **Administrador de servicio administrado.**
3. En **Administrador de servicios administrados,** seleccione la **pestaña** Tareas y, a continuación, **seleccione Agregar**.
4. Siga al asistente para nombrar la tarea y seleccionar los usuarios que se deben agregar a ella. La tarea se aplicará a todos los grupos de salas y salas.
5. Al final del asistente para tareas, seleccione **Agregar tarea.**

Los usuarios a los que se les asigna el rol de administrador de servicio administrado son responsables de la administración diaria y la supervisión del portal de Salas de Teams Premium de servicio administrado.

Después de asignar usuarios al rol de administrador [](#enroll-a-teams-rooms-device) de servicio administrado, continúe con la sección Inscribir un dispositivo para agregar un dispositivo Salas de Teams al portal de servicio administrado.

## <a name="enroll-a-teams-rooms-device"></a>Inscribir un Salas de Teams móvil

 Para inscribir un dispositivo en el Salas de Teams Premium administrado, vea Supervisar [la instalación de software del dispositivo.](monitor-software-installation-guide.md)

<!--2. Select on the **?** icon at the top right-hand corner of the portal to launch the help menu. The help menu includes an [Installation guide](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) containing detailed enrollment instructions:

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
