---
title: Expansor de configuración general del servidor de mediación
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: a00573b06c1900718fd670c96a21ffab069b491e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806730"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="d4ef2-102">Expansor de configuración general del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="d4ef2-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="d4ef2-103">Configuración general</span><span class="sxs-lookup"><span data-stu-id="d4ef2-103">General settings</span></span>

<span data-ttu-id="d4ef2-p101">Nombre de dominio completo (FQDN) del servidor de mediación o el grupo de servidores de mediación. Edite el nombre de dominio completo del servidor que se va a cambiar. Debe tener un registro host (A) de DNS que coincida con el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-p101">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="d4ef2-107">En la sección **Asociaciones**, seleccione un servidor perimetral o un grupo de servidores perimetrales para asociar con el servidor de mediación o el grupo de servidores de mediación.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="d4ef2-108">Seleccione el servidor perimetral que usarán los componentes multimedia del servidor de mediación para el usuario Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="d4ef2-109">Si no tiene definido ningún servidor perimetral y necesita asociar el servidor de mediación con un servidor perimetral, haga clic en **Nuevo** y defina el nuevo servidor perimetral o el grupo de servidores perimetrales en el asistente para definir un nuevo grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="d4ef2-110">Configuración del próximo salto</span><span class="sxs-lookup"><span data-stu-id="d4ef2-110">Next hop settings</span></span>

<span data-ttu-id="d4ef2-111">Se especifica el servidor de mediación o el grupo de servidores de mediación del próximo salto seleccionando el grupo de servidores front-end Enterprise Edition o el servidor front-end Standard Edition en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="d4ef2-112">Un servidor o un grupo de servidores director no son una selección válida para el siguiente salto de un servidor de mediación o un grupo de servidores de mediación; por lo tanto, no figurarán en la lista.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="d4ef2-113">Haga **clic en** Aceptar para aceptar y guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="d4ef2-114">Haga clic en **Cancelar** para descartar los cambios y salir de la página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="d4ef2-115">Configuración de la puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="d4ef2-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="d4ef2-p104">Defina las puertas de enlace de RTC asociadas con el servidor de mediación o el grupo de servidores de mediación. Si ya ha definido puertas de enlace, estarán disponibles para asociar con el servidor de mediación. Si habilita la colocación del servidor de mediación, el puerto de escucha del servidor en los servidores del grupo debe definirse para Seguridad de la capa de transporte (TLS). De forma predeterminada, este puerto es 5067. Si selecciona **Habilitar puerto TCP**, debe definir un puerto TCP para el servidor de mediación colocado. Se trata de una configuración opcional; se recomienda consultar los requisitos de la puerta de enlace o los de la RTC para saber si realmente necesita esto. De forma predeterminada, el valor de este puerto es 5068.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-p104">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="d4ef2-p105">Los troncos asociados con el servidor de mediación colocado. Si ya ha definido troncos, se podrán asociar inmediatamente con el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="d4ef2-p106">Si tiene asociado más de un tronco con un servidor de mediación, se puede especificar un tronco predeterminado seleccionando ese tronco y haciendo clic en **Convertir en predeterminada**. Para anular la selección de una puerta de enlace como predeterminada, haga clic en **Anular como predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="d4ef2-p106">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

