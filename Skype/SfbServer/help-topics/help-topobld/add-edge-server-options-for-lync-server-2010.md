---
title: Agregar opciones de servidor perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Puede definir un nuevo servidor perimetral o un grupo de servidores perimetrales y se presenta la oportunidad de definir características para el nuevo servidor o grupo de servidores. Las opciones entre las que puede elegir son:'
ms.openlocfilehash: 273b2543fc3eea1373817ab38eab39379ec59132
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216601"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Agregar opciones de servidor perimetral para Lync Server 2010

Puede definir un nuevo servidor perimetral o un grupo de servidores perimetrales y se presenta la oportunidad de definir características para el nuevo servidor o grupo de servidores. Las opciones entre las que puede elegir son:

- **Usar un FQDN único y una dirección IP**: active esta casilla para usar una sola dirección IPv4 o IPv6 (si elige usar ambos IPv4 y IPv6, deberá definir una dirección IP de cada tipo) y un nombre de dominio completo (FQDN) para las interfaces perimetrales externas.

    > [!IMPORTANT]
    > Si elige esta opción, usará una sola dirección IP, o una IPv4 y una IPv6, pero debe asignar números de puerto diferentes a cada interfaz perimetral.

- **Habilitar federación (puerto 5061)**: active esta casilla si va a establecer relaciones de federación con otras federaciones SIP, proveedores u ofertas hospedadas que usan el protocolo de inicio de sesión (SIP).

- **La dirección IP externa de este grupo de servidores perimetrales se traduce mediante NAT**: Seleccione esta casilla si usa direcciones IP privadas para las interfaces externas perimetrales y proporcionará un dispositivo de traducción de direcciones de red (NAT) para poner el servidor perimetral o el grupo de servidores perimetrales perimetrales detrás de forma lógica.

## <a name="see-also"></a>Vea también

[Planeación del acceso de usuarios externos](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[Implementación de servidores perimetrales](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
