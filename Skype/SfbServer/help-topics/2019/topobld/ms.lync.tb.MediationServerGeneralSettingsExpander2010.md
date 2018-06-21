---
title: Expansor de configuración General del servidor de mediación para Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Para editar las propiedades de los servidores de mediación en este cuadro de diálogo. En el lado izquierdo es un conjunto de vínculos rápidos para pasar a la configuración para la configuración General, la configuración de próximo salto y la configuración de puerta de enlace de RTC. En cada sección son las siguientes opciones:'
ms.openlocfilehash: 39e9f57efd695c7bb90386dddc3f106106bb867e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2018
ms.locfileid: "19990978"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="ad290-105">Expansor de configuración General del servidor de mediación para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="ad290-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="ad290-106">Para editar las propiedades de los servidores de mediación en este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ad290-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="ad290-107">En el lado izquierdo es un conjunto de vínculos rápidos para pasar a la configuración para la configuración General, la configuración de próximo salto y la configuración de puerta de enlace de RTC.</span><span class="sxs-lookup"><span data-stu-id="ad290-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="ad290-108">En cada sección son las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="ad290-108">In each section are the following settings:</span></span>
  
 <span data-ttu-id="ad290-109">**General**:</span><span class="sxs-lookup"><span data-stu-id="ad290-109">**General**:</span></span>
  
- <span data-ttu-id="ad290-110">**FQDN**: edite el nombre de dominio completo del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="ad290-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>
    
- <span data-ttu-id="ad290-111">**Asociaciones**: Active la casilla de verificación de **grupo de servidores perimetrales asociados (para componentes multimedia)** y seleccione un servidor perimetral o grupo de servidores perimetrales para el servidor de mediación para usarlo como la ruta de acceso de medios para el acceso externo.</span><span class="sxs-lookup"><span data-stu-id="ad290-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>
    
 <span data-ttu-id="ad290-112">**Próximo salto**:</span><span class="sxs-lookup"><span data-stu-id="ad290-112">**Next hop**:</span></span>
  
- <span data-ttu-id="ad290-113">**Selección de próximo salto**: seleccione en la lista el grupo de servidores Front-End o de servidor Front-End para usarlo como la ruta de acceso para el servidor de mediación que se usará para comunicarse con su implementación.</span><span class="sxs-lookup"><span data-stu-id="ad290-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>
    
 <span data-ttu-id="ad290-114">**Puerta de enlace RTC**:</span><span class="sxs-lookup"><span data-stu-id="ad290-114">**PSTN gateway**:</span></span>
  
 <span data-ttu-id="ad290-115">**Puerta de enlace RTC del servidor de mediación**:</span><span class="sxs-lookup"><span data-stu-id="ad290-115">**Mediation Server PSTN gateway**:</span></span>
  
- <span data-ttu-id="ad290-116">**Puertos de escucha**: definir los puertos de escucha en el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="ad290-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="ad290-117">Puede definir un puerto para la seguridad de la capa de transporte o de **TLS** o **TCP**, o protocolo de control de transporte.</span><span class="sxs-lookup"><span data-stu-id="ad290-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="ad290-118">Para el puerto de entrada para TCP para que esté disponible, debe seleccionar la casilla de verificación para **Habilitar el puerto TCP**.</span><span class="sxs-lookup"><span data-stu-id="ad290-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ad290-119">Hacer referencia a la configuración de documentación y la configuración de la puerta de enlace de telefónica conmutada (RTC) para determinar si necesita habilitar y definir valores de puerto TLS, TCP o ambos.</span><span class="sxs-lookup"><span data-stu-id="ad290-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="ad290-120">TLS es un protocolo más seguro, uso de certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace de RTC.</span><span class="sxs-lookup"><span data-stu-id="ad290-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="ad290-121">No todas las puertas de enlace de RTC admiten TLS.</span><span class="sxs-lookup"><span data-stu-id="ad290-121">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="ad290-122">Aparece una lista de enlaces troncales SIP y las puertas de enlace que se definen y configurados para su implementación.</span><span class="sxs-lookup"><span data-stu-id="ad290-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="ad290-123">Si no hay entradas están presentes, no hay ningún troncos SIP o puertas de enlace RTC configurados para su implementación.</span><span class="sxs-lookup"><span data-stu-id="ad290-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="ad290-124">Definir y configurar troncos y las puertas de enlace en **Componentes compartidos** en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="ad290-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ad290-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad290-125">See also</span></span>

[<span data-ttu-id="ad290-126">Información general sobre el enlace troncal SIP</span><span class="sxs-lookup"><span data-stu-id="ad290-126">Overview of SIP Trunking</span></span>](http://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)
  
[<span data-ttu-id="ad290-127">Opciones de implementación de puerta de enlace de RTC</span><span class="sxs-lookup"><span data-stu-id="ad290-127">PSTN Gateway Deployment Options</span></span>](http://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)