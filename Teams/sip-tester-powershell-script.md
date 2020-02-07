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
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0eca4b7c7c4708509eb33bc14e4514dc3f858980
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837960"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="ba18b-103">Script de PowerShell para probar el enrutamiento directo de las conexiones del controlador de borde de sesión</span><span class="sxs-lookup"><span data-stu-id="ba18b-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="ba18b-104">El cliente SIP Tester es un script de PowerShell de ejemplo que puede usar para probar el enrutamiento directo de las conexiones de controlador de borde de sesión (SBC) en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ba18b-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="ba18b-105">Este script prueba la funcionalidad básica de un tronco de protocolo de inicio de sesión (SIP) emparejado por el cliente con enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="ba18b-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="ba18b-106">El script envía una prueba SIP al Ejecutor de pruebas, espera el resultado y, a continuación, lo presenta en un formato legible.</span><span class="sxs-lookup"><span data-stu-id="ba18b-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="ba18b-107">Puede usar este script para probar los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="ba18b-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="ba18b-108">Llamadas salientes y entrantes</span><span class="sxs-lookup"><span data-stu-id="ba18b-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="ba18b-109">Llamadas simultáneas</span><span class="sxs-lookup"><span data-stu-id="ba18b-109">Simultaneous ring</span></span>
- <span data-ttu-id="ba18b-110">Escalado de elementos multimedia</span><span class="sxs-lookup"><span data-stu-id="ba18b-110">Media escalation</span></span>
- <span data-ttu-id="ba18b-111">Transferencia Consultiva</span><span class="sxs-lookup"><span data-stu-id="ba18b-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="ba18b-112">Descargar la secuencia de comandos y la documentación</span><span class="sxs-lookup"><span data-stu-id="ba18b-112">Download the script and documentation</span></span>

<span data-ttu-id="ba18b-113">Descargue el [script y la documentación del cliente de prueba SIP](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="ba18b-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>