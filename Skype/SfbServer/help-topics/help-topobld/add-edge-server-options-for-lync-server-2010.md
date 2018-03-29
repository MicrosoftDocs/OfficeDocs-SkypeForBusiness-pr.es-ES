---
title: Agregar las opciones de servidor de borde de Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Definir un nuevo servidor perimetral o un grupo de servidores de borde y se presentan con la oportunidad de definir funciones para el nuevo servidor o grupo de servidores. Las opciones que puede elegir son:'
ms.openlocfilehash: c031480dd3553aa4fc1ca2f2a8ddd03f67d9bc02
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Agregar las opciones de servidor de borde de Lync Server 2010
 
Definir un nuevo servidor perimetral o un grupo de servidores de borde y se presentan con la oportunidad de definir funciones para el nuevo servidor o grupo de servidores. Las opciones que puede elegir son:
  
- **Utilizar una única dirección IP y FQDN**: Active la casilla de verificación utilizar un solo IPv4 o IPv6 (Si opta por utilizar IPv4 e IPv6, debe definir uno de cada tipo de dirección IP) dirección y nombre de dominio completo (FQDN) para el externo interfaces del borde. 
    
    > [!IMPORTANT]
    > Si elige esta opción, se utiliza una única dirección IP, o uno de IPv4 y una IPv6, pero debe asignar a números de puerto diferentes para cada interfaz de bordes. 
  
- **Habilitar la federación (puerto 5061)**: seleccione esta casilla de verificación si va a federar con otras federaciones, proveedores u ofertas de host que utilicen el protocolo de inicio de sesión (SIP) de SIP.
    
- **NAT traduce la dirección IP externa de este grupo de borde**: seleccione esta casilla de verificación si utiliza direcciones IP privadas para las interfaces externas del borde y proporcionará un dispositivo de traducción (NAT) de direcciones de red para colocar el servidor perimetral o bordes de piscina lógicamente subyacente.
    
## <a name="see-also"></a>Vea también

#### 

[Planificación para el acceso de usuarios externos](http://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)
  
[Implementar el acceso de usuarios externos](http://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)

