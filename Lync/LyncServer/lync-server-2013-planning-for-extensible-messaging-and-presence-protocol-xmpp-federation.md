---
title: Planeación de la Federación de protocolo extensible de mensajería y presencia (XMPP)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4308bd09d571c41349ed9362affa220cf9723e3a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526537"
---
# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="9cfea-102">Planeación de la Federación de protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cfea-102">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cfea-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="9cfea-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="9cfea-104">Las versiones anteriores de Lync Server y Office Communications Server proporcionaban una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP) que se podía implementar como una función de servidor independiente para permitir la Federación con las implementaciones de XMPP.</span><span class="sxs-lookup"><span data-stu-id="9cfea-104">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="9cfea-105">En Microsoft Lync Server 2013, la funcionalidad de XMPP puede implementarse como una característica.</span><span class="sxs-lookup"><span data-stu-id="9cfea-105">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="9cfea-106">La funcionalidad XMPP se instala en dos partes: un proxy XMPP que se ejecuta en el servidor perimetral y la puerta de enlace XMPP que se ejecuta en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="9cfea-106">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="9cfea-107">La implementación y la configuración de XMPP se trata en [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) planea admitir XMPP en su organización mediante la definición de reglas de puerto y protocolo en el firewall, la configuración de certificados y la adición de registros DNS.</span><span class="sxs-lookup"><span data-stu-id="9cfea-107">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="9cfea-108">En los siguientes temas de esta sección se resume la información necesaria para planear correctamente la Federación XMPP para la implementación.</span><span class="sxs-lookup"><span data-stu-id="9cfea-108">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="9cfea-109">La capacidad XMPP de Lync Server 2013 se ha probado y es compatible con Microsoft para la Federación de mensajería instantánea con Google Talk.</span><span class="sxs-lookup"><span data-stu-id="9cfea-109">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="9cfea-110">Para cualquier otro sistema XMPP, póngase en contacto con el proveedor de terceros para comprobar que admiten la Federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="9cfea-110">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9cfea-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9cfea-111">In This Section</span></span>

  - [<span data-ttu-id="9cfea-112">Resumen de certificado-Federación del protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cfea-112">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="9cfea-113">Resumen de puertos-Federación del protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cfea-113">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="9cfea-114">Resumen de DNS-Federación del protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cfea-114">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9cfea-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9cfea-115">See Also</span></span>


[<span data-ttu-id="9cfea-116">Configuración de la Federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cfea-116">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="9cfea-117">Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cfea-117">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[<span data-ttu-id="9cfea-118">Administrar socios federados XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cfea-118">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
<span data-ttu-id="9cfea-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9cfea-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>  
<span data-ttu-id="9cfea-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9cfea-120">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>  
<span data-ttu-id="9cfea-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="9cfea-121">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

