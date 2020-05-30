---
title: Configurar el desvío de medios con enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Aprenda a configurar la omisión de medios con enrutamiento directo de sistema telefónico para Microsoft Teams cambiando a todos los usuarios a la vez o implementando un enfoque por fases (recomendado).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416900"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurar el desvío de medios con enrutamiento directo

Antes de configurar la omisión de medios con enrutamiento directo, asegúrese de que tiene un [plan de lectura de multimedia con enrutamiento directo](direct-routing-plan-media-bypass.md).

Para activar la omisión de elementos multimedia, se deben cumplir las condiciones siguientes:

1.    Asegúrese de que el proveedor del controlador de borde (SBC) de la sesión que elija admita la omisión de medios y proporciona instrucciones sobre cómo configurar el omisión en la SBC. Consulte la página de certificación para obtener información sobre SBCs, que admiten la omisión de elementos multimedia y para obtener instrucciones.

2.    Debe activar la omisión de elementos multimedia en el tronco con el siguiente comando: **set-CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**.

3.    Asegúrese de que los puertos necesarios estén abiertos. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrar desde troncos no omitidos a troncos habilitados para omitir

Puede cambiar todos los usuarios a la vez o puede implementar un enfoque por fases (recomendado).

- **Cambiar todos los usuarios a la vez.** Si se cumplen todas las condiciones, puede activar el modo de omisión. Sin embargo, todos los usuarios de producción se cambiarán al mismo tiempo. Dado que es posible que al principio experimente algunos problemas al configurar los troncos y los puertos, su experiencia con el usuario de producción podría verse afectada. 

- **Enfoque por fases. (Recomendado)**.  Cree un nuevo tronco para el mismo SBC (con un puerto diferente), pruébelo y cambie la Directiva de enrutamiento de voz en línea para que los usuarios apunten al nuevo tronco. 

  Este es el método recomendado porque permite una transición más fluida y una experiencia de usuario ininterrumpida. Este enfoque requiere la configuración de SBC, un nuevo nombre FQDN y la configuración del firewall. Nota tendrá que asegurarse de que su certificado admite ambos troncos. En SAN, debe tener dos nombres (**sbc1.contoso.com** y **sbc2.contoso.com**) o tener un certificado comodín.

![Migrar desde troncos no omitidos a troncos habilitados para omitir)](media/direct-routing-media-bypass-8.png)

Para obtener instrucciones sobre cómo configurar los troncos y realizar la migración, consulte la documentación del proveedor de SBC:

- [Documentación de la implementación de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentación de implementación de Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentación de implementación de comunicaciones de la cinta](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentación de la implementación de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Para obtener una lista de los controladores de borde de sesión (SBCs) certificados para enrutamiento directo, consulte [List of Session borde Controllers Certified for Direct Routing](direct-routing-border-controllers.md).



## <a name="related-topics"></a>Temas relacionados

[Planear la omisión de medios con enrutamiento directo](direct-routing-plan-media-bypass.md)



