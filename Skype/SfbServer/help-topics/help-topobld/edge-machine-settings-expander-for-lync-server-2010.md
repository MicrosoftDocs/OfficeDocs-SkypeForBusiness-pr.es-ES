---
title: Expansor de configuración de equipo perimetral para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar las propiedades de los equipos de servidor perimetral como un solo servidor perimetral o como equipos miembro en un grupo Edge, configure las opciones de configuración de nombre de servidor y dirección IP:'
ms.openlocfilehash: 411e870a874366754d17d0601ed1f216ce18899a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684783"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Expansor de configuración de equipo perimetral para Lync Server 2010
 
Para editar las propiedades de los equipos de servidor perimetral como un solo servidor perimetral o como equipos miembro en un grupo Edge, configure las opciones de **configuración de nombre de servidor y dirección IP** :
  
- **Nombre interno o FQDN**: escriba el nombre del equipo al que se hace referencia en el sistema de nombres de dominio (DNS). 
    
- **Dirección IPv4 interna**: escriba la dirección IPv4 de la tarjeta de interfaz de red (NIC) interna de este equipo.
    
- Configure la **dirección IPv4 externa** del **servicio perimetral de acceso** asociada con este equipo
    
    > [!IMPORTANT]
    > Si seleccionó usar una única dirección IP para la configuración del servidor perimetral, solo podrá editar la dirección IPv4 externa para el servicio perimetral de acceso. Los otros servicios perimetrales compartirán la misma dirección IPv4 que el servicio perimetral de acceso. 
  
- Si está disponible para editar, configure la **dirección IPv4 externa** del **servicio de conferencias web** asociada con este equipo
    
- Si está disponible para editar, configure el **servicio perimetral a/V** **dirección IPv4 externa** asociada con este equipo.
    
- Si está disponible para editar, configure la **dirección IPv4 pública habilitada para NAT** asociada con este equipo.
    
    > [!IMPORTANT]
    > La propiedad de configuración de una **dirección IPv4 pública habilitada para NAT** solo estará disponible para su edición si elige proporcionar la traducción de direcciones de red (NAT) para el servicio perimetral de a/V
  
  **Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
  **Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.
  
  **Ayuda** Abre esta pantalla de ayuda.
  

