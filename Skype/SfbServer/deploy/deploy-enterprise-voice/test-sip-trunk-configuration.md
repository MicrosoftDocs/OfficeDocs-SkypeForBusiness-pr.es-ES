---
title: Probar las opciones de configuración de troncos SIP en Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Resumen: Obtenga información sobre cómo probar las opciones de configuración de troncos SIP mediante el Skype para Shell de administración de servidor empresarial.'
ms.openlocfilehash: fb782ddefbf3930e5e2122724adf729ef63c05dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892282"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="32e88-103">Probar las opciones de configuración de troncos SIP en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="32e88-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="32e88-104">**Resumen:** Obtenga información sobre cómo probar las opciones de configuración de troncos SIP mediante el Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="32e88-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="32e88-p101">Las opciones de configuración de los troncos SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:</span><span class="sxs-lookup"><span data-stu-id="32e88-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="32e88-107">Si se debe activar la omisión de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="32e88-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="32e88-108">Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="32e88-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="32e88-109">Si se requiere el cifrado mediante el protocolo de transporte seguro en tiempo real (SRTP) en todos los troncos.</span><span class="sxs-lookup"><span data-stu-id="32e88-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="32e88-110">Al instalar Skype para Business Server, se crea una colección global de opciones de configuración de tronco SIP para usted.</span><span class="sxs-lookup"><span data-stu-id="32e88-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="32e88-111">Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).</span><span class="sxs-lookup"><span data-stu-id="32e88-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="32e88-112">Los administradores pueden usar también el cmdlet Test-CsTrunkConfiguration para comprobar que el tronco puede convertir un número que ha marcado el usuario en un número que la puerta de enlace puede controlar.</span><span class="sxs-lookup"><span data-stu-id="32e88-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="32e88-113">Los valores de configuración de tronco solo se pueden probar con Windows PowerShell y el cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="32e88-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="32e88-114">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="32e88-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="32e88-115">Para probar las opciones de configuración de troncos SIP</span><span class="sxs-lookup"><span data-stu-id="32e88-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="32e88-116">Este comando comprueba que los valores de configuración de tronco del sitio de Redmond pueden convertir correctamente el número marcado 4255551212.</span><span class="sxs-lookup"><span data-stu-id="32e88-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


