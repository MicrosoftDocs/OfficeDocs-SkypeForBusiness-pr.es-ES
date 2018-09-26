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
# <a name="verify-federation-and-remote-access-for-external-users"></a>Comprobar la federación y el acceso remoto de usuarios externos

Después de trasladar la ruta de federación para el Skype para servidor perimetral de Business Server 2019, debe realizar algunas pruebas funcionales para comprobar que la federación funciona del modo esperado. Las pruebas para el acceso de usuarios externos deben incluir cada tipo de usuario externo que admita su organización, incluidos cualquiera o todas las opciones siguientes.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Probar la conectividad de los usuarios externos y acceso externo

- Instalación de los usuarios al menos un dominio federado, un usuario interno de Skype para Business Server 2019 y un usuario en el heredado. Probar la mensajería instantánea (IM), presencia, audio y vídeo (A / V) y uso compartido de escritorio.
    
- Los usuarios de cada proveedor de servicios de mensajería instantánea pública que admita su organización (y para la que se ha completado el aprovisionamiento) comunicarse con un usuario de Skype para Business Server 2019 y un usuario de la instalación heredado. 
    
- Compruebe que los usuarios anónimos se pueden unir a las conferencias.
    
- Un usuario hospedado en el heredado instalar con acceso de usuarios remotos (registro i nPara Lync Server/Skype para la empresa desde fuera de la intranet, pero sin VPN) con un usuario de Skype para Business Server 2019 y un usuario en la instalación heredado. Mensajería instantánea, presencia, de prueba de un uso compartido V y escritorio.
    
- Un usuario hospedado en Skype para Business Server 2019 con acceso de usuarios remotos (inicio de sesión en Skype para Business Server 2019 desde fuera de la intranet, pero sin VPN) con un usuario de Skype para Business Server 2019 y un usuario de la instalación heredado. Mensajería instantánea, presencia, de prueba de un uso compartido V y escritorio.
    

