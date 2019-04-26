---
title: Configurar certificados y directivas de acceso por puerta de enlace XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'La federación XMPP define una implementación externa en función de la mensajería eXtensible y el protocolo de presencia (XMPP). Una configuración de XMPP permite a los usuarios acceso a los usuarios de dominio XMPP por:'
ms.openlocfilehash: 65ef8904660eaa75ddd10238a6561ea91b9f7278
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238664"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="9f689-104">Configurar certificados y directivas de acceso por puerta de enlace XMPP</span><span class="sxs-lookup"><span data-stu-id="9f689-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="9f689-105">La federación XMPP define una implementación externa en función de la mensajería eXtensible y el protocolo de presencia (XMPP).</span><span class="sxs-lookup"><span data-stu-id="9f689-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="9f689-106">Una configuración de XMPP permite a los usuarios acceso a los usuarios de dominio XMPP por:</span><span class="sxs-lookup"><span data-stu-id="9f689-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="9f689-107">Mensajería instantánea y presencia - solo persona a persona</span><span class="sxs-lookup"><span data-stu-id="9f689-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="9f689-108">Creación de contactos federados XMPP en el Skype para clientes empresariales</span><span class="sxs-lookup"><span data-stu-id="9f689-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="9f689-109">Al configurar las directivas de soporte técnico de XMPP socios federados, las directivas se aplican a los usuarios de dominios XMPP federado, pero no a los usuarios del protocolo de inicio de sesión (SIP) de mensajería instantánea servicio (IM) de SIP o proveedores de dominios federados.</span><span class="sxs-lookup"><span data-stu-id="9f689-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="9f689-110">Configurar a un socio federado de XMPP para cada dominio federado XMPP que se desea permitir a los usuarios agregar contactos y comunicarse con.</span><span class="sxs-lookup"><span data-stu-id="9f689-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="9f689-111">Una vez que las directivas están en su lugar, debe configurar los certificados de puerta de enlace XMPP.</span><span class="sxs-lookup"><span data-stu-id="9f689-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9f689-112">Funcionalidad XMPP está en desuso en Skype para Business Server 2019, pero se puede continuar en un servidor heredado en coexistencia con Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9f689-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="9f689-113">Asegúrese de que ya ha implementado el servidor heredado (Skype para Business Server 2015 / Lync Server 2013) puerta de enlace de XMPP y configurado las directivas de acceso para permitir a los usuarios para la puerta de enlace de XMPP heredado.</span><span class="sxs-lookup"><span data-stu-id="9f689-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="9f689-114">Para obtener información detallada, vea [Migrar la federación XMPP](migrating-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="9f689-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="9f689-115">Configurar una directiva de acceso externo para habilitar usuarios para la puerta de enlace de XMPP heredado</span><span class="sxs-lookup"><span data-stu-id="9f689-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="9f689-116">Abra el Skype heredado para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="9f689-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="9f689-117">En la barra de navegación izquierda, haga clic en **federación y acceso externo**y, a continuación, haga clic en **Directiva de acceso externo**.</span><span class="sxs-lookup"><span data-stu-id="9f689-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="9f689-118">Haga clic en **Nuevo** y, luego, en **Directiva de usuario**.</span><span class="sxs-lookup"><span data-stu-id="9f689-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="9f689-119">Escriba un nombre para la directiva de usuario de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="9f689-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="9f689-120">Proporcione una descripción para la directiva de usuario de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="9f689-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="9f689-121">Seleccione **Habilitar las comunicaciones con los usuarios federados**.</span><span class="sxs-lookup"><span data-stu-id="9f689-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="9f689-122">Seleccione **habilitar comunicaciones con XMPP usuarios federados**.</span><span class="sxs-lookup"><span data-stu-id="9f689-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="9f689-123">Haga clic en **Confirmar** para guardar los cambios en la directiva de sitio o usuario.</span><span class="sxs-lookup"><span data-stu-id="9f689-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

