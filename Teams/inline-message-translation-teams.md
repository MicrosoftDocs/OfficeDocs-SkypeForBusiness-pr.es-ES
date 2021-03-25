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
description: Obtenga información sobre cómo activar la traducción en línea en Microsoft Teams con el Centro de administración de Microsoft Teams o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c9e34c5e539d32b25259098973e9bfe6795ad7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120631"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Desactivar la traducción de mensajes en línea en Microsoft Teams
=================================================

La traducción de mensajes en línea es una característica de Microsoft Teams que permite a los usuarios traducir mensajes de Teams al [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado por su configuración de idioma personal.

La traducción de mensajes en línea se ha desarrollado de forma predeterminada para su organización. No es necesario realizar cambios si desea permitir que los usuarios usen esta característica en el cliente de Teams.

> [!NOTE]
>Esta implementación se excluye de las suscripciones de Office 365 en nuestros entornos de Office 365 Government Community Cloud y Office 365 Germany.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Usar PowerShell para desactivar la traducción de mensajes en línea

Puede usar la directiva de mensajería para desactivar la traducción de mensajes en línea.

Desactive la directiva con el cmdlet [Set-CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) La directiva tarda unos minutos en aplicarse. Es posible que los usuarios deba cerrar sesión y volver a iniciar sesión en Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Usar el Centro de administración de Microsoft Teams para desactivar la traducción de mensajes en línea

En el Centro de  administración de **Microsoft Teams,** seleccione Directivas de mensajería en el panel de navegación izquierdo, cree una nueva directiva o edite una directiva existente y establezca la opción Traducir **mensajes** en **Desactivado.**

> [!NOTE]
> El servicio realiza la traducción y la entrega al cliente sin ningún efecto en el contenido capturado en los registros de cumplimiento. Para obtener más información sobre la traducción, vea [¿Qué es Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)