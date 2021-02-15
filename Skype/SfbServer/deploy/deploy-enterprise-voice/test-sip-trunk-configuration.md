---
title: Probar las opciones de configuración del tronco SIP en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Resumen: obtenga información sobre cómo probar las opciones de configuración del tronco SIP mediante el Shell de administración de Skype Empresarial Server.'
ms.openlocfilehash: 8b3a98d54fd0d2dc8bb69e553e0c0a3a7b98b1ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830640"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="f493e-103">Probar las opciones de configuración del tronco SIP en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="f493e-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="f493e-104">**Resumen:** Obtenga información sobre cómo probar las opciones de configuración del tronco SIP mediante el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f493e-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="f493e-105">Las opciones de configuración del tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red telefónica conmutada (RTC), una central de conmutación (PBX) de IP-Public o un controlador de borde de sesión (SBC) en el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="f493e-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="f493e-106">Estos valores determinan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f493e-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="f493e-107">Si se debe habilitar el desvío de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="f493e-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="f493e-108">Condiciones en las que se envían paquetes del Protocolo de control de transporte en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="f493e-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="f493e-109">Indica si se requiere o no cifrado de Protocolo de transporte en tiempo real seguro (SRTP) en cada tronco.</span><span class="sxs-lookup"><span data-stu-id="f493e-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="f493e-110">Al instalar Skype Empresarial Server, se crea automáticamente una colección global de opciones de configuración de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="f493e-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="f493e-111">Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).</span><span class="sxs-lookup"><span data-stu-id="f493e-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="f493e-112">Los administradores pueden usar también el cmdlet Test-CsTrunkConfiguration para comprobar que el tronco puede convertir un número que ha marcado el usuario en un número que la puerta de enlace puede controlar.</span><span class="sxs-lookup"><span data-stu-id="f493e-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="f493e-113">Los valores de configuración de tronco solo se pueden probar con Windows PowerShell y el cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f493e-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="f493e-114">Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota del Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="f493e-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="f493e-115">Para probar las opciones de configuración del tronco SIP</span><span class="sxs-lookup"><span data-stu-id="f493e-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="f493e-116">Este comando comprueba que los valores de configuración de tronco del sitio de Redmond pueden convertir correctamente el número marcado 4255551212.</span><span class="sxs-lookup"><span data-stu-id="f493e-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


