---
title: Comprobar la federación y el acceso remoto de usuarios externos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Después de la transición de la ruta de Federación al servidor perimetral de Skype empresarial Server 2019, debe realizar algunas pruebas funcionales para comprobar que la Federación se ejecuta según lo previsto. Las pruebas de acceso de usuarios externos deben incluir cada tipo de usuario externo que admita su organización, incluidos algunos de los siguientes elementos o todos ellos.
ms.openlocfilehash: a07cbfc8596cfd49760af1fcee7df90eca362229
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292175"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="59d54-104">Comprobar la federación y el acceso remoto de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="59d54-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="59d54-105">Después de la transición de la ruta de Federación al servidor perimetral de Skype empresarial Server 2019, debe realizar algunas pruebas funcionales para comprobar que la Federación se ejecuta según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="59d54-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="59d54-106">Las pruebas de acceso de usuarios externos deben incluir cada tipo de usuario externo que admita su organización, incluidos algunos de los siguientes elementos o todos ellos.</span><span class="sxs-lookup"><span data-stu-id="59d54-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="59d54-107">Probar la conectividad de usuarios externos y acceso externo</span><span class="sxs-lookup"><span data-stu-id="59d54-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="59d54-108">Usuarios de al menos un dominio federado, un usuario interno de Skype empresarial Server 2019 y un usuario en la instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="59d54-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="59d54-109">Prueba la mensajería instantánea (mi), la presencia, el audio/vídeo (A/V) y el uso compartido del escritorio.</span><span class="sxs-lookup"><span data-stu-id="59d54-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="59d54-110">Los usuarios de cada proveedor de servicios de mensajería instantánea pública que su organización admita (y para el que se haya completado el aprovisionamiento) se comuniquen con un usuario de Skype empresarial Server 2019 y de un usuario en la instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="59d54-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="59d54-111">Comprobar que los usuarios anónimos pueden unirse a conferencias.</span><span class="sxs-lookup"><span data-stu-id="59d54-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="59d54-112">Un usuario alojado en la instalación heredada con acceso de usuarios remotos (inicio de sesión, prensi Lync Server/Skype empresarial desde fuera de la intranet pero sin VPN) con un usuario de Skype empresarial Server 2019 y un usuario en la instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="59d54-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="59d54-113">Prueba la mensajería instantánea, la presencia, la A/V y el uso compartido del escritorio.</span><span class="sxs-lookup"><span data-stu-id="59d54-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="59d54-114">Un usuario hospedado en Skype empresarial Server 2019 con acceso de usuario remoto (iniciar sesión en Skype empresarial Server 2019 desde fuera de la intranet pero sin VPN) con un usuario en Skype empresarial Server 2019 y un usuario en la instalación antigua.</span><span class="sxs-lookup"><span data-stu-id="59d54-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="59d54-115">Prueba la mensajería instantánea, la presencia, la A/V y el uso compartido del escritorio.</span><span class="sxs-lookup"><span data-stu-id="59d54-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

