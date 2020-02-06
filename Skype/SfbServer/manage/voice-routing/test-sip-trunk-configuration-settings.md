---
title: Probar la configuración del tronco del SIP en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios. '
ms.openlocfilehash: 911947b33f0e609b4dd532ec5cc2c3d56a08618c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816940"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="4ca36-103">Probar la configuración del tronco del SIP en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4ca36-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="4ca36-104">Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="4ca36-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="4ca36-105">Estas opciones de configuración especifican:</span><span class="sxs-lookup"><span data-stu-id="4ca36-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="4ca36-106">Si se debe activar la omisión de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="4ca36-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="4ca36-107">Las condiciones en que se envían paquetes de protocolo de control de transporte (RTCP) en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="4ca36-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="4ca36-108">Si se requiere o no cifrado de protocolo en tiempo real seguro (SRTP) en cada tronco.</span><span class="sxs-lookup"><span data-stu-id="4ca36-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="4ca36-109">Al instalar Skype empresarial Server, se crea una colección global de parámetros de configuración del tronco del SIP.</span><span class="sxs-lookup"><span data-stu-id="4ca36-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="4ca36-110">Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).</span><span class="sxs-lookup"><span data-stu-id="4ca36-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="4ca36-111">Los administradores también pueden usar el cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) para comprobar que un tronco puede convertir un número como marcado por un usuario en un número que puede ser administrado por la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="4ca36-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="4ca36-112">Los valores de configuración de tronco solo se pueden probar con Windows PowerShell y el cmdlet Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="4ca36-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="4ca36-113">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ca36-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="4ca36-114">**Para probar las opciones de configuración de troncos SIP**</span><span class="sxs-lookup"><span data-stu-id="4ca36-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="4ca36-115">Este comando comprueba que los valores de configuración de tronco del sitio de Redmond pueden convertir correctamente el número marcado 4255551212.</span><span class="sxs-lookup"><span data-stu-id="4ca36-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
