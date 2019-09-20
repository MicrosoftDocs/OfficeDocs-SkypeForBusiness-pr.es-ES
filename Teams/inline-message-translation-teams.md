---
title: Activar la traducción de mensajes en línea en Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Descubra cómo se usa la traducción en línea en Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2eb68a06a24436b6c12e4ee5b59a24a0da92ca7e
ms.sourcegitcommit: a6e44256c024fc3953cfd6a511ee024c4c7b8408
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047087"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a>Activar la traducción de mensajes en línea en Microsoft Teams 
=================================================

La traducción de mensajes en línea es una nueva característica de Microsoft teams que permite a los usuarios traducir los mensajes de los equipos en el [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado por la configuración de Idioma personal de Office 365.

La traducción de mensajes en línea se está implantando de forma predeterminada en su organización. Si desea permitir que los usuarios usen esta característica en el cliente de Teams, debe activar esta configuración.

> [!NOTE]
>Este lanzamiento se ha excluido de los planes de Office 365 en la nube de la comunidad de administración pública de Office 365 y en entornos de Office 365 Germany.

## <a name="use-powershell-to-turn-on-inline-message-translation"></a>Usar PowerShell para activar la traducción de mensajes en línea

Puede usar la Directiva de mensajería para activar la traducción de mensajes en línea.

Active la Directiva con el cmdlet [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) . La política tarda unos minutos en aplicarse. Es posible que los usuarios tengan que cerrar sesión e iniciarla de nuevo en Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a>Usar el centro de administración de Microsoft Teams para activar la traducción de mensajes en línea

En el **centro de administración de Microsoft Teams**, seleccione **directivas de mensajería** en el navegación izquierdo y, a continuación, cree una directiva nueva o edite una existente y establezca la opción **permitir que los usuarios traduzcan mensajes** a **activado**.

> [!NOTE]
> El servicio realiza la traducción y lo entrega al cliente sin ningún efecto en el contenido capturado en los registros de cumplimiento. Para obtener más información sobre la traducción, consulte [¿Qué es Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).