---
title: Migrar la federación XMPP
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
description: 'Las versiones anteriores proporcionaban una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP) que se podía implementar como una función de servidor independiente para permitir la Federación con las implementaciones de XMPP. La funcionalidad de XMPP ya no está disponible & en desuso en Skype empresarial Server 2019. Si desea continuar con la funcionalidad de XMPP, puede estar disponible en el entorno de coexitence con la versión heredada (Skype empresarial Server 2015/Lync Server 2013). La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral heredado y la puerta de enlace XMPP que se ejecuta en el servidor front-end heredado.'
ms.openlocfilehash: 71b6c213450f51ea4b3fe1f351e22dbb992ce8ca
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752652"
---
# <a name="migrating-xmpp-federation"></a>Migrar la federación XMPP

Las versiones anteriores proporcionaban una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP) que se podía implementar como una función de servidor independiente para permitir la Federación con las implementaciones de XMPP. La funcionalidad de XMPP ya no está disponible y está en desuso en Skype empresarial Server 2019. Si desea continuar con la funcionalidad XMPP, puede hacerlo en un entorno de coexistencia con una versión heredada (Skype empresarial Server 2015 o Lync Server 2013). La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral heredado y la puerta de enlace XMPP que se ejecuta en el servidor front-end heredado. 
  
Desde el punto de vista de la migración, los usuarios que deseen Dispa la característica XMPP deben permanecer en el servidor heredado y no se deben mover a un grupo de servidores de 2019 de Skype empresarial, pero seguir usando la puerta de enlace XMPP heredada. Esto solo es posible si el socio federado de XMPP está configurado en Skype empresarial Server 2015 o Lync Server 2013. No debe migrar el servidor perimetral heredado a Skype empresarial Server 2019 si desea continuar con la funcionalidad XMPP. Sin embargo, puede tener coexistencia del servidor perimetral heredado (con proxy XMPP) y el servidor perimetral 2019 de Skype empresarial.
  

    

