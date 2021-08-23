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
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo inscribir Salas de Microsoft Teams cuentas en Salas de Microsoft Teams Premium servicio administrado.
f1keywords: ''
ms.openlocfilehash: 6ac3a9752fcb285c663e05939ae31b2e60a8a1e6
ms.sourcegitcommit: 3ebf9c5d27263b7e92163f1a61844a5367a4744f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2021
ms.locfileid: "58449046"
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

Complete los pasos siguientes para inscribir un dispositivo en el Salas de Teams Premium administrado:

1. Inicie sesión en [el portal de Salas de Teams Premium](https://portal.rooms.microsoft.com/) con un usuario al que se le ha asignado el rol administrador del servicio administrado.
2. Seleccione en **el botón ?** en la esquina superior derecha del portal para iniciar el menú de ayuda. El menú de ayuda incluye una [guía de instalación](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) que contiene instrucciones de inscripción detalladas:

    1. Revise la **sección Requisitos previos** en la guía de instalación. Confirme que las direcciones URL enumeradas en la lista **Direcciones URL** necesarias para la comunicación se agregan a la lista de permitidos de tráfico del firewall.
    2. Siga las instrucciones de la sección **Habilitar tpm Configuración** habilitar la funcionalidad del módulo de plataforma de confianza (TPM) en el dispositivo.
    3. Siga las instrucciones de la **sección Agregar Configuración** proxy para configurar el dispositivo para que use la puerta de enlace proxy, si tiene una.
    4. Siga las instrucciones de la **sección Proceso** para instalar el software del agente de supervisión y configurar la clave de autoinscripción en el dispositivo.

3. Después de configurar el agente de supervisión y la clave XML única en el dispositivo, vaya a Salas **>** nombre del salón > **Estado** y, a continuación, seleccione **Inscribir**.

    > [!NOTE]
    > El Salas de Teams permanecerá en el  estado de incorporación hasta que un administrador de servicio administrado inscriba el dispositivo con el portal.

## <a name="link-to-installation-guide"></a>Vínculo a guía de instalación

El **menú** Ayuda proporciona un vínculo a la [guía de instalación que,](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) a su vez, proporciona la siguiente información:

- Instrucciones sobre las direcciones URL que deben aparecer en la lista de permitidos para permitir que se envíe telemetría de salón al servicio administrado.
- Instrucciones para aplicar el agente Salas de Microsoft Teams Premium supervisión y la clave XML única como parte de la inscripción de un dispositivo en el servicio administrado.
- Instrucciones de solución de problemas.
