---
title: Compartir llamadas y atender llamadas grupales en Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Uso compartido de llamadas y respuesta de llamadas en grupo permite a los usuarios compartir las llamadas entrantes con compañeros de trabajo para que las llamadas se pueden capturar cuando el usuario no está disponible.
ms.openlocfilehash: df98dd4df064b23b687ddcc569e6c5a431137527
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "30351333"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a>Compartir llamadas y atender llamadas grupales en Microsoft Teams

El uso compartido de llamada y el grupo de llamadas pickup características de recurso compartido de permiten a los usuarios de Microsoft Teams sus las llamadas entrantes con compañeros de trabajo para que los compañeros pueden responder a las llamadas que se producen mientras el usuario no está disponible.

Respuesta de llamadas en grupo es menos problemática para los destinatarios que otras formas de llamada de uso compartido (por ejemplo, el desvío de llamadas o las llamadas simultáneas) debido a que los usuarios pueden configurar la forma en que deseen recibir una notificación de una llamada entrante compartida (a través de notificación de audio y vídeo, solo, visual pancarta o en la aplicación de los equipos), y pueden decidir si se debe responder a la llamada.

Para compartir las llamadas con otros usuarios, un usuario crea un grupo de llamada y agrega a los usuarios que desean compartir sus llamadas con. A continuación, que elija una llamada simultánea o reenvían configuración. Para obtener información detallada, vea [llamar anillo desvío y simultánea en los equipos](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .

> [!IMPORTANT]
> Los usuarios, el propietario del grupo de llamada y los miembros del grupo de llamada deben estar en modo de implementación sólo los equipos. Para obtener más detalles sobre los modos de implementación de los equipos, vea [Descripción de los equipos de Microsoft y Skype para la interoperabilidad y coexistencia de negocio](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Se requiere una licencia

Los usuarios deben ser Enterprise Voice está habilitado para configurar y uso compartido de llamada y respuesta de llamadas de grupo. Para obtener más información sobre el modelo de licencias, vea [licencias de Office 365 para equipos de Microsoft](office-365-licensing.md).

## <a name="configure-group-call-pickup"></a>Configurar respuesta de llamadas en grupo

Para configurar la respuesta de llamadas en grupo, un usuario en primer lugar configura un grupo de llamada (Esto no es lo mismo como un grupo de seguridad o un grupo de Office 365) y, a continuación, agrega los usuarios que desean compartir sus llamadas con. A continuación, se elige una llamada simultánea o configuración de reenvío de llamadas. Para obtener más información y procedimientos paso a paso, vea [llamada anillo desvío y simultánea en los equipos](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).

Llamar a la creación del grupo y notificación preferencias son las características de controlado por el usuario; no es necesario que los administradores configurar estas características para sus usuarios. No se puede crear grupos de llamada de grupos de seguridad o grupos de Office 365; se deben crear en los equipos.

Los administradores deben habilitar grupos de llamada a través de la configuración de **TeamsCallingPolicy AllowCallGroups** para un usuario. Los administradores pueden controlar sólo si este usuario puede configurar los grupos de la llamada. Una vez que está establecido el bit a los administradores es true, no puede evitar que el usuario de configuración y la adición de los usuarios del grupo de llamada de su elección.

## <a name="limitations"></a>Limitaciones

Un inquilino puede contener un máximo de grupos de llamada 32.768. Puede haber un máximo de 5 usuarios en cada grupo de llamada. 

## <a name="more-information"></a>Más información

[Desvío de llamadas y la llamada simultánea en los equipos](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)