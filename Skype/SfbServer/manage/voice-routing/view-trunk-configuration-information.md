---
title: Ver información de configuración del tronco en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios.
ms.openlocfilehash: c473c3fc19138ac91b44dff8552555418d36533f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826170"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="72758-103">Ver información de configuración del tronco en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="72758-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="72758-104">Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="72758-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="72758-105">Si se debe habilitar el desvío de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="72758-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="72758-106">Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).</span><span class="sxs-lookup"><span data-stu-id="72758-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="72758-107">Si se requiere o no el cifrado del protocolo de tiempo real seguro (SRTP) en cada tronco.</span><span class="sxs-lookup"><span data-stu-id="72758-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="72758-108">Al instalar Skype Empresarial Server, se crea automáticamente una colección global de opciones de configuración de tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="72758-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="72758-109">Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).</span><span class="sxs-lookup"><span data-stu-id="72758-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="72758-110">**Para ver la información de configuración del tronco SIP mediante el Panel de control de Skype Empresarial Server**</span><span class="sxs-lookup"><span data-stu-id="72758-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="72758-111">En el Panel de control de Skype Empresarial Server, haga clic en **Enrutamiento** de voz y, a continuación, haga clic en **Configuración del tronco.**</span><span class="sxs-lookup"><span data-stu-id="72758-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="72758-112">En la **pestaña Configuración** de tronco verá una lista de todas las colecciones de opciones de configuración de tronco; para  cada colección verá los valores de las propiedades **Name**, **Scope**, **State** y Media **bypass,** junto con el número de usos de RTC, reglas de números de llamada y reglas de número de llamadas **asociadas** a la colección. </span><span class="sxs-lookup"><span data-stu-id="72758-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="72758-113">Para ver detalles adicionales sobre una colección de opciones de configuración de tronco, haga clic en la colección de interés, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles.**</span><span class="sxs-lookup"><span data-stu-id="72758-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="72758-114">Tenga en cuenta que solo puede ver información detallada de una recopilación de opciones de configuración de tronco a la vez.</span><span class="sxs-lookup"><span data-stu-id="72758-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="72758-115">Visualización de la información de configuración del tronco SIP mediante Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="72758-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="72758-116">Las opciones de configuración del tronco SIP se pueden ver con PowerShell de Skype Empresarial Server y el cmdlet Get-CsTrunkConfiguration web.</span><span class="sxs-lookup"><span data-stu-id="72758-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="72758-117">Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="72758-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="72758-118">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype Empresarial Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en https://go.microsoft.com/fwlink/p/?linkId=255876 .</span><span class="sxs-lookup"><span data-stu-id="72758-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at https://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="72758-119">REEMPLACE O QUITE ESTE VÍNCULO.</span><span class="sxs-lookup"><span data-stu-id="72758-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="72758-120">**Para ver la información de configuración del tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="72758-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="72758-121">Para ver información sobre todas las opciones de configuración del tronco SIP, escriba el siguiente comando en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="72758-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

```powershell
Get-CsTrunkConfiguration
```

<span data-ttu-id="72758-122">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="72758-122">That will return information similar to this:</span></span>

```console
Identity                                  : Global
OutboundTranslationRulesList              : {}
SipResponseCodeTranslationRulesList       : {}
OutboundCallingNumberTranslationRulesList : {}
PstnUsages                                : {}
Description                               :
ConcentratedTopology                      : True
EnableBypass                              : False
EnableMobileTrunkSupport                  : False
EnableReferSupport                        : True
EnableSessionTimer                        : False
EnableSignalBoost                         : False
MaxEarlyDialogs                           : 20
RemovePlusFromUri                         : False
RTCPActiveCalls                           : True
RTCPCallsOnHold                           : True
SRTPMode                                  : Required
EnablePIDFLOSupport                       : False
EnableRTPLatching                         : False
EnableOnlineVoice                         : False
ForwardCallHistory                        : False
Enable3pccRefer                           : False
ForwardPAI                                : False
EnableFastFailoverTimer                   : True
```
<span data-ttu-id="72758-123">Para obtener más información, consulte el tema de ayuda del cmdlet [Get-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration)</span><span class="sxs-lookup"><span data-stu-id="72758-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



