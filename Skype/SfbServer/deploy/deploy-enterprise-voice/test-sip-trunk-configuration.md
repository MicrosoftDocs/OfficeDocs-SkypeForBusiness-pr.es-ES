---
title: Probar las opciones de configuración del tronco SIP en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: obtenga información sobre cómo probar las opciones de configuración del tronco SIP mediante el Shell de administración de Skype Empresarial Server.'
ms.openlocfilehash: 8b3a98d54fd0d2dc8bb69e553e0c0a3a7b98b1ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830640"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Probar las opciones de configuración del tronco SIP en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo probar las opciones de configuración del tronco SIP mediante el Shell de administración de Skype Empresarial Server.
  
Las opciones de configuración del tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red telefónica conmutada (RTC), una central de conmutación (PBX) de IP-Public o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:
  
- Si se debe habilitar el desvío de medios en los troncos.
    
- Condiciones en las que se envían paquetes del Protocolo de control de transporte en tiempo real (RTCP).
    
- Indica si se requiere o no cifrado de Protocolo de transporte en tiempo real seguro (SRTP) en cada tronco.
    
Al instalar Skype Empresarial Server, se crea automáticamente una colección global de opciones de configuración de tronco SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC). Los administradores pueden usar también el cmdlet Test-CsTrunkConfiguration para comprobar que el tronco puede convertir un número que ha marcado el usuario en un número que la puerta de enlace puede controlar.
  
Los valores de configuración de tronco solo se pueden probar con Windows PowerShell y el cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps). Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota del Shell de administración de Skype Empresarial Server.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Para probar las opciones de configuración del tronco SIP

- Este comando comprueba que los valores de configuración de tronco del sitio de Redmond pueden convertir correctamente el número marcado 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


