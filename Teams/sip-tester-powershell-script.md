---
title: Script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Use este ejemplo de script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c52febae3d734af49d1b23c7c65ceb0c2f746f7a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834280"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo

El cliente evaluador SIP es un script de PowerShell de ejemplo que puede usar para probar conexiones del controlador de borde de sesión de enrutamiento directo (SBC) en Microsoft Teams. Este script prueba la funcionalidad básica de un tronco sip (Protocolo de inicio de sesión emparejado por el cliente) con enrutamiento directo.

El script envía una prueba SIP al ejecutor de pruebas, espera el resultado y, a continuación, lo presenta en un formato legible para la persona. Puede usar este script para probar los siguientes escenarios:

- Llamadas salientes y entrantes
- Llamada simultánea
- Escalación multimedia
- Transferencia consultiva

## <a name="download-the-script-and-documentation"></a>Descargar el script y la documentación

Descargue la [documentación y el script del cliente del evaluador de SIP.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)

  > [!NOTE]
  > El script del cliente de evaluador SIP solo adal.ps versión 3.19.8.1. Se devolverá un error si se usa una versión posterior del adal.ps datos.
  
  
