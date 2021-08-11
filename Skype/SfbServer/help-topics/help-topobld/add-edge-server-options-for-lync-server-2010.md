---
title: Agregar opciones de servidor perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Defina un nuevo servidor perimetral o grupo de servidores perimetrales y se le ofrece la oportunidad de definir características para el nuevo servidor o grupo de servidores. Las opciones entre las que puede elegir son:'
ms.openlocfilehash: c258f87ac3edb38ad72d536b8ccfb2f2870d5d9e09cda65b417e49ba2c87707f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320462"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Agregar opciones de servidor perimetral para Lync Server 2010

Defina un nuevo servidor perimetral o grupo de servidores perimetrales y se le ofrece la oportunidad de definir características para el nuevo servidor o grupo de servidores. Las opciones entre las que puede elegir son:

- **Usar un FQDN único y una dirección IP**: active esta casilla para usar una sola dirección IPv4 o IPv6 (si elige usar ambos IPv4 y IPv6, deberá definir una dirección IP de cada tipo) y un nombre de dominio completo (FQDN) para las interfaces perimetrales externas.

    > [!IMPORTANT]
    > Si elige esta opción, usará una sola dirección IP, o una IPv4 y una IPv6, pero debe asignar números de puerto diferentes a cada interfaz perimetral.

- **Habilitar federación (puerto 5061)**: active esta casilla si va a establecer relaciones de federación con otras federaciones SIP, proveedores u ofertas hospedadas que usan el protocolo de inicio de sesión (SIP).

- NAT traduce la dirección IP externa de este grupo de servidores perimetrales: active esta casilla si usa direcciones **IP** privadas para las interfaces externas perimetrales y proporcionará un dispositivo de traducción de direcciones de red (NAT) para colocar el servidor perimetral o el grupo perimetral lógicamente detrás.

## <a name="see-also"></a>Consulte también

[Planeación del acceso de usuarios externos](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)

[Implementación de servidores perimetrales](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-external-user-access)