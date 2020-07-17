---
title: Comprobar la federación y el acceso remoto de usuarios externos
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
description: Después de realizar la transición de la ruta de Federación al servidor perimetral de Skype empresarial Server 2019, debe realizar algunas pruebas funcionales para comprobar que la Federación funciona como se esperaba. Las comprobaciones de acceso de usuarios externos deben abarcar todos los tipos de usuario externo que la organización admita, incluido todos o cualquiera de los indicados a continuación.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751672"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="75441-104">Comprobar la federación y el acceso remoto de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="75441-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="75441-105">Después de realizar la transición de la ruta de Federación al servidor perimetral de Skype empresarial Server 2019, debe realizar algunas pruebas funcionales para comprobar que la Federación funciona como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="75441-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="75441-106">Las comprobaciones de acceso de usuarios externos deben abarcar todos los tipos de usuario externo que la organización admita, incluido todos o cualquiera de los indicados a continuación.</span><span class="sxs-lookup"><span data-stu-id="75441-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="75441-107">Probar la conectividad de los usuarios externos y el acceso externo</span><span class="sxs-lookup"><span data-stu-id="75441-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="75441-108">Usuarios de al menos un dominio federado, un usuario interno en Skype empresarial Server 2019 y un usuario de la instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="75441-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="75441-109">Compruebe la mensajería instantánea (MI), la presencia, el audio/vídeo (A/V) y el uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="75441-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="75441-110">Usuarios de cada proveedor de servicios de mensajería instantánea pública que su organización admita (y para los que se haya completado el aprovisionamiento) que se comuniquen con un usuario de Skype empresarial Server 2019 y un usuario de la instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="75441-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="75441-111">Compruebe que los usuarios anónimos pueden unirse a conferencias.</span><span class="sxs-lookup"><span data-stu-id="75441-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="75441-112">Un usuario hospedado en la instalación heredada con acceso de usuarios remotos (registro i nPara Lync Server/Skype empresarial desde fuera de la intranet pero sin VPN) con un usuario en Skype empresarial Server 2019 y un usuario en la instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="75441-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="75441-113">Compruebe la mensajería instantánea, la presencia, A/V y el uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="75441-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="75441-114">Un usuario hospedado en Skype empresarial Server 2019 con acceso de usuarios remotos (inicio de sesión en Skype empresarial Server 2019 desde fuera de la intranet pero sin VPN) con un usuario en Skype empresarial Server 2019 y un usuario en la instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="75441-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="75441-115">Compruebe la mensajería instantánea, la presencia, A/V y el uso compartido de escritorio.</span><span class="sxs-lookup"><span data-stu-id="75441-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

