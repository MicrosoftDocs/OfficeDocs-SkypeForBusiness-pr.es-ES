---
title: Expansor de configuración de equipo perimetral
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Para editar las propiedades de un servidor de un grupo de servidores perimetrales, haga lo siguiente:'
ms.openlocfilehash: 93d8169eaaa6c0ca69b9210addea37ac21a8c5b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820092"
---
# <a name="edge-machine-settings-expander"></a>Expansor de configuración de equipo perimetral
 
Para editar las propiedades de un servidor de un grupo de servidores perimetrales, haga lo siguiente:
  
El **nombre interno o FQDN** se puede cambiar editando el nombre de dominio completo (FQDN). El FQDN debe coincidir con el registro del host (A) del sistema de nombres de dominio (DNS) y el nombre de asunto del certificado asignado al servidor para la interfaz de red perimetral interna. El valor de **dirección IP interna** define la dirección IP que se asigna a la interfaz de red que se define como una red interna, en relación con el diseño de la red perimetral.
  
Las tres secciones siguientes del cuadro de diálogo definen las direcciones IP de la configuración externa de este servidor perimetral. La posibilidad de cambiar las direcciones IP se ve afectada por el parámetro habilitar las opciones **de FQDN e IP separadas para conferencias web y a/V** en la configuración de propiedades en el nivel de grupo de servidores perimetrales.
  
## <a name="sip-access"></a>Acceso SIP

Edite la dirección IP externa asignada a la interfaz de red para el acceso por protocolo de inicio de sesión (SIP). Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.
  
> [!NOTE]
> Si la opción **Habilitar FQDN y la dirección IP para las conferencias web y a/V** en la página Configuración del grupo está habilitada, solo la dirección IP del acceso SIP estará disponible para su edición.
  
## <a name="web-conferencing"></a>Conferencia web

Edite la dirección IP externa asignada a la interfaz de red para las conferencias web. Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.
  
## <a name="audiovideo"></a>Audio o vídeo

Edite la dirección IP externa asignada a la interfaz de red para audio/vídeo (A/V). Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.
  
La configuración de la **dirección IP pública habilitada para NAT usada** es la dirección pública que usa la interfaz externa para la interfaz de red a/V o el servidor perimetral en general. Si el valor **Habilitar FQDN e IP diferentes para conferencias web y a/V** está habilitado, esta dirección IP pública se usa para las tres interfaces externas.
  

