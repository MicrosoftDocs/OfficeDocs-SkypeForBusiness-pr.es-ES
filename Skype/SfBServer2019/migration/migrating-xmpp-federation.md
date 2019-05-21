---
title: Migrar la federación XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Las versiones anteriores proporcionaban una puerta de enlace de protocolo de presencia y mensajería extensible (XMPP) que se podía implementar como un rol de servidor independiente para permitir la Federación con implementaciones de XMPP. La funcionalidad de XMPP ya no está disponible & en desuso en Skype empresarial Server 2019. Si desea continuar con la funcionalidad de XMPP, puede estar disponible en el entorno de coexitence con versión heredada (Skype empresarial Server 2015/Lync Server 2013). La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral heredado y la puerta de enlace XMPP que se ejecuta en el servidor front-end heredado.'
ms.openlocfilehash: fd2b51af84133e28e9a4de035333b1a282d71d38
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298193"
---
# <a name="migrating-xmpp-federation"></a>Migrar la federación XMPP

Las versiones anteriores proporcionaban una puerta de enlace de protocolo de presencia y mensajería extensible (XMPP) que se podía implementar como un rol de servidor independiente para permitir la Federación con implementaciones de XMPP. La funcionalidad de XMPP ya no está disponible y quedó obsoleta en Skype empresarial Server 2019. Si desea continuar con la funcionalidad de XMPP, puede hacerlo en un entorno de coexistencia con una versión heredada (Skype empresarial Server 2015 o Lync Server 2013). La funcionalidad XMPP se instala en dos partes: como un proxy XMPP que se ejecuta en el servidor perimetral heredado y la puerta de enlace XMPP que se ejecuta en el servidor front-end heredado. 
  
Desde el punto de vista de la migración, los usuarios que deseen disponer de la característica XMPP deben permanecer en el servidor heredado y no se deben mover a un grupo de servidores de Skype empresarial 2019, pero seguir usando la puerta de enlace XMPP heredada. Esto solo es posible si el socio de XMPP federado está configurado en Skype empresarial Server 2015 o Lync Server 2013. No debe migrar el servidor perimetral heredado a Skype empresarial Server 2019 si desea continuar con la funcionalidad de XMPP. Sin embargo, puede tener coexistencia del servidor perimetral heredado (con proxy XMPP) y el servidor EDGE 2019 de Skype empresarial.
  

    

