---
title: Director (Herramienta de planeación)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: Un director es un servidor que ejecuta Skype Empresarial Server software de comunicaciones que puede autenticar solicitudes de usuario, pero no alberga cuentas de usuario.
ms.openlocfilehash: 26a6e7e0807f29622214d733b1d848180a3e437c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597144"
---
# <a name="director-planning-tool"></a>Director (Herramienta de planeación)
 
Un director es un servidor que ejecuta Skype Empresarial Server software de comunicaciones que puede autenticar solicitudes de usuario, pero no alberga cuentas de usuario. 
  
Este rol es opcional, elegiría implementar un director en los dos escenarios siguientes:
  
- Si habilita el acceso de usuarios externos mediante la implementación de servidores perimetrales, también debe implementar un director. En este escenario, el director autentica a los usuarios externos y, a continuación, pasa su tráfico a los servidores internos. Cuando se usa un director para autenticar usuarios externos, se libera a los servidores del grupo de servidores front-end de la sobrecarga de realizar la autenticación de estos usuarios. También ayuda a aislar los grupos de servidores front-end internos del tráfico malintencionado, como los ataques por denegación de servicio. Si la red está saturada con tráfico externo no válido, este tráfico llega al director.
    
- Si implementa varios grupos de servidores front-end en un sitio central, al agregar un director a ese sitio, puede simplificar las solicitudes de autenticación y mejorar el rendimiento. En este escenario, todas las solicitudes van primero al Director, que luego las enruta al grupo de servidores front-end correcto.
    

