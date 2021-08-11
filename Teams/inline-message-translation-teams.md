---
title: Activar la traducción de mensajes en línea
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo activar la traducción en línea en Microsoft Teams con el centro Microsoft Teams de administración o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 719f97e72f099edb4d14c22ef9d5a3de0f787ea7411f42f1d777ea842bcc4e27
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54339648"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Desactivar la traducción de mensajes en línea en Microsoft Teams

La traducción de mensajes en línea es una Microsoft Teams que permite a los usuarios traducir Teams mensajes al [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado por su configuración de idioma personal.

La traducción de mensajes en línea se ha desarrollado de forma predeterminada para su organización. No es necesario realizar cambios si desea permitir que los usuarios usen esta característica en el Teams cliente.

> [!NOTE]
>Esta implementación se excluye de Office 365 en nuestros Office 365 Administración Pública Community cloud y Office 365 entornos de Alemania.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Usar PowerShell para desactivar la traducción de mensajes en línea

Puede usar la directiva de mensajería para desactivar la traducción de mensajes en línea.

Desactive la directiva con el cmdlet [Set-CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) La directiva tarda unos minutos en aplicarse. Es posible que los usuarios deba cerrar sesión y volver a iniciar sesión en Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Use el Microsoft Teams de administración para desactivar la traducción de mensajes en línea

En el centro de administración  **de Microsoft Teams**, seleccione Directivas de mensajería en el panel de  navegación izquierdo, cree una directiva nueva o edite una directiva existente y establezca la opción Traducir mensajes en **Desactivado.**

> [!NOTE]
> El servicio realiza la traducción y la entrega al cliente sin ningún efecto en el contenido capturado en los registros de cumplimiento. Para obtener más información sobre la traducción, vea [¿Qué Traductor de Microsoft?](/azure/cognitive-services/translator/translator-info-overview)