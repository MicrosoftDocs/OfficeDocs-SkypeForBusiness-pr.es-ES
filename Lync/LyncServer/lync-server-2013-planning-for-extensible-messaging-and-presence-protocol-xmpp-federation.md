---
title: Planeación de la Federación de protocolo extensible de mensajería y presencia (XMPP)
description: Planeación de la Federación de protocolo extensible de mensajería y presencia (XMPP).
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
ms.openlocfilehash: 511273b69181334821f446bcc4424641367ecf51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562806"
---
# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="f96e4-103">Planeación de la Federación de protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f96e4-103">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f96e4-104">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f96e4-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f96e4-105">Las versiones anteriores de Lync Server y Office Communications Server proporcionaban una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP) que se podía implementar como una función de servidor independiente para permitir la Federación con las implementaciones de XMPP.</span><span class="sxs-lookup"><span data-stu-id="f96e4-105">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="f96e4-106">En Microsoft Lync Server 2013, la funcionalidad de XMPP puede implementarse como una característica.</span><span class="sxs-lookup"><span data-stu-id="f96e4-106">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="f96e4-107">La funcionalidad XMPP se instala en dos partes: un proxy XMPP que se ejecuta en el servidor perimetral y la puerta de enlace XMPP que se ejecuta en los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="f96e4-107">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="f96e4-108">La implementación y la configuración de XMPP se trata en [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) planea admitir XMPP en su organización mediante la definición de reglas de puerto y protocolo en el firewall, la configuración de certificados y la adición de registros DNS.</span><span class="sxs-lookup"><span data-stu-id="f96e4-108">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="f96e4-109">En los siguientes temas de esta sección se resume la información necesaria para planear correctamente la Federación XMPP para la implementación.</span><span class="sxs-lookup"><span data-stu-id="f96e4-109">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="f96e4-110">La capacidad XMPP de Lync Server 2013 se ha probado y es compatible con Microsoft para la Federación de mensajería instantánea con Google Talk.</span><span class="sxs-lookup"><span data-stu-id="f96e4-110">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="f96e4-111">Para cualquier otro sistema XMPP, póngase en contacto con el proveedor de terceros para comprobar que admiten la Federación con Lync Server 2013 y para cualquier recomendación sobre implementación o solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="f96e4-111">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f96e4-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f96e4-112">In This Section</span></span>

  - [<span data-ttu-id="f96e4-113">Resumen de certificado-Federación del protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f96e4-113">Certificate summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="f96e4-114">Resumen de puertos-Federación del protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f96e4-114">Port summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [<span data-ttu-id="f96e4-115">Resumen de DNS-Federación del protocolo extensible de mensajería y presencia (XMPP) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f96e4-115">DNS summary - Extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</span></span>](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f96e4-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f96e4-116">See Also</span></span>


[<span data-ttu-id="f96e4-117">Configuración de la Federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f96e4-117">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="f96e4-118">Configurar directivas para controlar el acceso de usuarios federados de XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f96e4-118">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[<span data-ttu-id="f96e4-119">Administrar socios federados XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f96e4-119">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
<span data-ttu-id="f96e4-120">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f96e4-120">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))</span></span>  
<span data-ttu-id="f96e4-121">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f96e4-121">[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))</span></span>  
<span data-ttu-id="f96e4-122">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="f96e4-122">[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

