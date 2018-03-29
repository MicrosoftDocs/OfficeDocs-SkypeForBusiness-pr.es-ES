---
title: Ampliador de configuración General del servidor de mediación de Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Editar las propiedades de los servidores de mediación en este cuadro de diálogo. En el lado izquierdo es un conjunto de vínculos rápidos para pasar a la configuración de opciones generales, ajustes de salto siguiente y configuración de puerta de enlace PSTN. En cada sección son los siguientes valores:'
ms.openlocfilehash: bc5016c9dbeb6b0693444f930c9883b1736258d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="ac12e-105">Ampliador de configuración General del servidor de mediación de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="ac12e-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="ac12e-106">Editar las propiedades de los servidores de mediación en este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ac12e-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="ac12e-107">En el lado izquierdo es un conjunto de vínculos rápidos para pasar a la configuración de opciones generales, ajustes de salto siguiente y configuración de puerta de enlace PSTN.</span><span class="sxs-lookup"><span data-stu-id="ac12e-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="ac12e-108">En cada sección son los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ac12e-108">In each section are the following settings:</span></span>
  
 <span data-ttu-id="ac12e-109">**General**:</span><span class="sxs-lookup"><span data-stu-id="ac12e-109">**General**:</span></span>
  
- <span data-ttu-id="ac12e-110">**FQDN**: editar el nombre de dominio completo del servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="ac12e-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>
    
- <span data-ttu-id="ac12e-111">**Asociaciones**: Active la casilla de verificación de **grupo de asociar borde (para componentes de medios)** y seleccione un servidor perimetral o grupo de borde para el servidor de mediación para utilizar como la ruta de acceso de medios de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="ac12e-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>
    
 <span data-ttu-id="ac12e-112">**Próximo salto**:</span><span class="sxs-lookup"><span data-stu-id="ac12e-112">**Next hop**:</span></span>
  
- <span data-ttu-id="ac12e-113">**Selección de salto siguiente**: seleccionar de una lista que utilice como la ruta de acceso para el servidor de mediación a utilizar para la comunicación con la implementación, el grupo de servidor Front-End o Front-End.</span><span class="sxs-lookup"><span data-stu-id="ac12e-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>
    
 <span data-ttu-id="ac12e-114">**Puerta de enlace PSTN**:</span><span class="sxs-lookup"><span data-stu-id="ac12e-114">**PSTN gateway**:</span></span>
  
 <span data-ttu-id="ac12e-115">**Puerta de enlace PSTN del servidor de mediación**:</span><span class="sxs-lookup"><span data-stu-id="ac12e-115">**Mediation Server PSTN gateway**:</span></span>
  
- <span data-ttu-id="ac12e-116">**Puertos de escucha**: definir los puertos de escucha en el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="ac12e-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="ac12e-117">Puede definir un puerto para la seguridad de la capa de transporte o **TLS** o **TCP**, o protocolo de control de transporte.</span><span class="sxs-lookup"><span data-stu-id="ac12e-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="ac12e-118">Para la entrada de puerto para TCP esté disponible, debe seleccionar la casilla de verificación para **Habilitar el puerto TCP**.</span><span class="sxs-lookup"><span data-stu-id="ac12e-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="ac12e-119">Consulte la configuración de configuración y documentación de la puerta de enlace de telefónica pública conmutada (PSTN) de red para determinar si necesita habilitar y definir los valores de puerto TLS, TCP o ambos.</span><span class="sxs-lookup"><span data-stu-id="ac12e-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="ac12e-120">TLS es un protocolo más seguro, el uso de certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace PSTN.</span><span class="sxs-lookup"><span data-stu-id="ac12e-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="ac12e-121">No todas las puertas de enlace PSTN compatible con TLS.</span><span class="sxs-lookup"><span data-stu-id="ac12e-121">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="ac12e-122">Se muestra una lista de los troncos SIP y las puertas de enlace que se definen y configurados para su implementación.</span><span class="sxs-lookup"><span data-stu-id="ac12e-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="ac12e-123">Si no hay entradas están presentes, no hay ningún SIP troncos o puertas de enlace PSTN configurados para su implementación.</span><span class="sxs-lookup"><span data-stu-id="ac12e-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="ac12e-124">Definir y configurar los troncos y puertas de enlace en **Componentes compartidos** en el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="ac12e-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ac12e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac12e-125">See also</span></span>

#### 

[<span data-ttu-id="ac12e-126">Información general acerca de SIP Trunking</span><span class="sxs-lookup"><span data-stu-id="ac12e-126">Overview of SIP Trunking</span></span>](http://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)
  
[<span data-ttu-id="ac12e-127">Opciones de implementación de puerta de enlace PSTN</span><span class="sxs-lookup"><span data-stu-id="ac12e-127">PSTN Gateway Deployment Options</span></span>](http://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)

