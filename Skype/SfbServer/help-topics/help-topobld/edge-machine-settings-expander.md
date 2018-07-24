---
title: Expansor de configuración de equipo perimetral
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Para editar las propiedades de un servidor en un grupo de servidores perimetrales, haga lo siguiente:'
ms.openlocfilehash: 2d3e2de296dc575d902422f2263e234f4a8ae1fd
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985370"
---
# <a name="edge-machine-settings-expander"></a>Expansor de configuración de equipo perimetral
 
Para editar las propiedades de un servidor en un grupo de servidores perimetrales, haga lo siguiente:
  
El **nombre interno o FQDN** puede cambiarse editando el nombre de dominio completo (FQDN). El FQDN debe coincidir con el registro (A) de host del sistema de nombres de dominio (DNS) y el nombre de sujeto del certificado asignado al servidor para la interfaz de red perimetral interna. El valor de la **dirección IP interna** define la dirección IP que se asigna a la interfaz de red que se ha definido como una red interna, en relación con el diseño de la red perimetral.
  
Las tres secciones del cuadro de diálogo Definición las direcciones IP para la configuración de este servidor perimetral externa. La capacidad para cambiar las direcciones IP se ve afectada por el valor de **de dirección IP y FQDN independiente de habilitar para la conferencia web y / V** en la configuración de las propiedades en el servidor perimetral de nivel de grupo de servidores.
  
## <a name="sip-access"></a>Acceso SIP

Editar la dirección IP externa que se asigna a la interfaz de red para el acceso de protocolo de inicio de sesión (SIP). Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.
  
> [!NOTE]
> Si la configuración de **de dirección IP y FQDN independiente de habilitar para la conferencia web y / V** en el grupo de página de configuración está habilitada, sólo la dirección IP para el acceso de SIP estará disponible para su edición.
  
## <a name="web-conferencing"></a>Conferencia web

Editar la dirección IP externa que se asigna a la interfaz de red para las conferencias web. Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.
  
## <a name="audiovideo"></a>Audio y vídeo

Editar la dirección IP externa que se asigna a la interfaz de red para audio y vídeo (A / V). Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.
  
El valor de la **dirección IP pública usado habilitado para NAT** es la dirección pública que usa la interfaz externa para puede ser el V red interfaz o el servidor perimetral en general. Si la configuración de **de dirección IP y FQDN independiente de habilitar para la conferencia web y / V** está habilitada, esta dirección IP pública se utiliza para todas las tres interfaces externas.
  

