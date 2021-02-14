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
description: Después de realizar la transición de la ruta de federación al servidor perimetral de Skype Empresarial Server 2019, debe realizar algunas pruebas funcionales para comprobar que la federación funciona según lo esperado. Las comprobaciones de acceso de usuarios externos deben abarcar todos los tipos de usuario externo que la organización admita, incluido todos o cualquiera de los indicados a continuación.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751672"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Comprobar la federación y el acceso remoto de usuarios externos

Después de realizar la transición de la ruta de federación al servidor perimetral de Skype Empresarial Server 2019, debe realizar algunas pruebas funcionales para comprobar que la federación funciona según lo esperado. Las comprobaciones de acceso de usuarios externos deben abarcar todos los tipos de usuario externo que la organización admita, incluido todos o cualquiera de los indicados a continuación.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Probar la conectividad de usuarios externos y el acceso externo

- Usuarios de al menos un dominio federado, un usuario interno en Skype Empresarial Server 2019 y un usuario en la instalación heredada. Compruebe la mensajería instantánea (MI), la presencia, el audio/vídeo (A/V) y el uso compartido de escritorio.
    
- Los usuarios de cada proveedor de servicios de mensajería instantánea pública que admite su organización (y para los que se ha completado el aprovisionamiento) se comunican con un usuario en Skype Empresarial Server 2019 y un usuario en la instalación heredada. 
    
- Compruebe que los usuarios anónimos pueden unirse a conferencias.
    
- Un usuario hospedado en la instalación heredada mediante el acceso de usuarios remotos (registro de i nto Lync Server/Skype Empresarial desde fuera de la intranet pero sin VPN) con un usuario en Skype Empresarial Server 2019 y un usuario en la instalación heredada. Compruebe la mensajería instantánea, la presencia, A/V y el uso compartido de escritorio.
    
- Un usuario hospedado en Skype Empresarial Server 2019 con acceso de usuario remoto (iniciando sesión en Skype Empresarial Server 2019 desde fuera de la intranet pero sin VPN) con un usuario en Skype Empresarial Server 2019 y un usuario en la instalación heredada. Compruebe la mensajería instantánea, la presencia, A/V y el uso compartido de escritorio.
    

