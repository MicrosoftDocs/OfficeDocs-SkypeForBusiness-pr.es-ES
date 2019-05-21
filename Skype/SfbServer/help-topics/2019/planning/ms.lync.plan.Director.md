---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: Un director es un servidor que ejecuta el software de comunicaciones de Skype empresarial Server y que puede autenticar solicitudes de usuario, pero no aloja ninguna cuenta de usuario.
ms.openlocfilehash: fa81954e59577ab15edd2a8190e556f4e8e66d47
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275916"
---
# <a name="director-planning-tool"></a>Director (Planning Tool)
 
Un director es un servidor que ejecuta el software de comunicaciones de Skype empresarial Server y que puede autenticar solicitudes de usuario, pero no aloja ninguna cuenta de usuario. 
  
Este rol es opcional y debería elegir implementar un director en los siguientes dos escenarios:
  
- Si habilita el acceso de usuarios externos mediante la implementación de servidores perimetrales, también debe implementar un director. En este escenario, el director autentica a los usuarios externos y, a continuación, pasa su tráfico a los servidores internos. Cuando se usa un director para autenticar usuarios externos, libera servidores de grupo de servidores front-end de la sobrecarga de realizar la autenticación de estos usuarios. También ayuda a aislar grupos internos de aplicaciones para el usuario contra tráfico malintencionado, como ataques de denegación de servicio. Si la red se inunda con tráfico externo no válido en tal ataque, este tráfico finaliza en el director.
    
- Si implementa varios grupos front-end en un sitio central agregando un director a ese sitio, podrá optimizar las solicitudes de autenticación y mejorar el rendimiento. En este escenario, todas las solicitudes se dirigen al Director, que a su vez las enruta al grupo de servidores front-end correcto.
    

