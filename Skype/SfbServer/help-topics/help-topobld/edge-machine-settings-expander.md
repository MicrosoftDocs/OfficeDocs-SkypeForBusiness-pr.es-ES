---
title: Expansor de configuración de equipo perimetral
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
- ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Para editar las propiedades de un servidor en un grupo de servidores perimetrales, efectúe las acciones siguientes:'
ms.openlocfilehash: 7c3b3d45617d8feeee062bb16e1c7222b71118d8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807130"
---
# <a name="edge-machine-settings-expander"></a>Expansor de configuración de equipo perimetral
 
Para editar las propiedades de un servidor en un grupo de servidores perimetrales, efectúe las acciones siguientes:
  
El valor de **Nombre interno o FQDN** puede cambiarse editando el nombre de dominio completo. El nombre de dominio completo debe coincidir con el registro de host (A) de DNS y el nombre del sujeto del certificado asignado al servidor para la interfaz de red perimetral interna. El valor de **Dirección IP interna** define la dirección IP interna que se asigna a la interfaz de red definida como red interna respecto al diseño de la red perimetral.
  
Las tres secciones siguientes del cuadro de diálogo definen las direcciones IP para la configuración externa de este servidor perimetral. La opción **Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V** en las propiedades del grupo de servidores perimetrales determina la capacidad de cambiar la dirección IP.
  
## <a name="sip-access"></a>Acceso al Protocolo de inicio de sesión (SIP)

Edite la dirección IP externa que se asigna a la interfaz de red para acceso al protocolo de inicio de sesión. Esta dirección IP puede ser pública o una de las posibles direcciones IP privadas.
  
> [!NOTE]
> Si está habilitada la opción **Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V** en la página de configuración del grupo de servidores, solamente se podrá editar la dirección IP para acceso SIP.
  
## <a name="web-conferencing"></a>Conferencia web

Edite la dirección IP externa que se asigna a la interfaz de red para conferencia web. Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.
  
## <a name="audiovideo"></a>Audio o vídeo

Edite la dirección IP externa que se asigna a la interfaz de red para audio o vídeo (A/V). Esta dirección IP puede ser una dirección IP pública o una dirección en el intervalo de direcciones IP privadas.
  
El valor de **Dirección IP habilitada para NAT usada** es la dirección pública usada por la interfaz externa para la interfaz de red A/V o el servidor perimetral en general. Si está habilitada la opción **Habilitar direcciones IP y números completos de dominio independientes para conferencia web y A/V**, esta dirección IP se usa para las tres interfaces externas.
  

