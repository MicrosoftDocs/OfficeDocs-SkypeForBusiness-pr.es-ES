---
title: Script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: 215edfed535352004c960182bd649721131aedb0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564138"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo

El cliente del evaluador de SIP es un script de PowerShell de ejemplo que puede usar para probar las conexiones del controlador de borde de sesión de enrutamiento directo (SBC) en Microsoft Teams. Este script prueba la funcionalidad básica de un tronco SIP (Protocolo de inicio de sesión) emparejado con el cliente con enrutamiento directo.

El script envía una prueba SIP al ejecutor de la prueba, espera el resultado y, a continuación, lo presenta en un formato legible para el usuario. Puede usar este script para probar los siguientes escenarios:

- Llamadas salientes y entrantes
- Llamada simultánea
- Escalación de medios
- Transferencia consultiva

## <a name="download-the-script-and-documentation"></a>Descargar el script y la documentación

Descarga la [documentación y el script del cliente del probador SIP](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).

  > [!NOTE]
  > El script de cliente del probador SIP solo admite adal.ps versión 3.19.8.1. Se devolverá un error si se usa una versión posterior del adal.ps.
  
  
