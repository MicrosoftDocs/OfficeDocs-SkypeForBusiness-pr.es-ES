---
title: Director (herramienta de planeación)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un Director es un servidor que ejecuta Skype para el software de comunicaciones de Business Server 2015 que puede autenticar las solicitudes de usuario, pero no alberga ninguna cuenta de usuario.
ms.openlocfilehash: b379388b05e4beda934b13517f36bc792b6f0748
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="director-planning-tool"></a>Director (herramienta de planeación)
 
Un Director es un servidor que ejecuta Skype para el software de comunicaciones de Business Server 2015 que puede autenticar las solicitudes de usuario, pero no alberga ninguna cuenta de usuario. 
  
Este rol es opcional, que se elige implementar un Director en los dos escenarios siguientes:
  
- Si habilita el acceso de los usuarios externos mediante la implementación de servidores perimetrales, también debe implementar un Director. En este escenario, el Director autentica a los usuarios externos y, a continuación, pasa el tráfico a los servidores internos. Cuando un Director se utiliza para autenticar a los usuarios externos, libera a servidores de grupo de Front-End de la sobrecarga de realizar la autenticación de estos usuarios. También ayuda a aislar grupos internos de Front-End de tráfico malintencionado, como los ataques de denegación de servicio. Si la red está desborda por el tráfico externo no válido en este tipo de ataque, este tráfico se termina en el Director.
    
- Si implementa varios grupos de servidores Front-End en un sitio central, agregando un Director a ese sitio puede agilizar las solicitudes de autenticación y mejorar el rendimiento. En este escenario, todas las solicitudes van primeras al Director, que enruta al grupo correcto de Front-End.
    

