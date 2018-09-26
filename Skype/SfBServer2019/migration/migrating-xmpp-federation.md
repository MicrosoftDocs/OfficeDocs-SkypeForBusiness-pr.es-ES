---
title: Migración de la federación XMPP
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Las versiones anteriores proporcionan una extensible de mensajería y presencia (XMPP) de protocolo puerta de enlace que se pueden implementar como una función de servidor distinta para permitir la federación con las implementaciones de XMPP. La funcionalidad XMPP ya no está en desuso en Skype para Business Server 2019 & disponibles. Si desea continuar con la funcionalidad XMPP, que puede optado en el entorno de coexitence con la versión heredada (Skype para Business Server 2015 / Lync Server 2013). Funcionalidad XMPP está instalada en dos partes: como un XMPP proxy que se ejecuta en el heredado servidor perimetral y la puerta de enlace XMPP que se ejecuta en el servidor de Front-End heredado.'
ms.openlocfilehash: d8db32bd823e4a0c15fa373f89ee930d2cd8d98c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029870"
---
# <a name="migrating-xmpp-federation"></a>Migración de la federación XMPP

Las versiones anteriores proporcionan una extensible de mensajería y presencia (XMPP) de protocolo puerta de enlace que se pueden implementar como una función de servidor distinta para permitir la federación con las implementaciones de XMPP. La funcionalidad XMPP ya no está disponible y está en desuso en Skype para Business Server 2019. Si desea continuar con la funcionalidad XMPP, puede hacerlo en un entorno de coexistencia con una versión heredada (Skype para Business Server 2015 o Lync Server 2013). Funcionalidad XMPP está instalada en dos partes: como un XMPP proxy que se ejecuta en el heredado servidor perimetral y la puerta de enlace XMPP que se ejecuta en el servidor de Front-End heredado. 
  
Desde una perspectiva de migración, los usuarios que deseen recurrir a la característica XMPP deben permanecer en el servidor heredado y no se mueven a un Skype para el grupo de servidores de Business Server 2019 pero seguirán usando la puerta de enlace XMPP heredado. Esto es posible sólo cuando el socio federado XMPP está configurado en Skype para Business Server 2015 o Lync Server 2013. No se debe migrar el servidor perimetral heredado a Skype para Business Server 2019 si desea continuar con la funcionalidad de XMPP. Sin embargo, puede tener la coexistencia del servidor perimetral heredado (con Proxy XMPP) y la Skype para servidor perimetral de negocio 2019.
  

    

