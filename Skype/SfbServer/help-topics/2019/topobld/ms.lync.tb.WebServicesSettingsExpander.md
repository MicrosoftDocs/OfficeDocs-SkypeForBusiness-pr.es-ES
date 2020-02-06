---
title: Expansor de configuración de servicios web
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: Desde el generador de topología, puede modificar la configuración de puerto que se usa para los servicios Web internos y externos. Además, y si va a implementar el equilibrio de carga del sistema de nombres de dominio (DNS), puede usar el generador de topología para configurar el nombre de dominio completo (FQDN) del grupo que se resuelve en las direcciones IP físicas de todos los servidores de ese grupo.
ms.openlocfilehash: e2460305199d1d626e44e5476adc6baf618ebe89
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795231"
---
# <a name="web-services-settings-expander"></a><span data-ttu-id="7767a-104">Expansor de configuración de servicios web</span><span class="sxs-lookup"><span data-stu-id="7767a-104">Web Services Settings Expander</span></span>
 
<span data-ttu-id="7767a-105">Desde el generador de topología, puede modificar la configuración de puerto que se usa para los servicios Web internos y externos.</span><span class="sxs-lookup"><span data-stu-id="7767a-105">From within Topology Builder, you can modify the port settings used for both your internal and external web services.</span></span> <span data-ttu-id="7767a-106">Además, y si va a implementar el equilibrio de carga del sistema de nombres de dominio (DNS), puede usar el generador de topología para configurar el nombre de dominio completo (FQDN) del grupo que se resuelve en las direcciones IP físicas de todos los servidores de ese grupo.</span><span class="sxs-lookup"><span data-stu-id="7767a-106">In addition, and if you are deploying Domain Name System (DNS) load balancing, you can use Topology Builder to configure the fully qualified domain name (FQDN) of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span>
  
### <a name="editing-web-services-settings"></a><span data-ttu-id="7767a-107">Edición de la configuración de los servicios web</span><span class="sxs-lookup"><span data-stu-id="7767a-107">Editing Web Services Settings</span></span>

1. <span data-ttu-id="7767a-108">Seleccione el servidor front-end Standard Edition o grupo de servidores front-end Enterprise Edition adecuado y, luego, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7767a-108">Select the appropriate Standard Edition Front End Server or the appropriate Enterprise Edition Front End Pool, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="7767a-109">En el cuadro de diálogo **Editar propiedades**, haga clic en la pestaña **Servicios web**.</span><span class="sxs-lookup"><span data-stu-id="7767a-109">In the **Edit Properties** dialog box, click the **Web services** tab.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="7767a-110">Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único.</span><span class="sxs-lookup"><span data-stu-id="7767a-110">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="7767a-111">Por ejemplo, si define el FQDN de los servicios web externos de un servidor front-end como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="7767a-111">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="7767a-112">Si también va a implementar directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro grupo de directores o directores, así como de cualquier grupo de servidores front-end o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="7767a-112">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="7767a-113">Si decide omitir los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="7767a-113">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
3. <span data-ttu-id="7767a-114">Si edita las propiedades de un grupo Enterprise Edition, tiene la opción de seleccionar **FQDN de reemplazo**.</span><span class="sxs-lookup"><span data-stu-id="7767a-114">If you are editing the properties of an Enterprise Edition pool, you have the option to select **Override FQDN**.</span></span> <span data-ttu-id="7767a-115">Esta opción se tendría que seleccionar solamente si usa el equilibrio de carga de Sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="7767a-115">This option should be selected only if you are using Domain Name System (DNS) load balancing.</span></span> <span data-ttu-id="7767a-116">Si usa el equilibrio de carga de DNS, seleccione **FQDN de reemplazo** y, luego, en el cuadro de texto, escriba el FQDN del grupo que se resuelve en las direcciones IP físicas de todos los servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="7767a-116">If you are using DNS load balancing, select **Override FQDN** and then, in the text box, type the FQDN of the pool that resolves to the physical IP addresses of all the servers in that pool.</span></span> <span data-ttu-id="7767a-117">Si no usa el equilibrio de carga de DNS y no selecciona **FQDN de reemplazo**, no podrá cambiar el FQDN de los servicios web internos.</span><span class="sxs-lookup"><span data-stu-id="7767a-117">If you are not using DNS load balancing, and if you do not select **Override FQDN**, you cannot change the Internal web services FQDN.</span></span> <span data-ttu-id="7767a-118">El FQDN de los servicios Web internos es la dirección URL que usan los usuarios internos para conectarse a Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7767a-118">The Internal web services FQDN is the URL used by internal users to connect to Skype for Business Server.</span></span>
    
4. <span data-ttu-id="7767a-p105">De manera opcional, especifique valores nuevos de HTTP, HTTPS o HTTP y HTTPS para los **Puertos de escucha** y los **Puertos publicados**. Los puertos de escucha son los puertos que usan Internet Information Services (IIS) para escuchar el tráfico entrante del Protocolo de inicio de sesión (SIP), mientras que los puertos publicados son los puertos configurados en un equilibrador de carga o servidor proxy inverso, y también se usan para escuchar el tráfico SIP entrante. De forma predeterminada, tanto el puerto de escucha HTTP como el puerto publicado HTTP están definidos en el puerto 80, mientras que los puertos HTTPS correspondientes se establecen ambos en 443. El valor predeterminado de los dos puertos publicados HTTP es 8080 y los puertos HTTPS correspondientes, en 4443.</span><span class="sxs-lookup"><span data-stu-id="7767a-p105">Optionally, enter new HTTP, HTTPS, or HTTP and HTTPS values for the **Listening ports** and the **Published ports**. Listening ports are the ports used by Internet Information Services (IIS) to listen for incoming Session Initiation Protocol (SIP) traffic; published ports are ports configured on a load balancer or reverse proxy server and are also used to listen for incoming SIP traffic. By default, both the HTTP listening port and the HTTP published port are set to port 80; the corresponding HTTPS ports are both set to 443. The default value for the two HTTP published ports is 8080 and the corresponding HTTPS ports are set to 4443.</span></span>
    
5. <span data-ttu-id="7767a-123">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7767a-123">Click **OK**.</span></span>
    
<span data-ttu-id="7767a-124">Si modifica el FQDN interno o cualquiera de los ajustes del puerto de escucha, necesitará restablecer la configuración local en todos los servidores del grupo para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="7767a-124">If you modify either the internal FQDN or any of the listening port assignments, you must local setup again on all the servers in the pool in order to have those changes take effect.</span></span>
  

