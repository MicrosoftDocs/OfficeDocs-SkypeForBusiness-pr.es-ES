---
title: Director (herramienta de planeación)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un Director es un servidor que ejecuta Skype para software de comunicaciones de Business Server que se puede autenticar las solicitudes de usuario, pero no se encarga de las cuentas de usuario.
ms.openlocfilehash: a1920d11ed354cab3409a9f2a1fd39280ce2d29d
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2018
ms.locfileid: "19975991"
---
# <a name="director-planning-tool"></a>Director (herramienta de planeación)
 
Un Director es un servidor que ejecuta Skype para software de comunicaciones de Business Server que se puede autenticar las solicitudes de usuario, pero no se encarga de las cuentas de usuario. 
  
Este rol es opcional, que decide implementar un Director en los dos escenarios siguientes:
  
- Si habilita el acceso de usuarios externos mediante la implementación de los servidores perimetrales, también debe implementar un Director. En este escenario, el Director autentica a los usuarios externos y, a continuación, pasa el tráfico de sesión en los servidores internos. Cuando se usa un Director para autenticar a los usuarios externos, se liberan los servidores del grupo de servidores Front-End de la sobrecarga de realizar la autenticación de estos usuarios. También ayuda a aislar los grupos de Front-End internos de tráfico malintencionado como ataques de denegación de servicio. Si la red se desborda con el tráfico externo no válido en este tipo de ataque, este tráfico termina en el Director.
    
- Si implementa varios grupos de servidores Front-End en un sitio central, mediante la adición de un Director para ese sitio puede optimizar las solicitudes de autenticación y mejorar el rendimiento. En este escenario, todas las solicitudes van primeros al Director, que enruta al grupo de servidores Front-End correcto.
    

