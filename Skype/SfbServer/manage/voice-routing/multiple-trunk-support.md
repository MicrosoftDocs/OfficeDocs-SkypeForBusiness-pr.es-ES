---
title: Compatibilidad con varios troncales en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La funcionalidad de Skype empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación. Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red de telefonía pública conmutada (RTC), controlador de borde de sesión (SBC) o IP-PBX. Use el generador de topología para asociar puertas de enlace con servidores de mediación (es decir, troncos).
ms.openlocfilehash: a6a0134ee04d939a10aaf9e36c81124d085af5aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274915"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a>Compatibilidad con varios troncales en Skype empresarial Server

La funcionalidad de Skype empresarial Server admite varias asociaciones entre puertas de enlace y servidores de mediación. Estas asociaciones se realizan mediante la definición de un tronco, que es una asociación lógica entre un grupo de servidores de mediación y una puerta de enlace de red de telefonía pública conmutada (RTC), controlador de borde de sesión (SBC) o IP-PBX. Use el generador de topología para asociar puertas de enlace con servidores de mediación (es decir, troncos).

- Para asignar o quitar un tronco en Skype empresarial Server, primero debe definir un tronco en el generador de topologías. Un tronco consiste en la siguiente Asociación: nombre de dominio completo (FQDN) de Media Server, el puerto de escucha del servidor de mediación, el FQDN de la puerta de enlace y el puerto de escucha de la puerta de enlace.
- Para configurar varios troncos, puede crear varias asociaciones entre la misma puerta de enlace y el servidor de mediación. Esto proporciona resistencia adicional a la infraestructura de telefonía IP empresarial, que es especialmente útil en escenarios de interoperabilidad de la intercambiación privada (PBX). 

Cuando se define un tronco, debe estar asociado con una ruta. Para asociar un tronco a una ruta, defina un nombre simple para el tronco en el generador de topología. Este nombre simple se usa como el nombre del tronco en el panel de control de Skype empresarial Server, donde se pueden asociar los troncos con las rutas. El nombre de tronco simple se usa como el nombre de la puerta de enlace desde el shell de administración de Skype empresarial Server.

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

El administrador debe seleccionar un tronco predeterminado asociado a un servidor de mediación. En el generador de topología, haga clic con el botón secundario en el servidor de mediación asociado y luego haga clic en **propiedades**. Especificar la puerta de enlace predeterminada para el servidor de mediación. 

En el siguiente diagrama se muestran los diversos troncos que se definen para cada servidor de mediación y puerta de enlace. 

![Varias asignaciones de tronco](../../media/multiple-trunk-assignments.jpg)
