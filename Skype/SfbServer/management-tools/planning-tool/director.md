---
title: Herramienta de planeación de directores
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un director es un servidor que Skype Empresarial Server software de comunicaciones de 2015 que puede autenticar solicitudes de usuario pero no alberga cuentas de usuario.
ms.openlocfilehash: 964a86ee4959a56e88db054ff9229fbd4363e4fe
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646461"
---
# <a name="director-planning-tool"></a>Herramienta de planeación de directores
 
Un director es un servidor que Skype Empresarial Server software de comunicaciones de 2015 que puede autenticar solicitudes de usuario, pero que no alberga cuentas de usuario. 
  
Este rol es opcional, elegiría implementar un director en los dos escenarios siguientes:
  
- Si habilita el acceso de los usuarios invitados mediante la implementación de servidores perimetrales, también debe implementar un director. En este escenario, el director autentica a los invitados y, a continuación, pasa su tráfico a servidores internos. Cuando se usa un director para autenticar invitados, se liberan los servidores del grupo de servidores front-end de la sobrecarga de autenticación de estos usuarios. También ayuda a aislar los grupos de servidores front-end internos del tráfico malintencionado, como los ataques por denegación de servicio. Si la red está saturada con tráfico externo no válido, este tráfico llega al director.
    
- Si implementa varios grupos de servidores front-end en un sitio central, al agregar un director a ese sitio, puede simplificar las solicitudes de autenticación y mejorar el rendimiento. En este escenario, todas las solicitudes van primero al Director, que luego las enruta al grupo de servidores front-end correcto.
    

