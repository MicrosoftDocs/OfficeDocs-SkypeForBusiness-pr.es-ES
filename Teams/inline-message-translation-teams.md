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
ms.openlocfilehash: 2afc1d0374333fdbb0bec9246d04224c6a82f032
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532705"
---
<a name="use-inline-message-translation-in-microsoft-teams"></a>Usar la traducción de mensajes en línea en Microsoft Teams 
=================================================

La traducción de mensajes en línea es una característica nueva de Microsoft Teams con la que los usuarios pueden traducir automáticamente los mensajes de Teams en el [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) que se especifique en su configuración de idioma personal de Office 365.

La traducción de mensajes en línea se está implantando de forma predeterminada en su organización. Si desea permitir a los usuarios usar esta característica en el cliente de los equipos, debe activar esta configuración.

> [!NOTE]
>Esta implantación se excluye de suscripciones a Office 365 en nuestros entornos de nube de la Comunidad de Office 365 gubernamentales y Office 365 Alemania.

## <a name="enable-by-using-powershell"></a>Habilitar mediante el uso de PowerShell

Puede activar la característica de traducción de mensaje en línea mediante el uso de la directiva de mensajería.

1. Activar la directiva mediante el cmdlet [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) .
2. La directiva tarda unos minutos que se debe aplicar. Los usuarios podrían deben cerrar la sesión e iniciar una sesión en los equipos.

## <a name="enable-by-using-the-microsoft-teams--skype-for-business-admin-center"></a>Habilitar mediante el uso de la Microsoft Teams & Skype para el centro de administración de negocio

En los **equipos de Microsoft & Skype para el centro de administración de negocio**, seleccione **Las directivas de mensajería** de la barra de la izquierda, a continuación, ya sea crear una nueva directiva o editar una directiva existente y establezca la opción de **Permitir a los usuarios para traducir los mensajes** a **en **.

> [!NOTE]
>Traducción se realiza mediante el servicio de y entrega al cliente con ningún efecto en el contenido que se capturan en los registros de cumplimiento. Para obtener más información acerca de la traducción, vea [¿Qué es Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).