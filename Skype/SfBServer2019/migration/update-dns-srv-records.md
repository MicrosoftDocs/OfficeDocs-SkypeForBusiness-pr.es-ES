---
title: Actualizar los registros DNS SRV
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Para completar correctamente este procedimiento, debe iniciar sesión en el servidor o dominio como miembro del grupo Administradores del dominio o un miembro del grupo DnsAdmins.
ms.openlocfilehash: f298db10f7030482b604734a1719756af4071ce2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027231"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="cf958-103">Actualizar los registros DNS SRV</span><span class="sxs-lookup"><span data-stu-id="cf958-103">Update DNS SRV records</span></span>

<span data-ttu-id="cf958-104">Para completar correctamente este procedimiento, debe iniciar sesión en el servidor o dominio como miembro del grupo Administradores del dominio o un miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="cf958-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="cf958-105">En este tema se describe cómo actualizar los registros del sistema de nombres de dominio (DNS) después de migrar a Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cf958-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="cf958-106">Después de que todos los usuarios se han movido a Skype para Business Server 2019, pero antes de que se retire el Director o grupo de servidores heredado, debe actualizar los registros SRV de DNS en su DNS interno para cada dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="cf958-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="cf958-107">Este procedimiento se supone que el DNS interno tiene zonas para los dominios de usuario SIP.</span><span class="sxs-lookup"><span data-stu-id="cf958-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="cf958-108">Para configurar un registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="cf958-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="cf958-109">En el servidor DNS, haga clic en **Inicio**, haga clic en **Herramientas administrativas**y, a continuación, haga clic en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="cf958-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="cf958-110">En el árbol de consola de su dominio SIP, expanda **Zonas de búsqueda directa**, expanda el dominio SIP en qué Skype para Business Server 2019 está instalado y navegue a la opción **_tcp** .</span><span class="sxs-lookup"><span data-stu-id="cf958-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="cf958-111">En el panel derecho, haga clic en **_sipinternaltls** y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cf958-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="cf958-112">En **Host que ofrece este servicio**, actualice el host FQDN para que apunte a la Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="cf958-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="cf958-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cf958-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="cf958-114">Para comprobar que se puede resolver el FQDN del servidor Standard Edition o grupo de servidores Front-End</span><span class="sxs-lookup"><span data-stu-id="cf958-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="cf958-115">Inicie sesión en un equipo cliente en el dominio.</span><span class="sxs-lookup"><span data-stu-id="cf958-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="cf958-116">Haga clic en  \*\*Inicio \*\* y en  \*\*Ejecutar \*\*.</span><span class="sxs-lookup"><span data-stu-id="cf958-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="cf958-117">En el cuadro **Abrir** , escriba cmd y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cf958-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="cf958-118">En el símbolo del sistema, escriba nslookup _ \<FQDN del grupo de servidores Front-End\> _ o _ \<FQDN del servidor Standard Edition\>_, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="cf958-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="cf958-119">Compruebe que recibe una respuesta que se resuelve en la dirección IP adecuada para el FQDN.</span><span class="sxs-lookup"><span data-stu-id="cf958-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

