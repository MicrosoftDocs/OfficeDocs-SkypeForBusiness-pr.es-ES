---
title: Director (Herramienta de planeación)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un director es un servidor que ejecuta software de comunicaciones de Skype Empresarial Server 2015 que puede autenticar solicitudes de usuario, pero no alberga cuentas de usuario.
ms.openlocfilehash: 9809a6293c212a52dd87476069125540848ee2a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810550"
---
# <a name="director-planning-tool"></a>Director (Herramienta de planeación)
 
Un director es un servidor que ejecuta software de comunicaciones de Skype Empresarial Server 2015 que puede autenticar solicitudes de usuario, pero no alberga cuentas de usuario. 
  
Este rol es opcional, elegiría implementar un director en los dos escenarios siguientes:
  
- Si habilita el acceso de usuarios externos mediante la implementación de servidores perimetrales, también debe implementar un director. En este escenario, el director autentica a los usuarios externos y, a continuación, pasa su tráfico a los servidores internos. Cuando se usa un director para autenticar usuarios externos, libera a los servidores del grupo de servidores front-end de la sobrecarga de realizar la autenticación de estos usuarios. También ayuda a aislar los grupos de servidores front-end internos del tráfico malintencionado, como los ataques por denegación de servicio. Si la red está saturada con tráfico externo no válido, este tráfico llega al director.
    
- Si implementa varios grupos de servidores front-end en un sitio central, si agrega un director a ese sitio, puede simplificar las solicitudes de autenticación y mejorar el rendimiento. En este escenario, todas las solicitudes van primero al director, que las enruta al grupo de servidores front-end correcto.
    

