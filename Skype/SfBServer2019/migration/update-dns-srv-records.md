---
title: Actualizar registros SRV de DNS
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753272"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="6ea52-103">Actualizar registros SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="6ea52-103">Update DNS SRV records</span></span>

<span data-ttu-id="6ea52-104">Para completar con éxito este procedimiento, debe iniciar sesión en el servidor o el dominio como miembro del grupo administradores del dominio o como miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="6ea52-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="6ea52-105">En este tema se describe cómo actualizar los registros del sistema de nombres de dominio (DNS) después de migrar a Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6ea52-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="6ea52-106">Una vez que todos los usuarios se han movido a Skype empresarial Server 2019, pero antes de que se retire el grupo o el director heredados, debe actualizar los registros DNS SRV en el DNS interno para cada dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="6ea52-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="6ea52-107">En este procedimiento, se presupone que el DNS interno tiene zonas para los dominios de usuarios SIP.</span><span class="sxs-lookup"><span data-stu-id="6ea52-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="6ea52-108">Para configurar un registro DNS SRV</span><span class="sxs-lookup"><span data-stu-id="6ea52-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="6ea52-109">En el servidor DNS, haga clic en **Inicio**, **Herramientas administrativas** y, a continuación, **DNS**.</span><span class="sxs-lookup"><span data-stu-id="6ea52-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="6ea52-110">En el árbol de la consola del dominio SIP, expanda **zonas de búsqueda directa**, expanda el dominio SIP en el que está instalado Skype empresarial Server 2019 y vaya a la configuración de **_tcp** .</span><span class="sxs-lookup"><span data-stu-id="6ea52-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="6ea52-111">En el panel derecho, haga clic con el botón secundario en **_sipinternaltls** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6ea52-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="6ea52-112">En **host que ofrece este servicio**, actualice el FQDN de host para que apunte al grupo de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6ea52-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="6ea52-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6ea52-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="6ea52-114">Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="6ea52-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="6ea52-115">Inicie sesión en un equipo cliente en el dominio.</span><span class="sxs-lookup"><span data-stu-id="6ea52-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="6ea52-116">Haga clic en **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="6ea52-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="6ea52-117">En el cuadro **abrir** , escriba cmd y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6ea52-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="6ea52-118">En el símbolo del sistema, escriba nslookup _\<FQDN of the Front End pool\>_ o _\<FQDN of the Standard Edition server\>_ y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="6ea52-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="6ea52-119">Compruebe que recibe una respuesta que resuelve la dirección IP adecuada para el FQDN.</span><span class="sxs-lookup"><span data-stu-id="6ea52-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

