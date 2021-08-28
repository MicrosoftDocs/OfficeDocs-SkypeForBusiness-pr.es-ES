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
ms.localizationpriority: medium
description: 'Las versiones anteriores proporcionaba una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP) que podía implementarse como un rol de servidor independiente para permitir la federación con implementaciones XMPP. La funcionalidad XMPP ya no está disponible & en desuso en Skype Empresarial Server 2019. Si desea continuar con la funcionalidad XMPP, puede usarse en entornos de coexitencia con la versión heredada (Skype Empresarial Server 2015/ Lync Server 2013). La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral heredado y la puerta de enlace XMPP que se ejecuta en el servidor front-end heredado.'
ms.openlocfilehash: a0c3eeaa6218c6e3b3726f755adcca6083a9ac3f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580134"
---
# <a name="migrating-xmpp-federation"></a>Migrar la federación XMPP

Las versiones anteriores proporcionaba una puerta de enlace de protocolo extensible de mensajería y presencia (XMPP) que podía implementarse como un rol de servidor independiente para permitir la federación con implementaciones XMPP. La funcionalidad XMPP ya no está disponible y está en desuso en Skype Empresarial Server 2019. Si desea continuar con la funcionalidad XMPP, puede hacerlo en un entorno de coexistencia con una versión heredada (Skype Empresarial Server 2015 o Lync Server 2013). La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral heredado y la puerta de enlace XMPP que se ejecuta en el servidor front-end heredado. 
  
Desde el punto de vista de la migración, los usuarios que quieran usar la característica XMPP deben permanecer en el servidor heredado y no deben moverse a un grupo de servidores de Skype Empresarial Server 2019, sino seguir usando la puerta de enlace XMPP heredada. Esto solo es posible cuando el partner federado XMPP está configurado en Skype Empresarial Server 2015 o Lync Server 2013. No debe migrar el servidor perimetral heredado a Skype Empresarial Server 2019 si desea continuar con la funcionalidad XMPP. Sin embargo, puede tener coexistencia del servidor perimetral heredado (con proxy XMPP) y el servidor perimetral Skype Empresarial 2019.
  

    

