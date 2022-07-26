---
title: Registros y seguimiento del explorador para Teams
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.date: 06/21/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Obtenga más información sobre los registros de Explorador y WebRTC producidos por Microsoft Teams, dónde se pueden encontrar, cómo recopilar registros con Soporte técnico de Microsoft y cómo pueden ayudar con la supervisión y la solución de problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9592091d97ad4fb34f02e906888757f0c7ab14ec
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005484"
---
# <a name="browser-logs-and-tracing-for-teams"></a>Registros y seguimiento del explorador para Teams

Para algunas categorías de errores, Soporte técnico de Microsoft puede requerir que recopile un seguimiento del explorador. Esta información puede proporcionar detalles importantes sobre el estado del cliente de Teams cuando se produce el error. En este artículo se describe cómo recopilar registros webRTC y de explorador para Teams.

## <a name="browser-logs"></a>Registros del explorador

Antes de iniciar el seguimiento del explorador, asegúrese de que ha iniciado sesión en Teams. Es importante hacerlo antes de iniciar el seguimiento para que no contenga información de inicio de sesión confidencial.

Después de iniciar sesión, seleccione uno de los siguientes vínculos, según corresponda para su explorador, y siga los pasos proporcionados. 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Perimetral](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> En los pasos, reemplace todas las referencias a la Azure Portal con el cliente de Teams.
  
## <a name="webrtc-logs-in-browsers"></a>Registros WebRTC en exploradores

Los registros WebRTC pueden ayudar a Soporte técnico de Microsoft proporcionando detalles de conexión para llamadas de audio y vídeo. Sigue los pasos para acceder a los registros webRTC en Edge (Chromium) o Chrome:
  
1. Abre una pestaña nueva y ve a una de las siguientes direcciones URL:
    - Edge (Chromium):`edge://webrtc-internals/`
    - Cromo: `chrome://webrtc-internals/`
  
2. Abra la aplicación web de Teams y reproduzca el problema.
  
3. Volver a la pestaña a la que se obtuvo acceso en el paso 1 y verá al menos dos pestañas:
    - Solicitudes getUserMedia
    - `https://teams.microsoft.com/url`

4. Elija la pestaña con el nombre de la aplicación Teams y guarde el contenido de la página.

## <a name="related-topics"></a>Temas relacionados

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)

[Configurar archivos de registro para supervisar y solucionar problemas en Teams](/MicrosoftTeams/log-files)
