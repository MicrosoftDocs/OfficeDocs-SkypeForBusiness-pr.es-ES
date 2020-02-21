---
title: Configurar las directivas y los certificados de acceso a puertas de enlace XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49733819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742c85d60d3f0bdab7beb67858bf2a804c15bcce
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="4e6b3-102">Configurar las directivas y los certificados de acceso a puertas de enlace XMPP</span><span class="sxs-lookup"><span data-stu-id="4e6b3-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e6b3-103">_**Última modificación del tema:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="4e6b3-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="4e6b3-p101">La federación XMPP define una implementación externa basada en el Protocolo extensible de mensajería y presencia (XMPP). Una configuración XMPP permite a los usuarios de Lync obtener acceso a los usuarios de dominio XMPP mediante:</span><span class="sxs-lookup"><span data-stu-id="4e6b3-p101">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="4e6b3-106">MI y presencia, solo persona a persona</span><span class="sxs-lookup"><span data-stu-id="4e6b3-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="4e6b3-107">Creación de contactos federados XMPP en el cliente Lync</span><span class="sxs-lookup"><span data-stu-id="4e6b3-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="4e6b3-p102">Cuando se configuran directivas para admitir socios federados del protocolo extensible de mensajería y presencia (XMPP), las directivas se aplican a los usuarios de los dominios federados de XMPP, pero no a los usuarios de los proveedores de servicio de mensajería instantánea (MI) del protocolo de inicio de sesión (SIP) (por ejemplo, Windows Live) o dominios federados de SIP. Se debe configurar un socio federado de XMPP para cada dominio federado de XMPP al que desea permitir que los usuarios agreguen contactos y con el que desea que se comuniquen. Una vez aplicadas las directivas, debe configurar los certificados de puerta de enlace XMPP.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-p102">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4e6b3-111">Para comenzar la migración de la puerta de enlace XMPP, debe implementar la puerta de enlace XMPP de Lync Server 2013 y configurar directivas de acceso para habilitar a los usuarios para la puerta de enlace XMPP de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="4e6b3-112">Es necesario mover todos los usuarios a la implementación de Lync Server 2013 antes de realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="4e6b3-113">Para obtener más información, consulte <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">Configure XMPP Gateway on Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="4e6b3-114">Configurar una directiva de acceso externo para habilitar usuarios para la puerta de enlace XMPP de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e6b3-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="4e6b3-115">Abra Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="4e6b3-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="4e6b3-116">En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="4e6b3-117">Haga clic en **Nuevo** y en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="4e6b3-118">Indique un nombre para la directiva de usuario de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="4e6b3-119">Indique una descripción para la directiva de usuario de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="4e6b3-120">Seleccione **Habilitar comunicaciones con usuarios federados**.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="4e6b3-121">Seleccione **Habilitar comunicaciones con usuarios federados de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="4e6b3-122">Haga clic en **Confirmar** para guardar los cambios en la directiva de sitio o de usuario.</span><span class="sxs-lookup"><span data-stu-id="4e6b3-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

