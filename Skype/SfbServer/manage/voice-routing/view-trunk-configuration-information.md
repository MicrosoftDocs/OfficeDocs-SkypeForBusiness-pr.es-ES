---
title: Ver la información de configuración troncal en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios.
ms.openlocfilehash: dd8bd94bb8831fc3e406bed46015b2d955a2359c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274873"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="6ac88-103">Ver la información de configuración troncal en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6ac88-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="6ac88-104">Los ajustes de configuración del tronco del SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red de telefonía pública conmutada (RTC), una central de conmutación (PBX) IP o un controlador de borde de sesión (SBC) en el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="6ac88-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="6ac88-105">Si se debe activar la omisión de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="6ac88-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="6ac88-106">Las condiciones en que se envían paquetes de protocolo de control de transporte (RTCP) en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="6ac88-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="6ac88-107">Si se requiere o no cifrado de protocolo en tiempo real seguro (SRTP) en cada tronco.</span><span class="sxs-lookup"><span data-stu-id="6ac88-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="6ac88-108">Al instalar Skype empresarial Server, se crea una colección global de parámetros de configuración del tronco del SIP.</span><span class="sxs-lookup"><span data-stu-id="6ac88-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="6ac88-109">Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).</span><span class="sxs-lookup"><span data-stu-id="6ac88-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="6ac88-110">**Para ver la información de configuración del tronco de SIP mediante el panel de control de Skype empresarial Server**</span><span class="sxs-lookup"><span data-stu-id="6ac88-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="6ac88-111">En el panel de control de Skype empresarial Server, haga clic en **enrutamiento de voz**y, a continuación, en **configuración troncal**.</span><span class="sxs-lookup"><span data-stu-id="6ac88-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="6ac88-112">En la pestaña **configuración de tronco** verá una lista de todas las colecciones de parámetros de configuración de troncal; para cada colección verá los valores de las propiedades de **nombre**, **ámbito**, **Estado**y **omisión de elementos multimedia** , junto con el número de **usos de RTC**, **las reglas de números de llamadas**y **las reglas de números** asociados a las mismas. con la colección.</span><span class="sxs-lookup"><span data-stu-id="6ac88-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="6ac88-113">Para ver más detalles sobre una colección de valores de configuración del tronco, haga clic en la colección de interés, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="6ac88-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="6ac88-114">Tenga en cuenta que solo puede ver información detallada de una colección de valores de configuración de troncales a la vez.</span><span class="sxs-lookup"><span data-stu-id="6ac88-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6ac88-115">Visualización de la información de configuración del tronco de SIP mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ac88-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="6ac88-116">Los ajustes de configuración del tronco de SIP se pueden ver con Skype empresarial Server PowerShell y el cmdlet Get-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="6ac88-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="6ac88-117">Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ac88-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="6ac88-118">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server 2010 http://go.microsoft.com/fwlink/p/?linkId=255876mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="6ac88-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at http://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="6ac88-119">REEMPLAZAR O QUITAR ESTE VÍNCULO.</span><span class="sxs-lookup"><span data-stu-id="6ac88-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="6ac88-120">**Para ver la información de configuración del tronco del SIP**</span><span class="sxs-lookup"><span data-stu-id="6ac88-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="6ac88-121">Para ver la información sobre todos los ajustes de configuración del troncal SIP, escriba el siguiente comando en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="6ac88-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

`Get-CsTrunkConfiguration`

<span data-ttu-id="6ac88-122">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ac88-122">That will return information similar to this:</span></span>

```
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
<span data-ttu-id="6ac88-123">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="6ac88-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



