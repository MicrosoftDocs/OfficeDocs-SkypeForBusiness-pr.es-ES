---
title: Comprobar la federación y el acceso remoto de usuarios externos
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de trasladar la ruta de federación para el Skype para servidor perimetral de Business Server 2019, debe realizar algunas pruebas funcionales para comprobar que la federación funciona del modo esperado. Las pruebas para el acceso de usuarios externos deben incluir cada tipo de usuario externo que admita su organización, incluidos cualquiera o todas las opciones siguientes.
ms.openlocfilehash: ce0e2dd6ee7d4fb605f844d7dfb26b3f9d13bf14
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027238"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="b0259-104">Comprobar la federación y el acceso remoto de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="b0259-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="b0259-105">Después de trasladar la ruta de federación para el Skype para servidor perimetral de Business Server 2019, debe realizar algunas pruebas funcionales para comprobar que la federación funciona del modo esperado.</span><span class="sxs-lookup"><span data-stu-id="b0259-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="b0259-106">Las pruebas para el acceso de usuarios externos deben incluir cada tipo de usuario externo que admita su organización, incluidos cualquiera o todas las opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="b0259-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="b0259-107">Probar la conectividad de los usuarios externos y acceso externo</span><span class="sxs-lookup"><span data-stu-id="b0259-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="b0259-108">Instalación de los usuarios al menos un dominio federado, un usuario interno de Skype para Business Server 2019 y un usuario en el heredado.</span><span class="sxs-lookup"><span data-stu-id="b0259-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="b0259-109">Probar la mensajería instantánea (IM), presencia, audio y vídeo (A / V) y uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="b0259-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="b0259-110">Los usuarios de cada proveedor de servicios de mensajería instantánea pública que admita su organización (y para la que se ha completado el aprovisionamiento) comunicarse con un usuario de Skype para Business Server 2019 y un usuario de la instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="b0259-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="b0259-111">Compruebe que los usuarios anónimos se pueden unir a las conferencias.</span><span class="sxs-lookup"><span data-stu-id="b0259-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="b0259-112">Un usuario hospedado en el heredado instalar con acceso de usuarios remotos (registro i nPara Lync Server/Skype para la empresa desde fuera de la intranet, pero sin VPN) con un usuario de Skype para Business Server 2019 y un usuario en la instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="b0259-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="b0259-113">Mensajería instantánea, presencia, de prueba de un uso compartido V y escritorio.</span><span class="sxs-lookup"><span data-stu-id="b0259-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="b0259-114">Un usuario hospedado en Skype para Business Server 2019 con acceso de usuarios remotos (inicio de sesión en Skype para Business Server 2019 desde fuera de la intranet, pero sin VPN) con un usuario de Skype para Business Server 2019 y un usuario de la instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="b0259-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="b0259-115">Mensajería instantánea, presencia, de prueba de un uso compartido V y escritorio.</span><span class="sxs-lookup"><span data-stu-id="b0259-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

