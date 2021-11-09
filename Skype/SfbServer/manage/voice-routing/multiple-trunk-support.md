---
title: Compatibilidad con varios troncos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype Empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación. Estas asociaciones se realizan definiendo un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red telefónica conmutada (RTC), controlador de borde de sesión (SBC) o IP-PBX. Use el Generador de topologías para asociar puertas de enlace con servidores de mediación (es decir, troncos).
ms.openlocfilehash: aee1cdebba9780eb0079200cf6b0e0c1a5789535
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833356"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Compatibilidad con varios troncos en Skype Empresarial Server

Skype Empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación. Estas asociaciones se realizan definiendo un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red telefónica conmutada (RTC), controlador de borde de sesión (SBC) o IP-PBX. Use el Generador de topologías para asociar puertas de enlace con servidores de mediación (es decir, troncos).

- Para asignar o quitar un tronco en Skype Empresarial Server, primero debe definir un tronco en el Generador de topologías. Un tronco consta de la siguiente asociación: Nombre de dominio completo (FQDN) del servidor de mediación, puerto de escucha del servidor de mediación, FQDN de puerta de enlace y puerto de escucha de puerta de enlace.
- Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación. Esto proporciona resistencia adicional a la infraestructura Telefonía IP empresarial, que es especialmente útil en escenarios interoperacionales de central de conmutación (PBX). 

Cuando se define un tronco, debe estar asociado con una ruta. Para asociar un tronco a una ruta, defina un nombre simple para el tronco en el Generador de topologías. Este nombre simple se usa como nombre de tronco en el Panel de control de Skype Empresarial Server, donde los troncos se pueden asociar con rutas. El nombre de tronco simple se usa como el nombre de puerta de enlace del Shell Skype Empresarial Server administración.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

El administrador debe seleccionar un tronco predeterminado asociado a un servidor de mediación. En el Generador de topologías, haga clic con el botón secundario en el servidor de mediación asociado y, a continuación, haga clic en **Propiedades**. Especifique la puerta de enlace predeterminada para el servidor de mediación. 

En el siguiente diagrama se muestran los varios troncos que se definen para cada servidor de mediación y puerta de enlace. 

![Varias asignaciones de tronco.](../../media/multiple-trunk-assignments.jpg)
