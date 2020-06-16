---
title: Configurar certificados y directivas de acceso por puerta de enlace XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7353d6bfdd4c045d9d592ababf92f2aaaec2365
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="ce037-102">Configurar certificados y directivas de acceso por puerta de enlace XMPP</span><span class="sxs-lookup"><span data-stu-id="ce037-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce037-103">_**Última modificación del tema:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="ce037-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="ce037-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span><span class="sxs-lookup"><span data-stu-id="ce037-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="ce037-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span><span class="sxs-lookup"><span data-stu-id="ce037-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="ce037-106">MI y presencia, solo persona a persona</span><span class="sxs-lookup"><span data-stu-id="ce037-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="ce037-107">Creación de contactos federados XMPP en el cliente Lync</span><span class="sxs-lookup"><span data-stu-id="ce037-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="ce037-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span><span class="sxs-lookup"><span data-stu-id="ce037-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="ce037-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span><span class="sxs-lookup"><span data-stu-id="ce037-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="ce037-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span><span class="sxs-lookup"><span data-stu-id="ce037-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce037-111">Para comenzar la migración de la puerta de enlace XMPP, debe implementar la puerta de enlace XMPP de Lync Server 2013 y configurar directivas de acceso para habilitar a los usuarios para la puerta de enlace XMPP de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce037-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="ce037-112">Es necesario mover todos los usuarios a la implementación de Lync Server 2013 antes de realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ce037-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="ce037-113">Para obtener más información, consulte <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP Gateway on Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ce037-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="ce037-114">Configurar una directiva de acceso externo para habilitar usuarios para la puerta de enlace XMPP de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce037-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="ce037-115">Abra Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="ce037-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="ce037-116">En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="ce037-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="ce037-117">Haga clic en **Nuevo** y en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="ce037-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="ce037-118">Indique un nombre para la directiva de usuario de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="ce037-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="ce037-119">Indique una descripción para la directiva de usuario de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="ce037-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="ce037-120">Seleccione **Habilitar comunicaciones con usuarios federados**.</span><span class="sxs-lookup"><span data-stu-id="ce037-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="ce037-121">Seleccione **Habilitar comunicaciones con usuarios federados de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="ce037-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="ce037-122">Haga clic en **Confirmar** para guardar los cambios en la directiva de sitio o de usuario.</span><span class="sxs-lookup"><span data-stu-id="ce037-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

