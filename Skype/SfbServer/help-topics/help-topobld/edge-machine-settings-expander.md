---
title: Ampliador de configuración de máquina borde
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Para editar las propiedades de un servidor en un grupo de servidores de borde, haga lo siguiente:'
ms.openlocfilehash: 04b8d8efc455203e49aeb81e533604a405e37cc5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="edge-machine-settings-expander"></a>Ampliador de configuración de máquina borde
 
Para editar las propiedades de un servidor en un grupo de servidores de borde, haga lo siguiente:
  
El **nombre interno o FQDN** puede cambiarse editando el nombre de dominio completo (FQDN). El FQDN debe coincidir con el registro (A) de host de sistema de nombres de dominio (DNS) y el nombre del sujeto del certificado asignado al servidor de la interfaz de red interna de borde. El valor de la **dirección IP interna** define la dirección IP que se asigna a la interfaz de red se define como una red interna, en relación con el diseño de la red perimetral.
  
Las tres secciones del cuadro de diálogo definen las direcciones IP de la configuración de este servidor perimetral externo. La capacidad de cambiar las direcciones IP se ve afectada por el valor de **Habilitar independiente FQDN y la dirección IP para conferencias por Internet y A / V** en la configuración de propiedades en el servidor perimetral de nivel de la piscina.
  
## <a name="sip-access"></a>Acceso SIP

Editar la dirección IP externa que se asigna a la interfaz de red para el acceso de protocolo de inicio de sesión (SIP). Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.
  
> [!NOTE]
> Si el valor de **Habilitar independiente FQDN y la dirección IP para conferencias por Internet y A / V** en el fondo de página configuración está habilitada, sólo estará disponible para editar la dirección IP para acceso SIP.
  
## <a name="web-conferencing"></a>Conferencia web

Editar la dirección IP externa que se asigna a la interfaz de red para conferencias web. Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.
  
## <a name="audiovideo"></a>Audio y vídeo

Editar la dirección IP externa que se asigna a la interfaz de red de audio y vídeo (A / V). Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.
  
La configuración de **NAT compatible con dirección IP pública que se utiliza** es la dirección pública utilizada por la interfaz externa en lugar de A cualquiera / V red interfaz o el servidor perimetral en general. Si la configuración **Habilitar independiente FQDN y la dirección IP para conferencias por Internet y A / V** está habilitada, esta dirección IP pública se utiliza para las tres interfaces externas.
  

