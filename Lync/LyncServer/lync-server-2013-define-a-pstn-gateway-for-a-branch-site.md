---
title: 'Lync Server 2013: Definir una puerta de enlace RTC para un sitio de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c253f82001fef4dd52e19dccb11e7ac77bb12417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a><span data-ttu-id="a9145-102">Definir una puerta de enlace RTC para un sitio de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9145-102">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9145-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a9145-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a9145-104">Realice este procedimiento en el sitio central, que contiene al menos un grupo de servidores front-end o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a9145-104">Perform this procedure at the central site, which contains at least one Front End pool or Standard Edition server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a9145-105">Antes de llevar a cabo el procedimiento, deben cumplirse las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a9145-105">Before you perform the procedure, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="a9145-106">El software de&nbsp;comunicaciones de Lync Server 2013 debe estar configurado en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="a9145-106">Lync Server 2013&nbsp;communications software must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="a9145-107">El servidor de mediación debe implementarse en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="a9145-107">Mediation Server must be deployed at the central site.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a><span data-ttu-id="a9145-108">Para definir una puerta de enlace RTC</span><span class="sxs-lookup"><span data-stu-id="a9145-108">To define a PSTN gateway</span></span>

1.  <span data-ttu-id="a9145-109">Haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a9145-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a9145-110">En el árbol de consola, expanda el sitio central, expanda **sitios de sucursal**, expanda el nombre del sitio de la sucursal para el que desea definir una puerta de enlace de red telefónica conmutada (RTC) y, a continuación, expanda **componentes**compartidos.</span><span class="sxs-lookup"><span data-stu-id="a9145-110">In the console tree, expand the central site, expand **Branch Office Sites**, expand name of the branch site that you want to define a public switched telephone network (PSTN) gateway for, and then expand **Shared Components**.</span></span>

3.  <span data-ttu-id="a9145-111">Haga clic con el botón secundario en **puertas de enlace RTC**y luego haga clic en **nueva puerta de enlace IP/PSTN**.</span><span class="sxs-lookup"><span data-stu-id="a9145-111">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="a9145-112">En el cuadro de diálogo **definir nueva puerta de enlace IP/RTC** , haga clic en **FQDN o dirección IP**de la puerta de enlace y, a continuación, escriba el nombre de dominio completo (FQDN) o la dirección IP de la puerta de enlace que está implementando en el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="a9145-112">In the **Define New IP/PSTN Gateway** dialog box, click **Gateway FQDN or IP Address**, and then type the fully qualified domain name (FQDN) or IP address of the gateway that you are deploying at the branch site.</span></span>

5.  <span data-ttu-id="a9145-113">Haga clic en **Puerto de escucha para la puerta de enlace IP/RTC**y, a continuación, acepte los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a9145-113">Click **Listening Port for IP/PSTN Gateway**, and then accept the default values.</span></span>

6.  <span data-ttu-id="a9145-114">En la lista **Protocolo de transporte SIP** , haga clic en el protocolo de transporte que usa la puerta de enlace y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a9145-114">In the **SIP Transport Protocol** list, click the transport protocol the gateway uses, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a9145-115">Por razones de seguridad, le recomendamos encarecidamente que use una puerta de enlace PSTN que admita la seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="a9145-115">For security reasons, we strongly recommend that you use a PSTN gateway that supports Transport Layer Security (TLS).</span></span>

    
    </div>

<div>


> [!TIP]  
> <span data-ttu-id="a9145-116">Use el cmdlet <STRONG>set-CsPstnGateway</STRONG> para modificar las propiedades de una puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="a9145-116">Use the cmdlet <STRONG>Set-CsPstnGateway</STRONG> to modify properties of a PSTN gateway.</span></span> <span data-ttu-id="a9145-117">Para obtener más información, vea <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">set-CsPstnGateway</A>en la ayuda del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a9145-117">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>, in the Lync Server Management Shell Help.</span></span>



</div>

<span data-ttu-id="a9145-118">**Paso siguiente** para la resistencia del sitio de sucursal: [configuración de usuarios para la resistencia de sitios de sucursal en Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="a9145-118">**Next step** for branch-site resiliency: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a9145-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9145-119">See Also</span></span>


[<span data-ttu-id="a9145-120">Opciones de implementación de la puerta de enlace RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9145-120">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

