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
description: Obtenga información sobre cómo activar la traducción directa en Microsoft Teams mediante el Centro de administración de Microsoft Teams o PowerShell.
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
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Desactivar la traducción de mensajes en línea en Microsoft Teams
=================================================

La traducción de mensajes en línea es una característica [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) de Microsoft Teams que permite a los usuarios traducir mensajes de Teams al idioma especificado por su configuración de idioma personal.

La traducción de los mensajes en línea se ofrece de forma predeterminada para su organización. No es necesario realizar cambios si desea permitir que los usuarios usen esta característica en el cliente de Teams.

> [!NOTE]
>Esta implementación se excluye de las suscripciones de Office 365 en nuestros entornos de Nube de la comunidad de la administración pública de Office 365 y Office 365 Germany.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Usar PowerShell para desactivar la traducción de mensajes en línea

Puede usar la directiva de mensajería para desactivar la traducción de mensajes en línea.

Desactive la directiva mediante el cmdlet [Set-CsTeamsMessagingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) La directiva tarda unos minutos en aplicarse. Es posible que los usuarios necesiten cerrar sesión y volver a iniciar sesión en Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Usar el Centro de administración de Microsoft Teams para desactivar la traducción de mensajes en línea

En el Centro de  administración de **Microsoft Teams,** seleccione Directivas de mensajería en el panel  de navegación izquierdo, cree una directiva o edite una directiva existente y establezca la opción Traducir mensajes en **Desactivado.**

> [!NOTE]
> El servicio realiza la traducción y lo entrega al cliente sin ningún efecto en el contenido capturado en los registros de cumplimiento. Para obtener más información sobre la traducción, vea [¿Qué es Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)
