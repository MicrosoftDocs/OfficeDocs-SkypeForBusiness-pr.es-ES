---
title: Probar la configuración del tronco del SIP en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 'Resumen: Obtenga información sobre cómo probar la configuración de los troncales SIP con el shell de administración de Skype empresarial Server.'
ms.openlocfilehash: a85af538f5729310c75e57313b049dcb14d09542
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766913"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Probar la configuración del tronco del SIP en Skype empresarial Server
 
**Resumen:** Obtenga más información sobre cómo probar la configuración de los troncales SIP con el shell de administración de Skype empresarial Server.
  
Las opciones de configuración de los troncos SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:
  
- Si se debe activar la omisión de medios en los troncos.
    
- Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).
    
- Si se requiere el cifrado mediante el protocolo de transporte seguro en tiempo real (SRTP) en todos los troncos.
    
Al instalar Skype empresarial Server, se crea una colección global de parámetros de configuración del tronco del SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC). Los administradores pueden usar también el cmdlet Test-CsTrunkConfiguration para comprobar que el tronco puede convertir un número que ha marcado el usuario en un número que la puerta de enlace puede controlar.
  
Los valores de configuración de tronco solo se pueden probar con Windows PowerShell y el cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps). Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de la consola de administración de Skype empresarial Server.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Para probar las opciones de configuración de troncos SIP

- Este comando comprueba que los valores de configuración de tronco del sitio de Redmond pueden convertir correctamente el número marcado 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


