---
title: Usar la traducción de mensaje en línea en Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/16/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar la traducción en línea de Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 191fe1e5517fdce9aba6fd17e084c866df200e82
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882911"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Usar la traducción de mensaje en línea en Microsoft Teams 
=================================================

Traducción de mensaje en línea es una característica nueva de Microsoft Teams que permite a los usuarios traducir automáticamente los mensajes de los equipos en el [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado por su configuración personal de idioma para Office 365.

Traducción de mensaje en línea se van a ejecutar de forma predeterminada para la organización. Si desea permitir a los usuarios usar esta característica en el cliente de los equipos, debe activar esta opción de configuración mediante el uso de PowerShell. Actualmente, esta opción no está disponible en el Microsoft Teams y Skype para el centro de administración de negocio, pero pronto.

> [!NOTE]
>Esta implantación se excluye de suscripciones a Office 365 en nuestros entornos de nube de la Comunidad de Office 365 gubernamentales y Office 365 Alemania. 

## <a name="enable-by-using-powershell"></a>Habilitar mediante el uso de PowerShell

Puede activar la característica de traducción de mensaje en línea mediante el uso de la directiva de mensajería. 

1. Activar la directiva mediante el cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .
2. La directiva tarda unos minutos que se debe aplicar. Los usuarios podrían deben cerrar la sesión e iniciar una sesión en los equipos.

## <a name="enable-by-using-the-teams-admin-center"></a>Habilitar mediante el centro de administración de equipos

La opción para activar la característica de traducción de mensaje en línea mediante el centro de administración de equipos es muy pronto.

> [!NOTE]
>Traducción es estrictamente de cliente y no ha capturado ningún efecto en el contenido en los registros de cumplimiento. Para obtener más información acerca de la traducción, vea [¿Qué es Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).