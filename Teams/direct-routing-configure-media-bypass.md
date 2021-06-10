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
description: Obtenga información sobre cómo configurar la omisión de medios con Sistema telefónico enrutamiento directo para Microsoft Teams cambiando todos los usuarios a la vez o implementando un enfoque por fases (recomendado).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416900"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurar el desvío de medios con enrutamiento directo

Antes de configurar la omisión de medios con Enrutamiento directo, asegúrese de que ha leído Planear la omisión de [medios con Enrutamiento directo.](direct-routing-plan-media-bypass.md)

Para activar la omisión de medios, deben cumplirse las siguientes condiciones:

1.    Asegúrese de que el proveedor de elección del controlador de borde de sesión (SBC) admite la omisión de medios y proporciona instrucciones sobre cómo configurar la omisión en el SBC. Consulte la página de certificación para obtener información sobre los SBC, que admiten la omisión de medios, y para obtener instrucciones.

2.    Debe activar la omisión de medios en el tronco con el siguiente  **comando: Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.

3.    Asegúrese de que los puertos necesarios están abiertos. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrar de troncos no omitido a troncos habilitados para omitir

Puede cambiar todos los usuarios a la vez o puede implementar un enfoque por fases (recomendado).

- **Cambiar todos los usuarios a la vez.** Si se cumplen todas las condiciones, puede activar el modo de omisión. Sin embargo, todos los usuarios de producción se cambiarán al mismo tiempo. Dado que es posible que experimente algunos problemas inicialmente al configurar troncos y puertos, es posible que su experiencia de usuario de producción se vea afectada. 

- **Enfoque por fases. (Recomendado).**  Cree un nuevo tronco para el mismo SBC (con un puerto diferente), probarlo y cambie la directiva de enrutamiento de voz en línea para que los usuarios apunten al nuevo tronco. 

  Este es el enfoque recomendado porque permite una transición más suave y una experiencia de usuario sin interrupciones. Este enfoque requiere la configuración del SBC, un nuevo nombre FQDN y la configuración del firewall. Tenga en cuenta que tendrá que asegurarse de que el certificado admite ambos troncos. En SAN, debe tener dos nombres **(sbc1.contoso.com** y **sbc2.contoso.com)** o tener un certificado comodín.

![Migrar de troncos no omitido a troncos habilitados para omitir)](media/direct-routing-media-bypass-8.png)

Para obtener instrucciones sobre cómo configurar los troncos y realizar la migración, consulte la documentación de su proveedor de SBC:

- [Documentación de implementación de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentación de implementación de Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentación de implementación de Comunicaciones de la cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentación de implementación de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Para obtener una lista de controladores de borde de sesión (SBC) certificados para enrutamiento directo, vea Lista de controladores de broder de sesión certificados [para enrutamiento directo.](direct-routing-border-controllers.md)



## <a name="related-topics"></a>Temas relacionados

[Planear el desvío de medios con enrutamiento directo](direct-routing-plan-media-bypass.md)



