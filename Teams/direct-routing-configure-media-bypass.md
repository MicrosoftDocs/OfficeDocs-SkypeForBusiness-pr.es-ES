---
title: Configurar el desvío de medios con enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: Lea este tema para aprender a configurar la omisión de medios con enrutamiento directo de sistema telefónico.
ms.openlocfilehash: a9769e921ff493e67614cf903ca9206f6f50bac8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290456"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurar el desvío de medios con enrutamiento directo

Antes de configurar la omisión de medios con enrutamiento directo, asegúrese de que tiene un [plan de lectura de multimedia con enrutamiento directo](direct-routing-plan-media-bypass.md).

Para activar la omisión de elementos multimedia, se deben cumplir las condiciones siguientes:

1.  Asegúrese de que el proveedor del controlador de borde (SBC) de la sesión que elija admita la omisión de medios y proporciona instrucciones sobre cómo configurar el omisión en la SBC. Consulte la página de certificación para obtener información sobre SBCs, que admiten la omisión de elementos multimedia y para obtener instrucciones.

2.  Para activar la omisión de elementos multimedia en el tronco, use el siguiente comando: **set-CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**.

3.  Asegúrese de que los puertos necesarios estén abiertos. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrar desde troncos no omitidos a troncos habilitados para omitir

Puede cambiar todos los usuarios a la vez o puede implementar un enfoque por fases (recomendado).

- **Cambiar todos los usuarios a la vez.** Si se cumplen todas las condiciones, puede activar el modo de omisión. Sin embargo, todos los usuarios de producción se cambiarán al mismo tiempo. Dado que es posible que al principio experimente algunos problemas al configurar los troncos y los puertos, su experiencia con el usuario de producción podría verse afectada. 

- **Enfoque por fases. (Recomendado)**.  Cree un nuevo tronco para el mismo SBC (con un puerto diferente), pruébelo y cambie la Directiva de enrutamiento de voz en línea para que los usuarios apunten al nuevo tronco. 

  Este es el método recomendado porque permite una transición más fluida y una experiencia de usuario ininterrumpida. Este enfoque requiere la configuración de SBC, un nuevo nombre FQDN y la configuración del firewall. Nota tendrá que asegurarse de que su certificado admite ambos troncos. En SAN, debe tener dos nombres (**sbc1.contoso.com** y **sbc2.contoso.com**) o tener un certificado comodín.

![Migrar desde troncos no omitidos a troncos habilitados para omitir)](media/direct-routing-media-bypass-8.png)

Para obtener instrucciones sobre cómo configurar los troncos y realizar la migración, consulte la documentación del proveedor de SBC:

- AudioCodes
- Lazo
- TE-Systems (AnyNode)    

Para obtener una lista de los controladores de borde de sesión (SBCs) certificados para enrutamiento directo, consulte [List of Session borde Controllers Certified for Direct Routing](direct-routing-border-controllers.md).



## <a name="see-also"></a>Vea también

[Planear la omisión de medios con enrutamiento directo](direct-routing-plan-media-bypass.md)



