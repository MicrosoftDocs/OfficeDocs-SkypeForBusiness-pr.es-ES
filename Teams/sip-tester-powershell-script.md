---
title: Script de PowerShell para probar conexiones del controlador de borde de sesión de enrutamiento directo
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Use este ejemplo de script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo en Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: acba1d06debc9a0e06ee6636e14ee5cbf15bd90f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774410"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script de PowerShell para probar conexiones del controlador de borde de sesión de enrutamiento directo

El cliente probador SIP es un script de PowerShell de ejemplo que puede usar para probar conexiones del controlador de borde de sesión de enrutamiento directo (SBC) en Microsoft Teams. Este script prueba la funcionalidad básica de un tronco del Protocolo de inicio de sesión (SIP) emparejado por el cliente con enrutamiento directo.

El script envía una prueba SIP al participante de la prueba, espera el resultado y, a continuación, lo presenta en un formato legible por el ser humano. Puede usar este script para probar los siguientes escenarios:

- Llamadas salientes y entrantes
- Anillo simultáneo
- Escalación de medios
- Transferencia consultiva

## <a name="download-the-script-and-documentation"></a>Descargar el script y la documentación

Descargue el script y la documentación del cliente de Prueba [SIP.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)

  > [!NOTE]
  > El script de cliente probador SIP solo admite adal.ps versión 3.19.8.1. Se devolverá un error si se usa una versión posterior del adal.ps.
  
  
