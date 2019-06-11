---
title: Configurar certificados y directivas de acceso por puerta de enlace XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49733819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f93134da1f61f4036a468a6aeeffb3867c2cce89
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="a26a8-102">Configurar certificados y directivas de acceso por puerta de enlace XMPP</span><span class="sxs-lookup"><span data-stu-id="a26a8-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a26a8-103">_**Última modificación del tema:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="a26a8-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="a26a8-104">La Federación XMPP define una implementación externa basada en el protocolo de presencia y mensajería extensible (XMPP).</span><span class="sxs-lookup"><span data-stu-id="a26a8-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="a26a8-105">Una configuración XMPP permite a los usuarios de Lync acceder a los usuarios del dominio XMPP de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a26a8-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="a26a8-106">Mensajería instantánea y presencia: solo para personas</span><span class="sxs-lookup"><span data-stu-id="a26a8-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="a26a8-107">Creación de los contactos de XMPP federados en el cliente de Lync</span><span class="sxs-lookup"><span data-stu-id="a26a8-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="a26a8-108">Al configurar directivas para la compatibilidad de los socios federados protocolo de presencia y mensajería extensible (XMPP), las directivas se aplican a los usuarios de XMPP Federated Domains, pero no a los usuarios de proveedores de servicios de mensajería instantánea (mi) protocolo de inicio de sesión (SIP) (por ejemplo, Windows Live) o dominios federados de SIP.</span><span class="sxs-lookup"><span data-stu-id="a26a8-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="a26a8-109">Configure un socio de XMPP federado para cada dominio de XMPP federado que desee permitir a los usuarios que añadan contactos y se comuniquen con ellos.</span><span class="sxs-lookup"><span data-stu-id="a26a8-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="a26a8-110">Una vez que las directivas estén en vigor, tendrá que configurar los certificados de la puerta de enlace XMPP.</span><span class="sxs-lookup"><span data-stu-id="a26a8-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a26a8-111">Para comenzar la migración de la puerta de enlace XMPP, debe implementar la puerta de enlace 2013 XMPP de Lync Server y configurar directivas de acceso para habilitar usuarios para la puerta de enlace XMPP de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a26a8-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="a26a8-112">Debe mover todos los usuarios a la implementación de Lync Server 2013 antes de realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a26a8-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="a26a8-113">Para obtener más información, consulte <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">configurar la puerta de enlace XMPP en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a26a8-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="a26a8-114">Configurar una directiva de acceso externo para habilitar usuarios en la puerta de enlace de Lync Server 2013 XMPP</span><span class="sxs-lookup"><span data-stu-id="a26a8-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="a26a8-115">Abra el Panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a26a8-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="a26a8-116">En la barra de navegación izquierda, haga clic en **Federación y acceso externo**y, después, haga clic en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="a26a8-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="a26a8-117">Haga clic en **nuevo** y, a continuación, en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="a26a8-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="a26a8-118">Escriba un nombre para la Directiva de usuario de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="a26a8-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="a26a8-119">Proporcione una descripción para la Directiva de usuario de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="a26a8-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="a26a8-120">Seleccione **Habilitar comunicaciones con usuarios federados**.</span><span class="sxs-lookup"><span data-stu-id="a26a8-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="a26a8-121">Seleccione **Habilitar comunicaciones con usuarios federados de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="a26a8-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="a26a8-122">Haga clic en **confirmar** para guardar los cambios en el sitio o en la Directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="a26a8-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

