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
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar las propiedades de los equipos del servidor perimetral como un solo servidor perimetral o como equipos miembros en un grupo de servidores perimetrales, configure las opciones de configuración de nombre del servidor y dirección IP:'
ms.openlocfilehash: eb2135391791fdb915578fe9938329b56c85908c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218931"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Expansor de configuración de equipo perimetral para Lync Server 2010
 
Para editar las propiedades de los equipos del servidor perimetral como un solo servidor perimetral o como equipos miembros en un grupo de servidores perimetrales, configure las opciones de **configuración de nombre del servidor y dirección IP** :
  
- **Nombre interno o FQDN**: escriba el nombre del equipo tal como aparece en el sistema de nombres de dominio (DNS). 
    
- **Dirección IPv4 interna**: escriba la dirección IPv4 de la tarjeta de interfaz de red interna (NIC) de este equipo.
    
- Configure la **dirección IPv4 externa** del **servicio perimetral de acceso** asociada con este equipo
    
    > [!IMPORTANT]
    > Si seleccionó usar una única dirección IP para la configuración del servidor perimetral, solo podrá editar la dirección IPv4 externa para el servicio perimetral de acceso. Los demás servicios perimetrales compartirán la misma dirección IPv4 que el servicio perimetral de acceso. 
  
- Si está disponible para edición, configure la **dirección IPv4 externa** de **servicio de conferencia web** asociada a este equipo.
    
- Si está disponible para edición, configure la **dirección IPv4 externa** del **servicio perimetral a/V** asociada con este equipo.
    
- Si está disponible para edición, configure la **Dirección IPv4 habilitada para NAT** asociada con este equipo.
    
    > [!IMPORTANT]
    > La propiedad de configuración de la **dirección IPv4 pública habilitada para NAT** solo estará disponible para su edición si elige proporcionar la traducción de direcciones de red (NAT) para el servicio perimetral a/V.
  
  **Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.
  
  **Cancelar** Descarta los cambios y cierra el cuadro de diálogo.
  
  **Ayuda** Muestra la ayuda de esta pantalla.
  

