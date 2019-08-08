---
title: Configurar certificados y directivas de acceso por puerta de enlace XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'La Federación XMPP define una implementación externa basada en el protocolo de presencia y mensajería extensible (XMPP). Una configuración XMPP permite a los usuarios acceder a los usuarios del dominio XMPP de la siguiente manera:'
ms.openlocfilehash: 01adcbe06718068e84844f704858e04198b197b2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239294"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="7723a-104">Configurar certificados y directivas de acceso por puerta de enlace XMPP</span><span class="sxs-lookup"><span data-stu-id="7723a-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="7723a-105">La Federación XMPP define una implementación externa basada en el protocolo de presencia y mensajería extensible (XMPP).</span><span class="sxs-lookup"><span data-stu-id="7723a-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="7723a-106">Una configuración XMPP permite a los usuarios acceder a los usuarios del dominio XMPP de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7723a-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="7723a-107">Mensajería instantánea y presencia-persona a persona solamente</span><span class="sxs-lookup"><span data-stu-id="7723a-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="7723a-108">Creación de los contactos de XMPP federado en el cliente de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="7723a-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="7723a-109">Al configurar directivas para la compatibilidad de los socios de XMPP federados, las directivas se aplican a los usuarios de XMPP Federated Domains, pero no a los usuarios de los proveedores de servicios de mensajería instantánea (mi) protocolo de inicio de sesión (mi) ni a los dominios federados de SIP.</span><span class="sxs-lookup"><span data-stu-id="7723a-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="7723a-110">Configure un socio de XMPP federado para cada dominio de XMPP federado que desee permitir a los usuarios que añadan contactos y se comuniquen con ellos.</span><span class="sxs-lookup"><span data-stu-id="7723a-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="7723a-111">Una vez que las directivas estén en vigor, tendrá que configurar los certificados de la puerta de enlace XMPP.</span><span class="sxs-lookup"><span data-stu-id="7723a-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7723a-112">La funcionalidad de XMPP es obsoleta en Skype empresarial Server 2019, pero puede continuarse en un servidor heredado en coexistencia con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7723a-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="7723a-113">Asegúrese de que ya ha implementado el servidor heredado (Skype empresarial Server 2015/Lync Server 2013) puerta de enlace XMPP y ha configurado las directivas de acceso para habilitar a los usuarios para la puerta de enlace XMPP heredada.</span><span class="sxs-lookup"><span data-stu-id="7723a-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="7723a-114">Para obtener más información, consulte migrar la [Federación XMPP](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="7723a-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="7723a-115">Configurar una directiva de acceso externo para habilitar a los usuarios para la puerta de enlace XMPP heredada</span><span class="sxs-lookup"><span data-stu-id="7723a-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="7723a-116">Abra el panel de control heredado de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7723a-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="7723a-117">En la barra de navegación izquierda, haga clic en **Federación y acceso externo**y, después, haga clic en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="7723a-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="7723a-118">Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="7723a-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="7723a-119">Escriba un nombre para la Directiva de usuario de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="7723a-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="7723a-120">Proporcione una descripción para la Directiva de usuario de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="7723a-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="7723a-121">Seleccione **Habilitar comunicaciones con usuarios federados**.</span><span class="sxs-lookup"><span data-stu-id="7723a-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="7723a-122">Seleccione **Habilitar comunicaciones con usuarios federados de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="7723a-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="7723a-123">Haga clic en **confirmar** para guardar los cambios en el sitio o en la Directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="7723a-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

