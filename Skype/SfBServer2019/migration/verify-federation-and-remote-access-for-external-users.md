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
# <a name="verify-federation-and-remote-access-for-external-users"></a>Comprobar la federación y el acceso remoto de usuarios externos

Después de la transición de la ruta de Federación al servidor perimetral de Skype empresarial Server 2019, debe realizar algunas pruebas funcionales para comprobar que la Federación se ejecuta según lo previsto. Las pruebas de acceso de usuarios externos deben incluir cada tipo de usuario externo que admita su organización, incluidos algunos de los siguientes elementos o todos ellos.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Probar la conectividad de usuarios externos y acceso externo

- Usuarios de al menos un dominio federado, un usuario interno de Skype empresarial Server 2019 y un usuario en la instalación heredada. Prueba la mensajería instantánea (mi), la presencia, el audio/vídeo (A/V) y el uso compartido del escritorio.
    
- Los usuarios de cada proveedor de servicios de mensajería instantánea pública que su organización admita (y para el que se haya completado el aprovisionamiento) se comuniquen con un usuario de Skype empresarial Server 2019 y de un usuario en la instalación heredada. 
    
- Comprobar que los usuarios anónimos pueden unirse a conferencias.
    
- Un usuario alojado en la instalación heredada con acceso de usuarios remotos (inicio de sesión, prensi Lync Server/Skype empresarial desde fuera de la intranet pero sin VPN) con un usuario de Skype empresarial Server 2019 y un usuario en la instalación heredada. Prueba la mensajería instantánea, la presencia, la A/V y el uso compartido del escritorio.
    
- Un usuario hospedado en Skype empresarial Server 2019 con acceso de usuario remoto (iniciar sesión en Skype empresarial Server 2019 desde fuera de la intranet pero sin VPN) con un usuario en Skype empresarial Server 2019 y un usuario en la instalación antigua. Prueba la mensajería instantánea, la presencia, la A/V y el uso compartido del escritorio.
    

