---
title: Probar las opciones de configuración de troncos SIP en Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Resumen: Obtenga información sobre cómo probar las opciones de configuración de troncos SIP mediante el Skype para Shell de administración de servidor empresarial.'
ms.openlocfilehash: d602f24c3342e6c8460cab41d5f14e68ba17188b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222852"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Probar las opciones de configuración de troncos SIP en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo probar las opciones de configuración de troncos SIP mediante el Skype para Shell de administración de servidor empresarial.
  
Las opciones de configuración de los troncos SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:
  
- Si se debe activar la omisión de medios en los troncos.
    
- Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).
    
- Si se requiere el cifrado mediante el protocolo de transporte seguro en tiempo real (SRTP) en todos los troncos.
    
Al instalar Skype para Business Server, se crea una colección global de opciones de configuración de tronco SIP para usted. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC). Los administradores pueden usar también el cmdlet Test-CsTrunkConfiguration para comprobar que el tronco puede convertir un número que ha marcado el usuario en un número que la puerta de enlace puede controlar.
  
Los valores de configuración de tronco solo se pueden probar con Windows PowerShell y el cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps). Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Skype para Shell de administración de servidor empresarial.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Para probar las opciones de configuración de troncos SIP

- Este comando comprueba que los valores de configuración de tronco del sitio de Redmond pueden convertir correctamente el número marcado 4255551212.
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


