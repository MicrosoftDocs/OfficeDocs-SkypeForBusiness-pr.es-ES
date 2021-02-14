---
title: Impedir sesiones para servicios
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Puede usar el Panel de control de instalación heredada para evitar nuevas sesiones para todos los servicios heredados que se ejecutan en un equipo específico o para evitar nuevas sesiones para un servicio heredado específico.
ms.openlocfilehash: c5cc8846febaf690376e01c36b9fa023b8377970
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752292"
---
# <a name="prevent-sessions-for-services"></a>Impedir sesiones para servicios

Puede usar el Panel de control de instalación heredada para evitar nuevas sesiones para todos los servicios heredados que se ejecutan en un equipo específico o para evitar nuevas sesiones para un servicio heredado específico.
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a>Para evitar nuevas sesiones para servicios en un equipo

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server 2019.
    
2. Abra el Panel de control de Skype Empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.
    
4. En la página **Estado**, clasifique o busque en la lista, según sea necesario, para localizar el equipo que está ejecutando los servicios para los que desea impedir que se creen sesiones nuevas y, a continuación, haga clic en él. 
    
5. Haga clic en **Acción**.
    
6. Haga clic en **Evitar sesiones nuevas en todos los servicios**.
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a>Para impedir que se creen sesiones nuevas para un servicio específico

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server 2019.
    
2. Abra el Panel de control de Skype Empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Topología** y, a continuación, en **Estado**.
    
4. En la página **Estado**, ordene la lista o realice una búsqueda para encontrar el equipo que ejecuta el servicio que desea iniciar o detener, y haga clic en él. 
    
5. Haga clic en **Propiedades**.
    
6. Clasifique la lista de servicios, si fuera necesario y, a continuación, haga clic en el servicio para el que desea impedir que se creen sesiones nuevas.
    
7. Haga clic en **Acción**.
    
8. Haga clic en **Evitar sesiones nuevas en el servicio**.
    
9. Haga clic en **Cerrar**.
    

