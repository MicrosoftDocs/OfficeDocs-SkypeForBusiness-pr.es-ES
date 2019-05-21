---
title: Agregar opciones de servidor perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Defina un nuevo servidor perimetral o un grupo de servidores perimetrales y se le presentará la oportunidad de definir características para el nuevo servidor o grupo. Las opciones que puede elegir son:'
ms.openlocfilehash: 4bb364ee24f2e85ec16ff2f972dfe05aea9306cd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289997"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Agregar opciones de servidor perimetral para Lync Server 2010

Defina un nuevo servidor perimetral o un grupo de servidores perimetrales y se le presentará la oportunidad de definir características para el nuevo servidor o grupo. Las opciones que puede elegir son:

- **Use un único FQDN y una dirección IP**: Active la casilla para usar un único IPv4 o IPv6 (si elige usar IPv4 e IPv6, deberá definir una de cada tipo de dirección IP) y la dirección de nombre de dominio completo (FQDN) para las interfaces de borde externo.

    > [!IMPORTANT]
    > Si elige esta opción, usará solo una dirección IP, o un IPv4 y un IPv6, pero debe asignar números de Puerto diferentes para cada interfaz perimetral.

- **Habilitar Federación (puerto 5061)**: Seleccione esta casilla si se va a federar con otras federaciones, proveedores o federaciones de SIP que usen el protocolo de inicio de sesión (SIP).

- **La dirección IP externa de este grupo de límites se traduce por NAT**: Seleccione esta casilla si usa direcciones IP privadas para las interfaces externas de Edge y proporcionará un dispositivo de traducción de direcciones de red (NAT) para colocar el servidor perimetral o el grupo perimetral de forma lógica respecto.

## <a name="see-also"></a>Vea también

[Planear el acceso de usuarios externos](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[Implementar el acceso de usuarios externos](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
