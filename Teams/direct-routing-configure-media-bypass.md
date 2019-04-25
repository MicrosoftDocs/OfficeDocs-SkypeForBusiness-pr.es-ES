---
title: Configurar el desvío de medios con enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Lea este tema para obtener información sobre cómo configurar el desvío de medios con el enrutamiento directo teléfono del sistema.
ms.openlocfilehash: 459ebd80a175fbf2c213a016436a2bf130ae9982
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232701"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurar el desvío de medios con enrutamiento directo

Antes de desvío de medios de configuración con el enrutamiento directo, asegúrese de que ha leído [Plan para los medios de desvío con el enrutamiento directo](direct-routing-plan-media-bypass.md).

Para activar el desvío de medios, se deben cumplir las siguientes condiciones:

1.  Asegúrese de que su proveedor de controlador de borde de sesión (SBC) de elección es compatible con el desvío de medios y proporciona instrucciones acerca de cómo configurar el desvío en el SBC. Consulte la página de certificación para obtener más información acerca de SBCs, el desvío de los medios de soporte técnico, y para obtener instrucciones.

2.  Debe activar el desvío de medios en el tronco mediante el siguiente comando: **Set-CSOnlinePSTNGateway-<sbc_FQDN> Identity - MediaBypass $true**.

3.  Asegúrese de que se abren los puertos requeridos. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migración de troncos no pasó a habilitados para el desvío de troncos

Puede cambiar todos los usuarios a la vez o puede implementar por fases lleva a cabo (recomendado).

- **Cambiar todos los usuarios a la vez.** Si se cumplen todas las condiciones, puede activar el modo de omisión. Sin embargo, todos los usuarios de producción cambiará al mismo tiempo. Debido a que podrían experimentar algunos problemas inicialmente al configurar troncos y puertos, la experiencia de usuario de producción podría verse afectada. 

- Enfoque de **Phased. (Recomendado)**.  Crear un nuevo tronco para la misma SBC (con un puerto diferente), ponerlo a prueba y cambiar la directiva de enrutamiento de voz en línea para los usuarios para que apunte al nuevo tronco. 

  Éste es el enfoque recomendado porque permite una transición más suave y la experiencia del usuario sin interrupciones. Este método requiere la configuración de la SBC, un nuevo nombre FQDN y la configuración del servidor de seguridad. Tenga en cuenta que tendrá para asegurarse de que su certificado admite tanto los troncos. En SAN, debe tener dos nombres (**sbc1.contoso.com** y **sbc2.contoso.com**) o tener un certificado de comodín.

![Migración de troncos no pasó a habilitados para el desvío de troncos)](media/direct-routing-media-bypass-8.png)

Para obtener instrucciones sobre cómo configurar los troncos y realizar la migración, consulte la documentación de su proveedor de SBC:

- AudioCodes
- Cinta de opciones
- TE-Systems (AnyNode)    

Para obtener una lista de controladores de borde de sesión (SBCs) certificados para el enrutamiento directo, vea la [lista de controladores de Broder sesión certificados para el enrutamiento directo](direct-routing-border-controllers.md).



## <a name="see-also"></a>Vea también

[Planear el desvío de medios con el enrutamiento directo](direct-routing-plan-media-bypass.md)



