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
description: Obtenga información sobre cómo activar la traducción en línea en Microsoft Teams mediante el centro de administración de Microsoft Teams o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395389"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Desactivar la traducción de mensajes en Microsoft Teams
=================================================

La traducción de mensajes en línea es una característica de Microsoft teams que permite a los usuarios traducir los mensajes de los equipos en el [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado por la configuración de Idioma personal.

La traducción de mensajes en línea se ha desactivado de forma predeterminada para su organización. No necesita realizar cambios si quiere permitir que los usuarios usen esta característica en el cliente de Teams.

> [!NOTE]
>Este lanzamiento se ha excluido de los planes de Office 365 en la nube de la comunidad de administración pública de Office 365 y en entornos de Office 365 Germany.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Usar PowerShell para desactivar la traducción de mensajes en línea

Puede usar la Directiva de mensajería para desactivar la traducción de mensajes en línea.

Desactive la Directiva mediante el cmdlet [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) . La política tarda unos minutos en aplicarse. Es posible que los usuarios tengan que cerrar sesión e iniciarla de nuevo en Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Usar el centro de administración de Microsoft Teams para desactivar la traducción de mensajes en línea

En el **centro de administración de Microsoft Teams**, seleccione **directivas de mensajería** en el navegación izquierdo y, a continuación, cree una directiva nueva o edite una existente y establezca la opción **traducir mensajes** como **desactivada**.

> [!NOTE]
> El servicio realiza la traducción y lo entrega al cliente sin ningún efecto en el contenido capturado en los registros de cumplimiento. Para obtener más información sobre la traducción, consulte [¿Qué es Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)
