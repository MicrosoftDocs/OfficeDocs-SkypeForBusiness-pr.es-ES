---
title: 'Skype Empresarial Server: Probar las opciones de configuración del tronco SIP'
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
description: 'Summary: Learn how to test SIP trunk configuration settings by using the Skype Empresarial Server Management Shell.'
ms.openlocfilehash: 19e0ad72b33d6ebbd5411fb269c3cdcbf2849a18
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772761"
---
# <a name="skype-for-business-server-test-sip-trunk-configuration-settings"></a>Skype Empresarial Server: Probar las opciones de configuración del tronco SIP
 
**Resumen:** Obtenga información sobre cómo probar las opciones de configuración del tronco SIP mediante el Shell Skype Empresarial Server administración.
  
Las opciones de configuración del tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de red telefónica conmutada (RTC), una central de conmutación (PBX) de sucursal de IP-Public o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:
  
- Si la omisión de medios debe habilitarse en los troncos
    
- Condiciones en las que se envían paquetes del Protocolo de control de transporte en tiempo real (RTCP)
    
- Si el cifrado del Protocolo de transporte en tiempo real seguro (SRTP) es necesario en cada tronco
    
Al instalar Skype Empresarial Server, se crea una colección global de opciones de configuración de tronco SIP. Además, los administradores pueden crear colecciones de opciones personalizadas en el ámbito del sitio o en el ámbito de servicio (solo para el servicio de puerta de enlace RTC). Los administradores también pueden usar el cmdlet Test-CsTrunkConfiguration para comprobar que un tronco puede convertir un número marcado por un usuario en un número que la puerta de enlace puede controlar.
  
Los valores de configuración de tronco solo se pueden probar con Windows PowerShell y el cmdlet [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration). Este cmdlet se puede ejecutar desde el Shell Skype Empresarial Server administración o desde una sesión remota de Skype Empresarial Server Shell de administración.
  
### <a name="to-test-sip-trunk-configuration-settings"></a>Para probar las opciones de configuración del tronco SIP

- Este comando comprueba que los valores de configuración de tronco del sitio de Redmond pueden convertir correctamente el número marcado 4255551212.
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```
