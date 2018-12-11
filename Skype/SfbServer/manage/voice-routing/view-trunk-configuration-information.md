---
title: Ver la información de configuración de tronco en Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Opciones de configuración de tronco SIP definen la relación y las funciones entre un servidor de mediación y la puerta de enlace de telefónica conmutada (RTC) de red, un IP-público conmutación (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios.
ms.openlocfilehash: 9d4890cd70256c6f063653a29d5d41f6e5a301cb
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222719"
---
# <a name="view-trunk-configuration-information-in-skype-for-business-server"></a><span data-ttu-id="ca676-103">Ver la información de configuración de tronco en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="ca676-103">View trunk configuration information in Skype for Business Server</span></span>

<span data-ttu-id="ca676-104">Opciones de configuración de tronco SIP definen la relación y las funciones entre un servidor de mediación y la puerta de enlace de telefónica conmutada (RTC) de red, un IP-público conmutación (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios.</span><span class="sxs-lookup"><span data-stu-id="ca676-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span>

- <span data-ttu-id="ca676-105">Si se debe activar la omisión de medios en los troncos.</span><span class="sxs-lookup"><span data-stu-id="ca676-105">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="ca676-106">Las condiciones en las que se envían los paquetes de protocolo (RTCP) de control de transporte en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="ca676-106">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="ca676-107">Si se requiere cifrado del protocolo seguro en tiempo real (SRTP) en cada tronco.</span><span class="sxs-lookup"><span data-stu-id="ca676-107">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="ca676-108">Al instalar Skype para Business Server, se crea una colección global de opciones de configuración de tronco SIP para usted.</span><span class="sxs-lookup"><span data-stu-id="ca676-108">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="ca676-109">Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC).</span><span class="sxs-lookup"><span data-stu-id="ca676-109">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="ca676-110">**Para ver información de configuración de tronco SIP mediante Skype para el Panel de Control de servidor empresarial**</span><span class="sxs-lookup"><span data-stu-id="ca676-110">**To view SIP trunk configuration information by using Skype for Business Server Control Panel**</span></span>

1. <span data-ttu-id="ca676-111">En Skype para el Panel de Control de servidor empresarial, haga clic en **Enrutamiento de voz**y, a continuación, haga clic en **Configuración del tronco**.</span><span class="sxs-lookup"><span data-stu-id="ca676-111">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="ca676-112">En la ficha **Configuración del tronco** verá una lista de las de las colecciones de opciones de configuración de tronco; para cada colección de podrá ver los valores de las propiedades **nombre**, **ámbito**, **estado**y **el desvío de medios** , junto con el número de **usos de RTC**, **las reglas de números de llamada**y **reglas de números llamados** asociado con la colección.</span><span class="sxs-lookup"><span data-stu-id="ca676-112">On the **Trunk Configuration** tab you will see a list of all your trunk configuration settings collections; for each collection you will see values for the **Name**, **Scope**, **State**, and **Media bypass** properties, along with the number of **PSTN usages**, **Calling number rules**, and **Called number rules** associated with the collection.</span></span> <span data-ttu-id="ca676-113">Para ver detalles adicionales acerca de una colección de opciones de configuración de tronco, haga clic en la colección de interés, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="ca676-113">To see additional details about a collection of trunk configuration settings, click the collection of interest, click **Edit**, and then click **Show details**.</span></span> <span data-ttu-id="ca676-114">Tenga en cuenta que puede ver información detallada solo para una colección de opciones de configuración de tronco a la vez.</span><span class="sxs-lookup"><span data-stu-id="ca676-114">Note that you can view detailed information only for one collection of trunk configuration settings at a time.</span></span>

## <a name="viewing-sip-trunk-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ca676-115">Visualización de información de configuración de tronco SIP mediante el uso de cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca676-115">Viewing SIP trunk configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ca676-116">SIP configuración del tronco configuración puede verse mediante el uso de Skype para Business Server PowerShell y el cmdlet Get-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ca676-116">SIP trunk configuration settings can be viewed by using Skype for Business Server PowerShell and the Get-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="ca676-117">Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ca676-117">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="ca676-118">Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, consulte el artículo del blog de Lync Server Windows PowerShell "Rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell" en http://go.microsoft.com/fwlink/p/?linkId=255876.</span><span class="sxs-lookup"><span data-stu-id="ca676-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at http://go.microsoft.com/fwlink/p/?linkId=255876.</span></span> <span data-ttu-id="ca676-119">REEMPLAZAR O QUITAR ESTE VÍNCULO.</span><span class="sxs-lookup"><span data-stu-id="ca676-119">REPLACE OR REMOVE THIS LINK.</span></span>


<span data-ttu-id="ca676-120">**Para ver la información de configuración de tronco SIP**</span><span class="sxs-lookup"><span data-stu-id="ca676-120">**To view SIP trunk configuration information**</span></span>

<span data-ttu-id="ca676-121">Para ver información acerca de todas las opciones de configuración del tronco SIP, escriba el siguiente comando en el Skype para Shell de administración de servidor empresarial y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="ca676-121">To view information about all your SIP trunk configuration settings, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

`Get-CsTrunkConfiguration`

<span data-ttu-id="ca676-122">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="ca676-122">That will return information similar to this:</span></span>

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
<span data-ttu-id="ca676-123">Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="ca676-123">For more information, see the help topic for the [Get-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunkConfiguration) cmdlet.</span></span>



