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
description: Aprenda a configurar la omisión de medios con el enrutamiento directo de Sistema telefónico para Microsoft Teams cambiando todos los usuarios a la vez o implementando un enfoque por fases (recomendado).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416900"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurar el desvío de medios con enrutamiento directo

Antes de configurar la omisión de medios con enrutamiento directo, asegúrese de haber leído plan de omisión [de medios con enrutamiento directo.](direct-routing-plan-media-bypass.md)

Para activar la omisión de medios, deben cumplirse las siguientes condiciones:

1.    Asegúrese de que el proveedor del controlador de borde de sesión (SBC) admite la omisión de medios y proporciona instrucciones sobre cómo configurar la omisión en la SBC. Consulta la página de certificación para obtener información sobre los SBC, que admiten el omisión de medios, y para obtener instrucciones.

2.    Debe activar la omisión de medios en el tronco usando el comando siguiente:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.

3.    Asegúrese de que los puertos necesarios estén abiertos. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrar desde troncos no omitados a troncos no habilitados para omisión

Puede cambiar todos los usuarios a la vez o implementar un enfoque por fases (recomendado).

- **Cambiar todos los usuarios a la vez.** Si se cumplen todas las condiciones, puede activar el modo de omisión. Sin embargo, todos los usuarios de producción se cambiarán al mismo tiempo. Como es posible que experimente algunos problemas inicialmente al configurar troncos y puertos, es posible que la experiencia del usuario de producción se vea afectada. 

- **Enfoque por fases. (Recomendado).**  Cree un tronco nuevo para el mismo SBC (con un puerto diferente), pruebe y cambie la directiva de enrutamiento de voz en línea para que los usuarios apunten al nuevo tronco. 

  Este es el enfoque recomendado porque permite una transición más fluida y una experiencia de usuario sin interrupciones. Este método requiere la configuración de la SBC, un nuevo nombre DE FQDN y la configuración del firewall. Tenga en cuenta que necesitará asegurarse de que el certificado admite ambos troncos. En SAN, debe tener dos nombres **(sbc1.contoso.com** y **sbc2.contoso.com)** o tener un certificado comodín.

![Migrar desde troncos no omitados a troncos habilitados para omisión)](media/direct-routing-media-bypass-8.png)

Para obtener instrucciones sobre cómo configurar los troncos y realizar la migración, consulte la documentación de su proveedor de SBC:

- [Documentación de implementación de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentación de implementación de Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentación de implementación de comunicaciones de la cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentación de implementación de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Para obtener una lista de controladores de borde de sesión (SBCs) certificados para enrutamiento directo, consulta la lista de controladores de controlador de borde de sesión certificados [para enrutamiento directo.](direct-routing-border-controllers.md)



## <a name="related-topics"></a>Temas relacionados

[Planear la omisión de medios con enrutamiento directo](direct-routing-plan-media-bypass.md)



