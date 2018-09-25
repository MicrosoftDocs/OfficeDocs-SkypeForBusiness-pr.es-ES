---
title: Usar la traducción de mensajes en línea en Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
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
ms.openlocfilehash: 9097e7421bb65b1a9ce0900df097080a6cfc2023
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016840"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Usar la traducción de mensajes en línea en Microsoft Teams 
=================================================

La traducción de mensajes en línea es una característica nueva de Microsoft Teams con la que los usuarios pueden traducir automáticamente los mensajes de Teams en el [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) que se especifique en su configuración de idioma personal de Office 365.

Traducción de mensaje en línea se van a ejecutar de forma predeterminada para la organización. Si desea permitir a los usuarios usar esta característica en el cliente de los equipos, debe activar esta opción de configuración mediante el uso de PowerShell. Actualmente, esta opción no está disponible en el Microsoft Teams y Skype para el centro de administración de negocio, pero pronto.

> [!NOTE]
>Este lanzamiento no se incluye en las suscripciones de Office 365 de nuestros entornos de Office 365 Government Community Cloud y Office 365 Germany. 

## <a name="enable-by-using-powershell"></a>Habilitar mediante PowerShell

La característica de traducción de mensajes en línea se puede activar mediante la directiva de mensajería. 

1. Active la directiva con el cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).
2. La directiva tarda unos minutos que se debe aplicar. Los usuarios podrían deben cerrar la sesión e iniciar una sesión en los equipos.

## <a name="enable-by-using-the-teams-admin-center"></a>Habilitar mediante el Centro de administración de Teams

La opción para activar la característica de traducción de mensajes en línea mediante el Centro de administración de Teams estará disponible muy pronto.

> [!NOTE]
>Traducción es estrictamente de cliente y no ha capturado ningún efecto en el contenido en los registros de cumplimiento. Para obtener más información acerca de la traducción, vea [¿Qué es Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).