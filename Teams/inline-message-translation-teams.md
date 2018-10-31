---
title: Usar la traducción de mensajes en línea en Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Descubra cómo se usa la traducción en línea en Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69c6e8046b185cc8dbc85ac0c99dc5b4cfa6fe2a
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851571"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Usar la traducción de mensajes en línea en Microsoft Teams 
=================================================

La traducción de mensajes en línea es una característica nueva de Microsoft Teams con la que los usuarios pueden traducir automáticamente los mensajes de Teams en el [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) que se especifique en su configuración de idioma personal de Office 365.

La traducción de mensajes en línea se está implantando de forma predeterminada en su organización. Si quiere que los usuarios puedan usarla dentro del cliente de Teams, debe activar esta opción mediante PowerShell. En este momento, la opción no está disponible en el Centro de administración de Skype Empresarial y Microsoft Teams, pero lo estará muy pronto.

> [!NOTE]
>Este lanzamiento no se incluye en las suscripciones de Office 365 de nuestros entornos de Office 365 Government Community Cloud y Office 365 Germany. 

## <a name="enable-by-using-powershell"></a>Habilitar mediante PowerShell

La característica de traducción de mensajes en línea se puede activar mediante la directiva de mensajería. 

1. Active la directiva con el cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).
2. La directiva tardará unos minutos en aplicarse. Es posible que los usuarios tengan que cerrar la sesión y volver a iniciarla en Teams.

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a>Habilitar mediante el uso de la Microsoft Teams & Skype para el centro de administración de negocio

La opción para activar la característica de traducción de mensaje en línea usando el Microsoft Teams & Skype para el centro de administración de negocio es muy pronto.

> [!NOTE]
>La traducción se produce únicamente en el cliente y no afecta al contenido que se captura en los registros de cumplimiento normativo. Para obtener más información sobre la traducción, consulte [¿Qué es Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).