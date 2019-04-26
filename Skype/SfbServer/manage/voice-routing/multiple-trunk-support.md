---
title: Tronco compatibilidad con múltiples en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para la funcionalidad de Business Server admite varias asociaciones entre los servidores de mediación y puertas de enlace. Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una telefónica conmutada (RTC) de red puerta de enlace, controlador de borde de sesión (SBC) o IP-PBX. Use el generador de topología para asociar las puertas de enlace con los servidores de mediación (es decir, troncos).
ms.openlocfilehash: 5d093bee56597474f0cefcf1053536774f2eb795
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214648"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Tronco compatibilidad con múltiples en Skype para Business Server

Skype para la funcionalidad de Business Server admite varias asociaciones entre los servidores de mediación y puertas de enlace. Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una telefónica conmutada (RTC) de red puerta de enlace, controlador de borde de sesión (SBC) o IP-PBX. Use el generador de topología para asociar las puertas de enlace con los servidores de mediación (es decir, troncos).

- Para asignar o quitar un tronco en Skype para Business Server, primero debe definir un tronco en el generador de topología. Un tronco consta de la asociación siguiente: el servidor de mediación completo (FQDN) del nombre de dominio, el puerto de escucha del servidor de mediación, el FQDN de puerta de enlace y el puerto de escucha de puerta de enlace.
- Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación. Esto proporciona resistencia adicional a la infraestructura de telefonía IP empresarial, que es especialmente útil en escenarios de interoperational de central de conmutación (PBX) de exchange. 

Cuando se define un tronco, debe estar asociado con una ruta. Para asociar un tronco a una ruta, defina un nombre sencillo para el tronco en el generador de topología. Este nombre simple se utiliza como el nombre del tronco en el Skype para el Panel de Control de servidor empresarial, donde se pueden asociadas con rutas de troncos. El nombre del tronco simple se utiliza como el nombre de la puerta de enlace de la Skype para Shell de administración de servidor empresarial.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

El administrador debe seleccionar un tronco predeterminado asociado con un servidor de mediación. En el generador de topología, haga clic en el servidor de mediación asociado y, a continuación, haga clic en **Propiedades**. Especifique la puerta de enlace predeterminada para el servidor de mediación. 

En el siguiente diagrama se ilustra los múltiples troncos que se definen para cada servidor de mediación y la puerta de enlace. 

![Varias asignaciones de tronco](../../media/multiple-trunk-assignments.jpg)
