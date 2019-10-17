---
title: Script de PowerShell para probar el enrutamiento directo de las conexiones del controlador de borde de sesión
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Use este ejemplo de script de PowerShell para probar el enrutamiento directo de las conexiones de controlador de borde de sesión en Microsoft Teams.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9910ac347b5e797ad30ac65e76173ba4024a87c4
ms.sourcegitcommit: fa55f9e3690fcca36b530bd13a9eeaa44120b87c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "37547242"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script de PowerShell para probar el enrutamiento directo de las conexiones del controlador de borde de sesión

El cliente SIP Tester es un script de PowerShell de ejemplo que puede usar para probar el enrutamiento directo de las conexiones de controlador de borde de sesión (SBC) en Microsoft Teams. Este script prueba la funcionalidad básica de un tronco de protocolo de inicio de sesión (SIP) emparejado por el cliente con enrutamiento directo.

El script envía una prueba SIP al Ejecutor de pruebas, espera el resultado y, a continuación, lo presenta en un formato legible. Puede usar este script para probar los escenarios siguientes:

- Llamadas salientes y entrantes
- Llamadas simultáneas
- Escalado de elementos multimedia
- Transferencia Consultiva

## <a name="download-the-script-and-documentation"></a>Descargar la secuencia de comandos y la documentación

Descargue el [script y la documentación del cliente de prueba SIP](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).