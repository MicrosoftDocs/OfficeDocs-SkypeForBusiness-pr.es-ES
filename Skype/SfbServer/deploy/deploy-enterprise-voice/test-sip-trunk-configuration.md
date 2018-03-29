---
title: Probar las opciones de configuración de troncos SIP en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Resumen: Conozca cómo probar la configuración de troncales SIP utilizando el Skype para el Shell de administración de servidor empresarial.'
ms.openlocfilehash: 4e4c0c7ce117143f743dd40536bc49bfce92d978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server-2015"></a>Probar las opciones de configuración de troncos SIP en Skype Empresarial Server 2015
 
**Resumen:** Aprenda a probar opciones de configuración de troncal SIP mediante el Skype para el Shell de administración de servidor empresarial.
  
Las opciones de configuración de los troncos SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:
  
- Si se debe activar la omisión de medios en los troncos.
    
- Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).
    
- Si se requiere el cifrado mediante el protocolo de transporte seguro en tiempo real (SRTP) en todos los troncos.
    
Al instalar Skype para Business Server, se crea una colección global de la configuración de troncales SIP para usted. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC). Los administradores pueden usar también el cmdlet Test-CsTrunkConfiguration para comprobar que el tronco puede convertir un número que ha marcado el usuario en un número que la puerta de enlace puede controlar.
  
Configuración de tronco sólo puede probarse mediante Windows PowerShell y el cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) . Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Skype para el Shell de administración de servidor de empresa.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Para probar las opciones de configuración de troncos SIP

- Este comando comprueba que los valores de configuración de tronco del sitio de Redmond pueden convertir correctamente el número marcado 4255551212.
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


