---
title: Administrar los correos electrónicos de actividad procesables
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo habilitar y deshabilitar los correos electrónicos de actividad accionables de las conversaciones de Microsoft Teams
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: de1bd12a0f079154a37156e3a01c3e5791bef10c
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198512"
---
# <a name="manage-actionable-activity-emails"></a>Administrar los correos electrónicos de actividad procesables

Los correos electrónicos de actividad accionables están habilitados de forma predeterminada y notifican a los usuarios de su organización las conversaciones perdidas en Microsoft Teams.

Un correo electrónico de actividad perdida muestra las respuestas más recientes a una conversación, incluidos los mensajes enviados después del mensaje perdido. Esta característica permite a los usuarios responder directamente desde Outlook seleccionando **Responder**.

## <a name="disable-actionability-in-missed-activity-emails"></a>Deshabilitar la capacidad de acción en correos electrónicos de actividad perdida

Aunque esta característica está configurada para habilitarse de forma predeterminada, puede desactivar la capacidad de acción en los correos electrónicos de actividad en toda la organización mediante la ejecución del siguiente comando:

```Powershell
Set-OrganizationConfig -SmtpActionableMessagesEnabled $false
```

Una vez deshabilitada la característica, la opción **Responder** se reemplaza por **Responder en Teams** para que los correos electrónicos de actividad perdida ya no se consideren accionables. Los usuarios ya no podrán responder directamente desde Outlook y se les dirigirá para continuar la conversación en Teams.

> [!NOTE]
> Esta característica no es compatible con Outlook para Mac ni con algunas versiones anteriores de Outlook para Windows. Para obtener más información, vea [Mensajes accionables en Outlook y grupos de Office 365](/outlook/actionable-messages/).

## <a name="related-topics"></a>Temas relacionados

[Responder a correos electrónicos de actividad perdida desde Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381).

[Mensajes accionables en Outlook y grupos de Office 365](/outlook/actionable-messages/).
