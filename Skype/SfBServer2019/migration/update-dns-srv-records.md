---
title: Actualizar registros SRV de DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.
ms.openlocfilehash: ef77f491efd090949ff5dd6b653dd3cd6ea1cde7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812778"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="d6d92-103">Actualizar registros SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="d6d92-103">Update DNS SRV records</span></span>

<span data-ttu-id="d6d92-104">Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio como miembro del grupo administradores de dominio o miembro del grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="d6d92-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="d6d92-105">En este tema se describe cómo actualizar los registros del sistema de nombres de dominio (DNS) después de migrar a Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d6d92-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="d6d92-106">Después de que todos los usuarios se hayan movido a Skype empresarial Server 2019, pero antes de que el grupo o el director heredado se haya decomisado, debe actualizar los registros SRV de DNS en el DNS interno para cada dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="d6d92-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="d6d92-107">En este procedimiento se supone que su DNS interno tiene zonas para sus dominios de usuario SIP.</span><span class="sxs-lookup"><span data-stu-id="d6d92-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="d6d92-108">Para configurar un registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="d6d92-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="d6d92-109">En el servidor DNS, haga clic en **Inicio**, haga clic en **herramientas administrativas**y, a continuación, haga clic en **DNS**.</span><span class="sxs-lookup"><span data-stu-id="d6d92-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="d6d92-110">En el árbol de consola de su dominio SIP, expanda **zonas de búsqueda directa**, expanda el dominio SIP en el que está instalado Skype empresarial Server 2019 y vaya a la configuración de **_tcp** .</span><span class="sxs-lookup"><span data-stu-id="d6d92-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="d6d92-111">En el panel derecho, haga clic con el botón derecho en **_sipinternaltls** y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d6d92-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="d6d92-112">En **host que ofrece este servicio**, actualice el FQDN del host para que apunte al grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="d6d92-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="d6d92-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d6d92-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="d6d92-114">Para comprobar que se puede resolver el FQDN del grupo de servidores front-end o del servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d6d92-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="d6d92-115">Inicie sesión en un equipo cliente del dominio.</span><span class="sxs-lookup"><span data-stu-id="d6d92-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="d6d92-116">Haga clic en  \*\*Inicio \*\* y en  \*\*Ejecutar \*\*.</span><span class="sxs-lookup"><span data-stu-id="d6d92-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="d6d92-117">En el cuadro **abrir** , escriba cmd y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d6d92-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="d6d92-118">En el símbolo del sistema, escriba nslookup _ \<FQDN del grupo\> de servidores front-end_ o _ \<FQDN del servidor\>Standard Edition_y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="d6d92-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="d6d92-119">Compruebe que recibe una respuesta que se resuelve en la dirección IP adecuada para el nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="d6d92-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

