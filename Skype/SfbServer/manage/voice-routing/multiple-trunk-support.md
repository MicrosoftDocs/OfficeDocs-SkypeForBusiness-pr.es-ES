---
title: Compatibilidad con varios troncos en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La funcionalidad de Skype Empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación. Estas asociaciones se realizan definiendo un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red telefónica conmutada (RTC), un controlador de borde de sesión (SBC) o una IP-PBX. Use el Generador de topologías para asociar puertas de enlace con servidores de mediación (es decir, troncos).
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826230"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Compatibilidad con varios troncos en Skype Empresarial Server

La funcionalidad de Skype Empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación. Estas asociaciones se realizan definiendo un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red telefónica conmutada (RTC), un controlador de borde de sesión (SBC) o una IP-PBX. Use el Generador de topologías para asociar puertas de enlace con servidores de mediación (es decir, troncos).

- Para asignar o quitar un tronco en Skype Empresarial Server, primero debe definir un tronco en topology Builder. Un tronco consta de la siguiente asociación: nombre de dominio completo (FQDN) del servidor de mediación, puerto de escucha del servidor de mediación, FQDN de puerta de enlace y puerto de escucha de puerta de enlace.
- Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación. Esto proporciona resistencia adicional a la infraestructura Telefonía IP empresarial, que es especialmente útil en escenarios interoperacionales de central de conmutación (PBX). 

Cuando se define un tronco, debe estar asociado con una ruta. Para asociar un tronco a una ruta, debe definir un nombre simple para el tronco en topology Builder. Este nombre simple se usa como nombre de tronco en el Panel de control de Skype Empresarial Server, donde los troncos se pueden asociar con rutas. El nombre de tronco simple se usa como el nombre de puerta de enlace del Shell de administración de Skype Empresarial Server.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

El administrador debe seleccionar un tronco predeterminado asociado a un servidor de mediación. En el Generador de topologías, haga clic con el botón secundario en el servidor de mediación asociado y, a continuación, haga clic en **Propiedades.** Especifique la puerta de enlace predeterminada para el servidor de mediación. 

El siguiente diagrama ilustra los múltiples troncos que se definen para cada servidor de mediación y puerta de enlace. 

![Asignaciones de varios troncos](../../media/multiple-trunk-assignments.jpg)
