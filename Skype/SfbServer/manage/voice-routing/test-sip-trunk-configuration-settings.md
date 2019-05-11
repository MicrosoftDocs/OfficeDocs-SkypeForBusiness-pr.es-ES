---
title: Probar las opciones de configuración de troncos SIP en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Opciones de configuración de tronco SIP definen la relación y las funciones entre un servidor de mediación y la puerta de enlace de telefónica conmutada (RTC) de red, un IP-público conmutación (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. '
ms.openlocfilehash: 1caf96e9979936c8fb9ff61d9b28b613fb09ce7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902267"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="37a5b-103">Probar las opciones de configuración de troncos SIP en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="37a5b-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="37a5b-104">Opciones de configuración de tronco SIP definen la relación y las funciones entre un servidor de mediación y la puerta de enlace de telefónica conmutada (RTC) de red, un IP-público conmutación (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="37a5b-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="37a5b-105">Estas opciones de configuración especifican:</span><span class="sxs-lookup"><span data-stu-id="37a5b-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="37a5b-106">Si se debe activar la omisión de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="37a5b-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="37a5b-107">Las condiciones en las que se envían los paquetes de protocolo (RTCP) de control de transporte en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="37a5b-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="37a5b-108">Si se requiere cifrado del protocolo seguro en tiempo real (SRTP) en cada tronco.</span><span class="sxs-lookup"><span data-stu-id="37a5b-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="37a5b-109">Al instalar Skype para Business Server, se crea una colección global de opciones de configuración de tronco SIP para usted.</span><span class="sxs-lookup"><span data-stu-id="37a5b-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="37a5b-110">Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).</span><span class="sxs-lookup"><span data-stu-id="37a5b-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="37a5b-111">Los administradores también pueden usar el cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) para comprobar que un tronco puede convertir a un número como marcados por un usuario a un número que se puede controlar mediante la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="37a5b-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="37a5b-112">Los valores de configuración de tronco solo se pueden probar con Windows PowerShell y el cmdlet Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="37a5b-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="37a5b-113">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37a5b-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="37a5b-114">**Para probar las opciones de configuración de troncos SIP**</span><span class="sxs-lookup"><span data-stu-id="37a5b-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="37a5b-115">Este comando comprueba que los valores de configuración de tronco del sitio de Redmond pueden convertir correctamente el número marcado 4255551212.</span><span class="sxs-lookup"><span data-stu-id="37a5b-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
