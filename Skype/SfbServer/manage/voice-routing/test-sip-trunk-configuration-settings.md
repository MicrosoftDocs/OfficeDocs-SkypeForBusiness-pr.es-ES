---
title: Probar las opciones de configuración de troncos SIP en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Opciones de configuración de tronco SIP definen la relación y las funciones entre un servidor de mediación y la puerta de enlace de telefónica conmutada (RTC) de red, un IP-público conmutación (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. '
ms.openlocfilehash: 3f251ea720ab220ccda0cfe9882d4a8396085aa0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214627"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Probar las opciones de configuración de troncos SIP en Skype para Business Server

Opciones de configuración de tronco SIP definen la relación y las funciones entre un servidor de mediación y la puerta de enlace de telefónica conmutada (RTC) de red, un IP-público conmutación (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estas opciones de configuración especifican:

- Si se debe activar la omisión de medios en los troncos.
- Las condiciones en las que se envían los paquetes de protocolo (RTCP) de control de transporte en tiempo real.
- Si se requiere cifrado del protocolo seguro en tiempo real (SRTP) en cada tronco.

Al instalar Skype para Business Server, se crea una colección global de opciones de configuración de tronco SIP para usted. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC). Los administradores también pueden usar el cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) para comprobar que un tronco puede convertir a un número como marcados por un usuario a un número que se puede controlar mediante la puerta de enlace.

Los valores de configuración de tronco solo se pueden probar con Windows PowerShell y el cmdlet Test-CsTrunkConfiguration. Este cmdlet se puede ejecutar desde la Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. 

**Para probar las opciones de configuración de troncos SIP**

Este comando comprueba que los valores de configuración de tronco del sitio de Redmond pueden convertir correctamente el número marcado 4255551212.

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
