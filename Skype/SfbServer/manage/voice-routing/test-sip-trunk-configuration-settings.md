---
title: Probar las opciones de configuración de tronco SIP en Skype empresarial Server
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
description: 'Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. '
ms.openlocfilehash: bed342de3f602499f16b9f27ee0726f10d2c867e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "42048193"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="6a3d7-103">Probar las opciones de configuración de tronco SIP en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6a3d7-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="6a3d7-p101">Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6a3d7-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="6a3d7-106">Si se debe habilitar el desvío de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="6a3d7-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="6a3d7-107">Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="6a3d7-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="6a3d7-108">Si se requiere o no el cifrado del protocolo de tiempo real seguro (SRTP) en cada tronco.</span><span class="sxs-lookup"><span data-stu-id="6a3d7-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="6a3d7-109">Al instalar Skype empresarial Server, se crea una colección global de opciones de configuración de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="6a3d7-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="6a3d7-110">Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).</span><span class="sxs-lookup"><span data-stu-id="6a3d7-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="6a3d7-111">Los administradores también pueden usar el cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) para comprobar que un tronco puede convertir un número como marcado por un usuario en un número que se puede controlar mediante la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="6a3d7-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="6a3d7-112">Los valores de configuración de tronco solo se pueden probar con Windows PowerShell y el cmdlet Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="6a3d7-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="6a3d7-113">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a3d7-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="6a3d7-114">**Para probar las opciones de configuración del tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="6a3d7-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="6a3d7-115">Este comando comprueba que los valores de configuración de tronco del sitio de Redmond pueden convertir correctamente el número marcado 4255551212.</span><span class="sxs-lookup"><span data-stu-id="6a3d7-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
