---
title: Configurar certificados y directivas de acceso por puerta de enlace XMPP
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
description: 'La federación XMPP define una implementación externa basada en el Protocolo extensible de mensajería y presencia (XMPP). Una configuración XMPP permite a los usuarios acceder a los usuarios del dominio XMPP de la siguiente manera:'
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753940"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="0a807-104">Configurar certificados y directivas de acceso por puerta de enlace XMPP</span><span class="sxs-lookup"><span data-stu-id="0a807-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="0a807-105">La federación XMPP define una implementación externa basada en el Protocolo extensible de mensajería y presencia (XMPP).</span><span class="sxs-lookup"><span data-stu-id="0a807-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="0a807-106">Una configuración XMPP permite a los usuarios acceder a los usuarios del dominio XMPP de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0a807-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="0a807-107">MI y presencia-persona solo para la persona</span><span class="sxs-lookup"><span data-stu-id="0a807-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="0a807-108">Creación de contactos federados XMPP en el cliente de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="0a807-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="0a807-109">Al configurar directivas para la compatibilidad con socios federados de XMPP, las directivas se aplican a los usuarios de dominios federados XMPP, pero no a los usuarios de los proveedores de servicios de mensajería instantánea (mi) del Protocolo de inicio de sesión (mi) ni a los dominios federados SIP.</span><span class="sxs-lookup"><span data-stu-id="0a807-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="0a807-110">Configure un socio federado XMPP para cada dominio federado de XMPP en el que desee permitir que los usuarios agreguen contactos y se comuniquen con ellos.</span><span class="sxs-lookup"><span data-stu-id="0a807-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="0a807-111">Una vez aplicadas las directivas, debe configurar los certificados de puerta de enlace XMPP.</span><span class="sxs-lookup"><span data-stu-id="0a807-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0a807-112">La funcionalidad XMPP está en desuso en Skype empresarial Server 2019, pero puede continuarse en un servidor heredado en coexistencia con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0a807-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="0a807-113">Asegúrese de que ya ha implementado la puerta de enlace XMPP del servidor heredado (Skype empresarial Server 2015/Lync Server 2013) y de que ha configurado las directivas de acceso para habilitar a los usuarios para la puerta de enlace XMPP heredada.</span><span class="sxs-lookup"><span data-stu-id="0a807-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="0a807-114">Para obtener más información, consulte [migrar la Federación XMPP](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="0a807-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="0a807-115">Configurar una directiva de acceso externo para habilitar a los usuarios para la puerta de enlace XMPP heredada</span><span class="sxs-lookup"><span data-stu-id="0a807-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="0a807-116">Abra el panel de control de Skype empresarial Server heredado.</span><span class="sxs-lookup"><span data-stu-id="0a807-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="0a807-117">En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="0a807-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="0a807-118">Haga clic en **Nuevo** y después en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="0a807-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="0a807-119">Indique un nombre para la directiva de usuario de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="0a807-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="0a807-120">Indique una descripción para la directiva de usuario de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="0a807-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="0a807-121">Seleccione **Habilitar comunicaciones con usuarios federados**.</span><span class="sxs-lookup"><span data-stu-id="0a807-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="0a807-122">Seleccione **Habilitar comunicaciones con usuarios federados de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="0a807-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="0a807-123">Haga clic en **Confirmar** para guardar los cambios en la directiva de sitio o de usuario.</span><span class="sxs-lookup"><span data-stu-id="0a807-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

