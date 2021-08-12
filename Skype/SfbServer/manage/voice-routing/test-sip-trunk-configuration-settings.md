---
title: 'Skype Empresarial Server: probar las opciones de configuración del tronco SIP'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Las opciones de configuración del tronco SIP definen la relación y las capacidades entre una puerta de enlace del servidor de mediación y la puerta de enlace PST, una PBX o un SBC en el proveedor de servicios. '
ms.openlocfilehash: b6154c1f6a608d0cac0084b3c49caf2b7aa630229464d922926f0eeb4ad20f7f
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848995"
---
# <a name="skype-for-business-server---test-sip-trunk-configuration-settings"></a>Skype Empresarial Server: probar las opciones de configuración del tronco SIP

Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:

- Si se debe habilitar el desvío de medios en los troncos.
- Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).
- Si se requiere o no el cifrado del protocolo de tiempo real seguro (SRTP) en cada tronco.

Al instalar Skype Empresarial Server, se crea una colección global de opciones de configuración de tronco SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC). Los administradores también pueden usar el cmdlet [Test-CsTrunkConfiguration](/powershell/module/skype/Test-CsTrunkConfiguration) para comprobar que un tronco puede convertir un número marcado por un usuario en un número que puede controlar la puerta de enlace.

Los valores de configuración de tronco solo se pueden probar con Windows PowerShell y el cmdlet Test-CsTrunkConfiguration. Este cmdlet se puede ejecutar desde el Shell Skype Empresarial Server administración o desde una sesión remota de Windows PowerShell. 

**Para probar las opciones de configuración del tronco SIP**

Este comando comprueba que los valores de configuración de tronco del sitio de Redmond pueden convertir correctamente el número marcado 4255551212.

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
