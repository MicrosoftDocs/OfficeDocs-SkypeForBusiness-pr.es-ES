---
title: Agregar opciones de servidor perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Definir un nuevo servidor perimetral o grupo de servidores perimetrales y se presentan con la oportunidad para definir las características para el nuevo servidor o grupo de servidores. Las opciones que puede elegir son:'
ms.openlocfilehash: cb2b7f1df7da9abbe5eb4d8e5b451f7f0db05d0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886293"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Agregar opciones de servidor perimetral para Lync Server 2010

Definir un nuevo servidor perimetral o grupo de servidores perimetrales y se presentan con la oportunidad para definir las características para el nuevo servidor o grupo de servidores. Las opciones que puede elegir son:

- **Usar una única dirección IP y FQDN**: Active la casilla de verificación para usar un solo IPv4 o IPv6 (Si opta por utilizar IPv4 como IPv6, y, a continuación, debe definir uno de cada tipo de dirección IP) dirección y nombre de dominio completo (FQDN) para la externa perimetral interfaces.

    > [!IMPORTANT]
    > Si elige esta opción, va a usar una única dirección IP, o una IPv4 y uno IPv6, pero debe asignar a números de puerto diferentes para cada interfaz perimetral.

- **Habilitar la federación (puerto 5061)**: seleccione esta casilla de verificación si va a federar con otras federaciones SIP, proveedores u ofertas hospedadas que usan el protocolo de inicio de sesión (SIP).

- **La dirección IP externa de este grupo de servidores perimetrales se traduce mediante NAT**: seleccione esta casilla de verificación si se usa direcciones IP privadas para las interfaces externas perimetrales y proporcionará un dispositivo de traducción (NAT) de direcciones de red para colocar el servidor perimetral o grupo de servidores perimetrales lógicamente subyacente.

## <a name="see-also"></a>Vea también

[Planear el acceso de usuarios externos](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[Implementación de acceso de usuarios externos](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
